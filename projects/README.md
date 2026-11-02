# Hands-on projects — Career Guide V2

The original five major projects are preserved as scaffold and still remain the production/portfolio targets. Add a **foundation project** to prevent jumping into RAG or agents before understanding Transformer internals.

## Foundation lab — before production projects

- [00. Attention & Mini Transformer](00-attention-and-mini-transformer/README.md) — embedding similarity → attention → masking → tiny decoder-only LM; includes math-to-LLM debugging.

## Five major original portfolio projects

| Existing project | V2 phase | Engineering evidence |
|---|---|---|
| [01. End-to-end ML System](01-end-to-end-ml-system/README.md) | 3, 6, 10 | Data validation, baseline, evaluation, API, deployment |
| [02. Production RAG](02-production-rag/README.md) | 7, 10 | Hybrid retrieval, reranking, citations, evaluation, security |
| [03. Autonomous Agent Workflow](03-autonomous-agent-workflow/README.md) | 8, 10 | State, MCP/tools, approval, retries, tracing, agent eval |
| [04. Optimized Local LLM Serving](04-optimized-local-llm-serving/README.md) | 5, 9, 10 | TTFT/TPOT, VRAM, quantization and quality/perf benchmarks |
| [05. Model Training & Fine-tuning](05-model-training-and-fine-tuning/README.md) | 2, 4, 9 | SFT/LoRA, checkpoint, reproducibility, before/after evaluation |

## Final integrated capstone (Phase 11)

Combine relevant capabilities into one well-scoped product with architecture decisions, secure authenticated APIs, evaluation regression tests, observability, deployment and an incident simulation.

## Definition of done

For each project: reproducible setup, README, architecture diagram, baseline, real tests, metrics, debug/failure analysis, version/hardware notes when benchmarking, limitations and trade-offs. Do not mark a scaffold or an AI-written description as completed implementation.

**Status:** existing five project folders are scaffold-only unless later actual evidence demonstrates otherwise. This index does not assert completion.