# LLM Fundamentals Diagnostic — Round 1 (Transformer and Inference)

**Recorded:** 2026-11-04 (Asia/Bangkok). **Assessment:** in-chat, open-ended L2-focused diagnostic. **Not a formal Core/L2 pass; L3 remains UNASSESSED.** Original modules: 6, 9.1, 9.4, 15; V2 Phase 4/5/9.  
**Scenario:** hypothetical decoder-only 8B / 32 layers / 32 query heads / 8 KV heads (GQA) / d_head 128 / BF16 KV cache / batch 2 / prompt 2048 tokens / max 256 new tokens / no prefix sharing, no sliding window. No real inference engine, hardware traces or code were supplied.

## Scoring (rubric specific to these 4 questions; not official V2 4-competency gate)

| Question | Previously assigned points | Evidence and limit |
|---|---:|---|
| Transformer, Q/K/V, GQA and shapes | 16/25 | Correct GQA 4:1 ratio and Q/K/V prefill shapes; incorrect claim that K/V are made from grouped Queries; self-declared gap in linear projection from hidden states |
| Prefill/decode & KV Cache | 20/25 | Strong generation overview, correctly connects cache to avoiding old prefix recomputation and O(n) new-query attention; incorrectly attributed O(n²) prefill only to absence of cache |
| KV cache memory | 15/25 | Recognizes linear token scaling and non-weight memory; incorrect 128 MB initial estimate due omitted batch and BF16 byte factors |
| Production inference diagnosis | 12/25 | Recognizes quantization can fail to speed up, batches can trade latency/memory, and attention kernels matter; omits queue/prefill/decode/TTFT/TPOT metrics and incorrectly describes FlashAttention memory transfer |
| **Total** | **63/100** | **Provisional; below 75 diagnostic threshold, not a certification of overall LLM proficiency** |

## Essential corrections

### How Q/K/V are created

At each Transformer layer, *the same current hidden states* X are independently projected using learned parameter matrices: Q=XW_Q, K=XW_K, V=XW_V (subject to architecture details such as normalization and position encoding). It is false that one KV pair is **generated from four Query heads**. In GQA (32 query, 8 KV), each of 8 independently projected K/V heads is **shared by** four Q heads during attention. Reducing KV heads from 32 to 8 cuts *KV cache storage* about 75% versus like-for-like 32-KV-head MHA, not total VRAM and not invariably accuracy.

With B=2,T=2048,head_dim=128, Q=[2,32,2048,128] and K=V=[2,8,2048,128]. To illustrate projections, if d_model=4096 (not stipulated by original scenario), W_Q is [4096,4096] and W_K=W_V [4096,1024]. Each layer has its own trained weights and K/V tensors.

### Prefill, decode and complexity

Prefill processes a whole prompt in parallel; standard dense attention prefill still scales O(T²) in attention arithmetic, *whether or not KV is retained for decoding*. With cache, for each newly decoded query, Q_new @ K_cachedᵀ has O(T) attention-score arithmetic for fixed head_dim, and historical prefix K/V need not be recomputed. Without cache, naive autoregressive decoding recomputes prefix hidden states and attention, typically O(T²) for the whole prefix *per decoding step*. Caching trades GPU memory for avoiding repeated computations.

### Correct KV cache memory

KV bytes = **B × L × 2(K,V) × H_KV × T × d_head × bytes_per_element**  
= 2 × 32 × 2 × 8 × 2048 × 128 × 2  
= **536,870,912 bytes = 512 MiB** post-prefill; at T=4096 it becomes **1,024 MiB = 1 GiB**. The user's 128 MiB used only one factor 2 where the full calculation needs **three independent factors of 2** (batch size, K+V, BF16 bytes/element). Ignore allocator overhead, weights, workspaces, model activations and additional generated KV.

### Production engineering corrections

Before enabling a kernel, changing batching or quantizing, record per-request/engine metrics: P50/P95 e2e latency, queue latency/depth, TTFT, TPOT/ITL, prefill/decode time, input/output tokens, tokens/s throughput, GPU utilization/VRAM/KV occupancy, OOM/preemption, error/retry rate and workload mix. Compare controlled loads with concurrency 10 and 50, same input/output distribution, engine configs and quality criteria.

FlashAttention is an IO-aware *tiling strategy reducing HBM↔on-chip SRAM traffic* and avoids materializing the full attention matrix; HBM is GPU device memory (VRAM), not a separate transfer destination. It does not fundamentally reduce ordinary dense attention FLOPs from O(T²) to O(T). Hardware/kernel compatibility and numerical differences are relevant. Larger batching can improve throughput while increasing memory/queue or per-request latency. Quantization (e.g. BF16 weight to FP8) can roughly halve *weight storage* where supported; speed/quality changes must be benchmarked and KV cache dtype may remain BF16.

## Observed strengths

- Understands GQA query-to-KV ratio and correct tensor shapes.
- Good high-level text→token→embedding→blocks→logits→sampling mental model.
- Understands KV reuse and the difference between Q_new (one position) and prefix K/V.
- Realistic skepticism about whether quantization actually improves latency.

## Prioritized gaps and learning path

1. **Just-in-time Linear Algebra → Q/K/V**: tensor projection using W_Q/W_K/W_V, reshape/transposes, head sharing and masking; no need to re-study unrelated determinant drills.
2. **KV Cache accounting**: batch × layers × K/V × KV heads × tokens × head dim × bytes. Convert bytes↔MiB correctly and distinguish prefill vs decode memory.
3. **Attention compute complexity**: prefill O(n²), per-step cached decode attention O(n).
4. **Inference observability & benchmarking**: TTFT/TPOT/queue/prefill/decode and throughput-vs-latency; troubleshoot bottlenecks before choosing FlashAttention/batching/quantization.

## Next checkpoint

Ask a **brief transfer question** to verify the Q/K/V projection mapping and corrected memory factors using changed settings. Then advance to Round 2 **Training vs SFT vs LoRA / gradient flow**, requiring explicit assumptions and explaining observed mistakes. Never imply code implementation/L3 is complete.

## External technical references (to verify versions and concepts)

- [PyTorch scaled_dot_product_attention & GQA](https://docs.pytorch.org/docs/stable/generated/torch.nn.functional.scaled_dot_product_attention)
- [FlashAttention: IO-aware exact attention](https://arxiv.org/abs/2205.14135)
- [vLLM production metrics](https://docs.vllm.ai/en/latest/usage/metrics/)
