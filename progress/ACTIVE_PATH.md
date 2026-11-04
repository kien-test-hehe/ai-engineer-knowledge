# Active learning path — Competency-driven V2

**Updated:** 2026-11-04. Learning order is flexible according to evidence. Do not blindly require Phase 0→11 serially.

## Known observations

- **Tensor Fundamentals for LLM (subscope 1.1):** L2 PASS, 54/60=90%, 2026-10-21; see [record](assessments.jsonl).
- **RAG conversational diagnostic:** 3 rounds with provisional scores 68, 77, 65 and qualitative synthesis showing substantial conceptual/architecture knowledge. **No formal overall RAG L2 PASS; L3 unassessed.** See [report](diagnostics/2026-11-04-rag-l2-diagnostic.md).
- **Work experience reported:** more than one year of AI-related practical work. This is contextual input for interview difficulty, **not evidence that a specific untested competency is passed**.
- **Unknown:** full implementation strength, production benchmark validity, Transformer internals training/inference depth and remaining modules.

## NEXT: Calibrate before prescribing basic coursework

1. **LLM Fundamentals L2 diagnostic** — start with a concrete decoder-only inference case; follow with training/LoRA and engineering decision cases. [Diagnostic plan](LLM_DIAGNOSTIC_PLAN.md).
2. **Then calibrate NLP** as needed; avoid elementary definitions if already demonstrably understood.
3. **Targeted RAG learning:** golden datasets, per-stage retrieval/generation metrics, paired tests, distractor and positional controls, root-cause tracing, end-to-end quality/latency/cost trade-offs.
4. **Independent RAG implementation challenge:** compare exact conditions with code, real measured outputs and acceptance tests to establish L3; do **not** mark it complete yet.
5. **Math-in-context track stays active in parallel:** Q/K/V projections → scaled dot-product attention → causal masking → autograd/gradient debugging → small decoder-only Transformer. See [math map](../curriculum/MATH_TO_LLM_MAP.md).

## Prioritized learning policy

- **Already demonstrated conceptual competence:** use a fast checkpoint instead of rerunning long introductory modules.
- **Partial/uncertain:** targeted experiments and active recall, then checkpoint.
- **Untested implementation:** L3 unassessed until runnable independent evidence.
- **Math deeper than immediate model use:** record in backlog (e.g., determinant proofs, detailed eigendecomposition/SVD, Hessians) and revisit for LoRA/PCA or specific engineering needs.

## Available early-phase notebooks (resources, not certification)

- [Tensor shapes & memory](../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notebooks/01-tensor-shapes-and-memory.ipynb)
- [Attention shape reasoning](../knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/notebooks/02-attention-shape-reasoning.ipynb)

Any new assessment must include clearly specified hypotheses, scope, rubrics and measured evidence; no invented output or mastery.

## Update — 2026-11-04: LLM Fundamentals Round 1

- [Diagnostic report](diagnostics/2026-11-04-llm-inference-round1.md): preliminary **63/100**, **not a formal L2 PASS**, L3 unassessed.
- Strengths: inference flow, GQA head ratio/shapes, KV Cache purpose, quantization skepticism.
- **Immediate micro-remediation (before Round 2):** Q/K/V are independent learned projections from hidden states (NOT generated from grouped query heads); 512 MiB vs 1GiB KV memory with correct factors; prefill O(n²) attention even with cache; queue/TTFT/TPOT metrics before optimization.
- Next: short transfer check, then LLM training/SFT/LoRA diagnostic. Do not mark module 9 as mastered.
