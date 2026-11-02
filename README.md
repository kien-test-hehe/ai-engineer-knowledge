# AI Engineer Knowledge Base — Career Guide V2.0 (2026)

> **Learning by Building · Math in Context · LLM-first · Production-oriented**  
> Target: **Middle AI Engineer (LLM / AI Application focus)**. Updated: **2026-11-02**.

## Start here

1. **[Career Guide V2 — the active learning path](curriculum/LEARNING_PATH_V2.md)**: phases 0–12, learning scope, expected artifacts, gates, priorities, scheduling.
2. **[Phase index](indexes/PHASE_INDEX.md)**: connects V2 learning order to every original topic (the original topic IDs remain stable).
3. **[Math → LLM map](curriculum/MATH_TO_LLM_MAP.md)**: learn linear algebra and calculus *inside* embeddings, attention, backpropagation and LoRA.
4. **[Current next steps](progress/ACTIVE_PATH.md)**: the recommended learning sequence, with no invented mastery.
5. **[Mastery & evaluation rules](curriculum/MASTERY_LEVELS.md)**: 75/100 rubric, L2/L3 distinction, assessment evidence.
6. **[Projects](projects/README.md)** and **[Middle competency standard](competency/README.md)**.

## How this repository is organized

- **curriculum/** — active V2 study path and original canonical roadmap.
- **indexes/** — learning-order index AND complete original topic index.
- **knowledge/** — 10-part / 37-module / 219-subtopic source taxonomy; notes, labs and notebooks live under their original topic IDs.
- **projects/** — hands-on deliverables and evidence of engineering skills.
- **progress/** — assessments, current phase, review queue (never infer mastery).
- **docs/** — learning workflow, notebook conventions and naming.
- **templates/** — assessment and topic templates.

### The 13 phases

| Phase | Focus | Evidence |
|---|---|---|
| 0 | Engineering baseline | Reproducible Python repo, tests, Git |
| 1 | Math for embeddings & attention | Embedding similarity + scaled-dot-product attention |
| 2 | Calculus, backprop & PyTorch | NumPy MLP, autograd and gradient debugging |
| 3 | Data, statistics & traditional ML | Reproducible ML baseline → API |
| 4 | DL architectures & Transformer | Mini decoder-only Transformer |
| 5 | LLM internals & generation | Tokenization, decoding, KV cache experiments |
| 6 | AI application & backend | Tested LLM API, auth, streaming |
| 7 | Embeddings, RAG & evaluation | RAG with retrieval, reranking and eval |
| 8 | Agents & MCP | Stateful, recoverable agent workflow |
| 9 | Fine-tuning, inference & optimization | LoRA/QLoRA, serving and benchmarks |
| 10 | MLOps, cloud, security, production | Deploy, monitor, protect and roll back |
| 11 | System design & ownership | Integrated capstone with decision records |
| 12 | Advanced specialization | Choose a focused technical track |

Phases are an **ordered learning emphasis**, not 13 isolated prerequisites. Software engineering, evaluation, security and production thinking are recurring threads.

## Current starting point

The historical **Tensor Fundamentals for LLM** subtopic has a documented **L2 PASS 54/60 = 90% (2026-10-21)**; this does *not* mean the entire Linear Algebra module or its L3 practical is complete. Evidence: [assessments](progress/assessments.jsonl), [topic](knowledge/01-foundations/01-mathematics-for-ai-and-machine-learning/01-01-linear-algebra/README.md).

**Recommended next learning module:** Q/K/V projections → scaled dot-product attention → causal mask → shape-debugging; then chain rule/autograd for actual training. See [active path](progress/ACTIVE_PATH.md).

## Source preservation

- [Original 2026 roadmap — archived as reference, unchanged](curriculum/ROADMAP_SOURCE.md)
- [Original 37-module index](indexes/ROADMAP_INDEX.md)
- [Original 219-topic machine-readable index](indexes/topics.json)

The original structure is the **knowledge catalog**; V2 is the **learning order and career priority**. Neither a syllabus checkbox nor an AI-generated note is evidence of mastery.

## Contribution & approval

Use a branch and PR for knowledge/curriculum changes; **do not merge to main without user review**. Follow [workflow](docs/WORKFLOW.md), [notebook rules](docs/NOTEBOOKS.md), [agent rules](AGENTS.md).