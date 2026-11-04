# LLM Fundamentals — upcoming diagnostic plan (V2 Phase 4/5/9)

**Status:** PLANNED; no questions graded, no mastery promoted as of 2026-11-04.  
**Purpose:** Calibrate actual knowledge before deciding which earlier learning modules can be shortened. Adapt difficulty to prior working experience. **Do not** force beginner-level definitions after strong evidence.

## Focus and source mapping

| Area | Questions | Original modules |
|---|---|---|
| Transformer internals | decoder-only vs encoder-only/encoder-decoder, attention Q/K/V, causal mask, tensor/head dimensions, GQA | 6, 9.1 |
| Training & fine-tuning | autoregressive objective, loss masking, gradient flow, freeze/LoRA, stability, evaluation | 5, 9.3, 14 |
| Inference | prefill vs decode, KV cache, generation, batching, latency/memory trade-offs | 9.4, 15 |
| Tokenization | token counts, chat templates, truncation, data leakage | 9.2 |
| Engineering judgment | design a benchmark and choose model/technique using evidence, cost, quality | 13, 23, 31 |

## Format

1. **Round 1: open-ended architecture/inference case** with all specs explicitly fixed (batch, layers, query/KV heads, head dimension, dtype, sequence length). Ask for tensor shapes, prefill vs decode, approximate KV memory and high-value debugging metrics. No multiple-choice guessing.
2. **Round 2: training/fine-tuning case** differentiating pretraining/SFT, frozen weights, LoRA rank, gradients, data leakage and model evaluation.
3. **Round 3: engineering decision case** balancing latency, VRAM, accuracy, context limits and cost, with explicit controlled experiments.
4. **Optional later:** independent PyTorch implementation/tests before claiming L3.

## Scoring integrity

Record transparent per-round qualitative/quantitative feedback, then apply a separately agreed L2 rubric with a consistent, valid question set. **Do not treat open-ended conversation or a topic-coverage estimate as V2 certified Core or L3.** Preserve all user evidence, assumptions and untested capabilities.
