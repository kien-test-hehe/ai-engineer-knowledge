# Active learning path — proposed next steps

**Updated:** 2026-11-02 · **Recommended next emphasis:** Phase 1 → Phase 2 → Phase 4, with Phase 0 engineering practice continuous.

## Existing evidence (do not overinterpret)

- **Completed L2 sub-scope:** Tensor Fundamentals for LLM, 2026-10-21, 54/60 = 90%, 12 questions, original assessment rubric. [Record](assessments.jsonl).
- **Not certified:** whole Linear Algebra module; full L3 implementation; mathematical rank/basis/determinant/eigen/SVD; other phases.
- **Already available for practice:** [Tensor shapes notebook](../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notebooks/01-tensor-shapes-and-memory.ipynb) and [Attention shape notebook](../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notebooks/02-attention-shape-reasoning.ipynb). These are study resources, not proof of independent completion.

## Suggested immediate sequence

| Step | Study/experiment | Check before moving on |
|---|---|---|
| 1 | MatMul, transpose, dot/inner product tied to Q/K/V projections | Explain the operation/shape, solve a novel shape question |
| 2 | Embedding similarity with dot vs cosine | Code outputs agree with intuition/tests |
| 3 | Scaled dot-product attention: QKᵀ, divide sqrt(d_k), softmax over key axis, @V | Forward implementation and shape tests |
| 4 | Causal mask; masked future positions; test no future leakage | Correct mask, probabilities and edge cases |
| 5 | Batched multi-head attention; contrast encoder/decoder/self/cross attention | Independent shape reasoning and debugging |
| 6 | Targeted Phase 1 checkpoint (75/100 + >=12 per criterion) | Record **actual** assessment before upgrading mastery |
| 7 | Chain rule, a tiny manual gradient and PyTorch autograd verification | Manual ≈ autograd, train/debug a tiny MLP |
| 8 | Continue mini decoder-only Transformer | Training and inference distinction, source-specific tests |

## Deep-dive backlog (not blocking attention)

Determinant proofs, high-dimensional manual matmul repetitions, full eigen/SVD derivations, positive semidefinite theory, detailed Jacobian/Hessian derivations. Revisit these with PCA, LoRA, numerical optimization or model research as appropriate.

## Evidence to collect next (currently NOT recorded)

- New attention lab/notebook with real executed output and tests.
- A self-explained shape/mask/debug assessment.
- Explicit evidence for L3 independent implementation.
- A concise write-up: why the math matters in the actual LLM block.

This file is a **study proposal**, not a task-completion claim.