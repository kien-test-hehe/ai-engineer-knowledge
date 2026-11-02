# 00 — Attention & Mini Transformer (Foundation Lab)

**V2 phases:** 1, 2, 4, 5. **Status:** PLANNED; no implementation or test output recorded.

## Why this project exists

Bridge pure Linear Algebra to working decoder-only Transformer architecture, with just-in-time math and code. This is a learning lab, not a substitute for production RAG, fine-tuning, system design or employment experience.

## Milestones

1. **Embedding similarity:** create tiny vector representations, compare dot-product vs cosine ranking (and normalized results).
2. **Q/K/V projections:** generate input tensor, project it, and trace batch/head/sequence/head-dim axes.
3. **Scaled dot-product attention:** calculate QKᵀ/√d_k, apply softmax across key positions, multiply by V.
4. **Causal mask:** verify that future positions receive zero attention probability and cannot influence previous tokens.
5. **Multi-head attention:** split/merge heads, test dimensions and compare numerical results to a trusted PyTorch reference in compatible settings.
6. **Backpropagation:** derive a small gradient manually and compare to autograd; test frozen weights/gradient flow.
7. **Decoder block:** RMSNorm/LayerNorm, residuals, MLP, attention. Compare encoder bidirectionality vs causal decoder behavior.
8. **Tiny LM:** token embeddings, blocks, LM head, CE loss, training loop, short autoregressive sampling.

## Required tests / questions

- Check attention output shape, row sums of valid softmax rows, mask behavior and gradients.
- Test an invalid tensor shape and an intentionally wrong mask/softmax axis; explain the failure.
- Show a deterministic example with seed and dependency versions.
- Train on small, openly usable text data; report real loss and note limits, not invented model quality.

## What to submit

A small set of human-readable notebooks (linked via an eventual registry), ideally tested Python functions, saved reproducible safe outputs, a 1-page explanation of math→model and a debug report.

## Completion evidence

Use the [new 4 × 25 rubric](../../curriculum/MASTERY_LEVELS.md) for a targeted checkpoint and confirm independent L3 implementation. **No notebook or score has been created for this project yet.**

## Existing references

- [Tensor fundamentals note](../../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notes/01-tensor-fundamentals-for-llm.md)
- [Attention shape notebook](../../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notebooks/02-attention-shape-reasoning.ipynb)
- [Math-to-LLM map](../../curriculum/MATH_TO_LLM_MAP.md)