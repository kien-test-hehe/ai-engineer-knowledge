# Math in Context — from foundations to actual LLM engineering

**Purpose:** Connect each math topic to a concrete model component, an observable output and a debug use case. Do not spend weeks calculating without understanding why a model needs the operation.

| Math | First real LLM context | Minimum actionable competency | Deep dive trigger |
|---|---|---|---|
| Tensors and axes | embeddings, hidden states, batching | explain batch/seq/head/dim, verify shape | tensor parallelism / custom kernels |
| Matrix multiplication | Q/K/V projections, MLP | matmul dimensions, implement, compare | GEMM performance |
| Transpose | QKᵀ | explain score-matrix shape and semantics | physical memory layout/caching |
| Dot/inner product | attention scores, embeddings | compute, interpret and normalize similarity | retrieval metric learning |
| Vector norms | normalized embeddings, RMSNorm | explain scale and correct axis | numerical stability |
| Vector spaces/basis/rank | hidden representations, LoRA | interpret low-rank intuition | rank/adapter bottleneck |
| Eigenvalues/SVD/PCA | projection/compression, LoRA background | explain decomposition at high level | low-rank compression or PCA |
| Chain rule | backpropagation | derive one small example and autograd-verify | custom backward / research training |
| Gradient | train and fine-tune | inspect gradients, troubleshoot frozen weights | optimization research |
| Probability | next-token prediction | explain logits→softmax→sampling | calibration, probabilistic decoding |
| Entropy / cross-entropy / KL | LM loss, DPO, distillation | connect losses to predicted distributions | post-training |
| Numerical precision | FP16/BF16, INT8/INT4 | detect overflow/accuracy trade-off | kernel/quantization |
| Statistics & uncertainty | eval, A/B, model selection | compare to baseline with fair sampling | significance/power studies |

## The first practical pipeline

Text → Token IDs → Embeddings → Q/K/V linear projections → Q @ K.transpose(-2,-1) → scale → causal mask → softmax over **key** axis → weighted sum with V → residual/MLP → logits.

Example per head: Q and K of shape (batch, heads, tokens, head_dim) yield an attention score tensor (batch, heads, query_tokens, key_tokens). The final softmax is across **key_tokens**. A causal mask prevents each query position from attending to future key positions.

**Train vs infer:** chain rule/autograd is necessary to update trainable parameters in training/fine-tuning, but not for an ordinary no-grad autoregressive inference loop.

## Stopping rule

1. Explain **why** the operation exists.
2. Predict the input/output and tensor shapes.
3. Implement a minimal correct version and a test.
4. Investigate a realistic failure (wrong axis, mask, NaN, memory, frozen gradient).
5. Move on if mastery evidence is sufficient; log mathematical proofs/derivations for a later deep dive.

A long proof or the 20th hand-computed matrix product is not automatically better evidence of Middle-level AI engineering.

## Related material

- [Active path and next exercises](../progress/ACTIVE_PATH.md)
- [Career Guide V2](LEARNING_PATH_V2.md)
- [Original Linear Algebra topic](../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/README.md)
- [Existing attention shape notebook](../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notebooks/02-attention-shape-reasoning.ipynb)