# AI Engineer Roadmap 2026 — Career Guide V2.0

**Updated:** 2026-11-02  
**Primary track:** Middle AI Engineer — **LLM / AI Application & Agent Engineering**.  
**Supporting tracks:** model understanding, traditional ML, fine-tuning, inference optimization, production engineering.  
**Goal:** build, evaluate, deploy, debug and own reliable AI systems; not only run a chatbot tutorial.

## 0. Rules of this roadmap

- **Core**: independently explain, implement, test and debug.
- **Working**: use correctly, choose between approaches, and explain trade-offs.
- **Awareness**: understand the problem, vocabulary and limitations.
- **Advanced**: optional research/optimization depth, chosen by specialization.
- **L2 vs L3** refer to demonstrated learner mastery and are *not* roadmap phase numbers. See [mastery](MASTERY_LEVELS.md).
- **Big Picture → Why → Relevant Math → Implement → Break/Debug → Evaluate → Revisit**.
- Stop repeated manual calculation once fundamental correctness is established and the concept is usable. Keep unresolved deep dives in a backlog; revisit just in time.
- No project completion, score, learning status or model benchmark is presumed. Evidence is linked, not manufactured.
- **The 2026 label identifies the knowledge version, not a 31 December 2026 deadline.** Phases can overlap.

## Phase overview

| Phase | Topic | Rough weeks* | Required outcome |
|---|---|---:|---|
| 0 | Engineering baseline | 1–2 | Organized Python project, environment, tests and Git |
| 1 | Mathematics for Embeddings & Attention | 4–6 | Q/K/V attention lab and tensor shape tests |
| 2 | Calculus, Backpropagation & PyTorch | 5–7 | MLP/autograd training + gradient debug |
| 3 | Data, Statistics & Traditional ML | 4–6 | Baseline-led ML system with data validation |
| 4 | DL Architectures & Transformers | 6–9 | Implement small decoder-only Transformer |
| 5 | LLM Internals, Training & Generation | 4–6 | Tokenizer/generation loop and cache experiments |
| 6 | AI Application & Backend Engineering | 4–6 | Reliable, tested LLM inference API |
| 7 | Embeddings, RAG & LLM Evaluation | 6–9 | Evaluated production-style RAG |
| 8 | AI Agents, MCP & Reliability | 6–9 | Stateful tool-using agent with recovery |
| 9 | Fine-Tuning, Serving & Optimization | 7–10 | LoRA/SFT serving benchmark |
| 10 | MLOps, Infrastructure, Security & Production | 8–12 | Deployed, observed and secured AI service |
| 11 | System Design, Capstone & Ownership | 6–10 | End-to-end system with tests, metrics and ADRs |
| 12 | Specialization & Research Literacy | flexible | Deliberate depth in a relevant career track |

*Illustrative at ~12–15 focused hours/week; not promises or prerequisites. Parallel study, prior experience, equipment and project scope change actual durations. Total study may take ~14–24 months or longer; middle-level work experience is not automatically conferred by completing this repository.

---

## PHASE 0 — Engineering Baseline (Core; 1–2 weeks, continuous)

**Learn:** Python functions/classes/modules, generators, type hints, dataclasses/Pydantic, exceptions, environment/dependency management, NumPy/Pandas, JSON/Parquet basics, Git & PRs, Linux CLI, unit tests/pytest, logging, config, HTTP/REST, Big-O/data structures fundamentals, asyncio basics and Docker introduction.

**Build:** a clean repository structure with src/, tests/, experiments/, config, reproducible setup, README, linting/tests and a basic CI workflow.

**Gate:** someone else can clone, install, run, test and understand your code without modifying internals. Improve engineering habits in every subsequent phase.

## PHASE 1 — Mathematics for Embeddings & Attention (Core; 4–6 weeks)

**Core now:** scalar/vector/matrix/tensor, shape/axes/strides awareness, linear projections, dot product, general inner product, matmul, transpose, batched matmul, broadcasting, vector norms, cosine similarity, normalization, exponentials, softmax and numerical stability.

**Working now:** vector spaces/subspaces, span, basis, linear independence, matrix rank, orthogonality/projections. **Just-in-time / deeper later:** inverse, determinant, eigenvalues/eigenvectors, SVD, pseudoinverse, PSD matrices and long proofs. Revisit rank/SVD with LoRA or PCA.

**Connect math:** token embedding → projection to Q/K/V → QKᵀ score matrix → scale by sqrt(d_k) → mask → softmax over keys → weighted sum of V. Explain head/batch/sequence dimensions.

**Build A:** small embedding similarity experiment (dot vs cosine, normalization, retrieval ranking).

**Build B:** scaled dot-product attention in NumPy/PyTorch, tests against a reference implementation; add causal mask and shape/error tests.

**Gate:** independently justify each operation in softmax(QKᵀ/√d_k)V, predict tensor shapes, explain softmax axis and debug wrong transpose or masking. Avoid dozens of equivalent hand calculations.

## PHASE 2 — Calculus, Backpropagation & PyTorch (Core; 5–7 weeks)

**Core math:** derivatives, partial derivatives, chain rule, gradients, computational graph, gradient descent and basic matrix calculus. **Working:** Jacobian concept, directionals, Taylor/Hessian intuition, convex vs non-convex landscape.

**Core DL:** perceptron/MLP, linear + activation, GELU/ReLU/SiLU, losses (MSE, CE, BCE), backprop, weight initialization, normalization, residuals, regularization, dropout, gradient explosion/vanishing and train/validation behavior.

**Optimization:** SGD, momentum, Adam/AdamW, learning-rate schedules, weight decay, gradient clipping/accumulation; convergence and numeric stability. AdaGrad/RMSProp, constrained methods at Working/Awareness when appropriate.

**PyTorch:** tensors, autograd, nn.Module, Dataset/DataLoader, custom training loop, optimizer, eval/train, checkpoints, reproducibility, CPU/GPU device and mixed precision basics.

**Build:** derive a tiny network's gradient once on paper; compare NumPy/manual implementation against PyTorch autograd; train a small network; intentionally cause and debug NaNs, frozen gradients, bad learning rate, shape errors.

**Gate:** explain forward→loss→backward→step, independently implement a loop and diagnose a gradient issue. No requirement to symbolically differentiate a full Transformer.

## PHASE 3 — Data, Statistics & Traditional ML (Core/Working; 4–6 weeks, may overlap)

**Data:** NumPy/Pandas/Polars; clean/validate missing, duplicate and outlier data; leakage-safe splits, preprocessing and feature engineering; SQL joins/aggregations/CTEs/windows, PostgreSQL; CSV/JSONL/Parquet, ETL/ELT and data lineage/versioning.

**Traditional ML:** supervised/unsupervised/self-supervised concepts; linear/logistic regression, trees, random forests, gradient boosting/XGBoost/LightGBM; KNN/SVM/Naive Bayes and clustering (K-Means, PCA) at Working; feature selection, tuning, under-/overfitting and interpretability.

**Probability/statistics:** conditional probability/Bayes, expectations, variance/covariance, probability distributions, MLE/MAP, entropy/cross-entropy/KL, sampling, confidence intervals, hypothesis testing, bootstrap, A/B tests and correlation vs causation.

**Evaluation:** F1, accuracy/precision/recall, ROC/PR-AUC, MAE/RMSE/R², cross-validation, calibration, class imbalance and error analysis.

**Build:** data → quality checks → baseline → >=2 models → eval → justified choice → tested API, with reproducible environments.

**Gate:** defend model selection and prove a measurable improvement over a defined baseline, not merely report a good score.

## PHASE 4 — DL Architectures & Transformers (Core; 6–9 weeks)

**Sequential history (Working):** RNN, LSTM/GRU, hidden state, seq2seq, teacher forcing, encoder-decoder and recurrent vanishing-gradient limits. CNN essentials and image tensors at Awareness/Working; CV specialism later.

**Attention (Core):** Q/K/V, scaled dot-product, self vs cross, multi-head, causal and padding mask, attention complexity, visualization; GQA/MQA, FlashAttention at Working.

**Architectures (Core):** encoder-only (bidirectional/MLM), decoder-only (causal next-token), encoder-decoder (self + cross attention), embeddings, position, RoPE, feed-forward/MLP, residual, pre/post norm, LayerNorm/RMSNorm, GELU/SwiGLU, weight tying, KV cache concepts.

**Build:** Mini decoder-only Transformer in PyTorch: token embedding, position, causal MHA, block/MLP, norms, residual, LM head, CE loss, training loop and basic autoregressive generation.

**Gate:** draw and explain the encoder/decoder distinctions and the decoder tensor path, write/test a small model, and debug an attention mask issue. No need to train a frontier model.

## PHASE 5 — LLM Internals, Training & Generation (Core; 4–6 weeks)

**Tokenization:** BPE, WordPiece, SentencePiece, byte-level methods, special tokens, chat templates, vocabulary and token budgeting.

**Training:** causal vs masked LM, next-token objective, cross-entropy/perplexity, sequence packing, loss masking, data contamination, parameter counts, dense/MoE and model cards.

**Decoding:** logits, softmax, temperature, greedy, top-k, top-p/min-p, repetition penalties, stop sequences, structured outputs, beam search (Working).

**Inference:** prefill vs decode, token-by-token generation, positions/masks, KV cache, context length, memory/latency and output nondeterminism. Know GPT/Llama/Qwen-style architectures, SLMs, MoE, long-context and failure modes at Working. Reasoning/test-time compute at Awareness/Working.

**Build:** load an appropriately sized pretrained open-weight LM; implement or instrument a generation loop; compare sampling and cache behavior; benchmark time/memory with stated hardware and reproducible inputs.

**Gate:** explain text→tokens→embeddings→blocks→logits→next token and where training gradients differ from inference.

## PHASE 6 — AI Application & Backend Engineering (Core; 4–6 weeks)

**Backend:** FastAPI, REST, Pydantic, auth/authz, secrets, async/await, SSE/WebSocket streaming, PostgreSQL/Redis, caching, error handling, retries/timeouts, rate limits, background jobs, queues, request tracing, integration tests.

**Prompt & context:** roles/instruction hierarchy, zero/few-shot, prompt templates/versioning, structured output JSON Schema, function calling, context assembly/truncation/compression, prompt caching, context budget, prompt regression and injection awareness.

**Architecture:** API model vs self-host, synchronous/streaming, state/conversation isolation, cost tracking, model routing basics and backward-compatible API contracts.

**Build:** LLM-backed backend with streaming, auth, validation, retries, structured outputs, logs, tests and clear setup.

**Gate:** a teammate can run and call the service; key bad-input and failure paths are covered.

## PHASE 7 — Embeddings, RAG & LLM Evaluation (Core; 6–9 weeks)

**Embeddings/search:** token/sentence and contextual embeddings, sparse/dense/hybrid search, TF-IDF/BM25, cosine/dot/L2, bi/cross encoders, query-document asymmetry, FAISS, Qdrant/pgvector, HNSW and metadata filters.

**RAG:** PDF/HTML/DOCX ingestion, parsing, chunking, overlap, metadata, indexing, query rewrite, retrieval, candidate fusion, reranking, context assembly, grounded answers/citations, abstention, permissions and document lifecycle updates.

**Evaluation:** golden datasets, Recall@K, MRR/NDCG, retriever vs generator metrics, context precision/recall, faithfulness, citation accuracy, hallucinations, human-calibrated LLM-as-a-judge, latency/cost, regression and A/B testing.

**Advanced at Working:** parent-child and semantic chunking, multi-query/multi-hop RAG, GraphRAG, SQL/multimodal/temporal RAG, caching and monitoring.

**Build:** production-style hybrid RAG with reranker, source citations, user permissions, golden tests, tracing, separate retrieval and generation analyses.

**Gate:** demonstrate a meaningful baseline comparison and localize a failure to ingestion/retrieval/reranking/context/generation.

## PHASE 8 — AI Agents, MCP & Reliability (Core; 6–9 weeks)

**Concepts:** workflow vs agent, agent loop, planning/acting/observation, tool selection, function schemas, tool validation, state, termination and logging.

**Patterns:** routing, prompt chaining, parallelism, ReAct, plan-and-execute, orchestrator-worker, evaluator-optimizer, checkpoints/resume, human approvals.

**MCP:** host/client/server, tools/resources/prompts, JSON-RPC, transports, discovery, auth/permissions and secure MCP server/client.

**Reliability:** timeout, retry, idempotency, infinite-loop and step limits, budgets, tool failures, state persistence, resume, audit traces, tool injection, sandbox boundaries, tenant isolation and evaluation of tool trajectories.

**Working/Awareness:** A2A, multi-agent coordination, long-term memory and durable execution patterns.

**Build:** stateful, tool-using agent with persistent checkpoints, human approval for side effects, failure simulation, tracing and task-completion metrics.

**Gate:** can recover from a failed tool/malformed output, prevent duplicate actions and explain why a deterministic workflow might be safer.

## PHASE 9 — Fine-Tuning, Serving & Optimization (Core/Working; 7–10 weeks)

**Fine-tuning:** pretrained vs frozen weights, SFT, instruction/chat templates, packing, truncation/loss masking, hyperparameters, checkpointing, LoRA/QLoRA, rank/alpha, adapter merging, catastrophic forgetting, before/after eval and deciding RAG vs SFT.

**Post-training (Working):** preference data, reward models, RLHF, DPO, PPO/GRPO concepts, distillation, synthetic data and reward hacking.

**Serving:** prefill/decode, KV cache, continuous batching, concurrency, GPU VRAM/weights/activations, vLLM or llama.cpp, OpenAI-compatible APIs; TTFT, TPOT, tokens/s, P95 latency, throughput and cost.

**Quantization (Working):** FP32/FP16/BF16, FP8 awareness, INT8/INT4, scales/zero points, PTQ vs QAT, GPTQ/AWQ, bitsandbytes/GGUF, quality regressions. FlashAttention/PagedAttention, prefix caching, speculative decoding, gradient checkpointing, mixed precision and profiler at Working.

**Build:** select a supported model/hardware combo; baseline, LoRA/QLoRA SFT, held-out evaluation, serve API, latency/VRAM/quality benchmark; quantize only if the engine/hardware makes it feasible.

**Gate:** explain and *measure* training/inference, memory/quality/cost trade-offs; no made-up GPU speedups.

## PHASE 10 — MLOps, Infrastructure, Security & Production (Core/Working; 8–12 weeks)

**Lifecycle:** experiment tracking/MLflow, model/data registry, dataset versions, reproducibility, CI/CD, regression evaluation gates, deployment, canary/rollback, monitoring and drift.

**Infrastructure:** Linux, Docker/Compose, Kubernetes fundamentals, networking, load balancers, queues, object storage, cloud IAM, compute/GPU resources, select *one* primary cloud, infrastructure as code at Working.

**Security/governance:** auth/authz and RBAC, OAuth concepts, secrets, prompt injection/jailbreak, RAG exfiltration and tenant separation, tool permissions, unsafe tool execution, privacy/PII, data retention, licensing, fairness/safety evaluation and threat modeling.

**Observability/reliability:** structured logs, OpenTelemetry/traces, token and cost metrics, P50/P95/P99 latency, error rate, alerts, root-cause analyses, incident recovery and postmortems.

**Build:** deploy an earlier AI service with Docker, CI, auth, monitored metrics, eval regression checks, a security review, incident simulation and rollback steps.

**Gate:** self-manage common production failures of the project without relying on a single notebook demo.

## PHASE 11 — System Design, Capstone & Engineering Ownership (Core; 6–10 weeks)

**Design:** requirements, baseline, data/request flow, boundaries, state, model selection, caching, queuing, latency/throughput, capacity, scalability, failure isolation, privacy and total cost.

**Judgment:** accuracy vs latency, quality vs cost, API vs local model, RAG vs fine-tuning, workflow vs agent, single vs multi-agent, local vs cloud, maintainability vs complexity, benchmark-driven decisions.

**Ownership:** ADRs, code review, docs, architecture diagrams, test strategy, technical debt, release/rollback, incident RCA, collaboration and technical communication.

**Capstone:** an enterprise document assistant or similar AI system with ingestion, retrieval/model decisions, authenticated API, optional controlled tool agent, golden eval set, tracing, deployment, performance and security tests, ADRs and an incident simulation.

**Gate:** demonstrate, benchmark, explain, maintain and debug a coherent system. Portfolio output is evidence; the **job title Middle** also relies on actual teamwork and independent professional responsibility.

## PHASE 12 — Advanced Specialization (select, not all required)

- **A. AI Application / Agent (primary)**: advanced RAG, context systems, MCP/A2A, reliable agents, multi-tenancy, evaluation and runtime security.
- **B. LLM Model/Fine-tuning**: curated pretraining data, distributed training, PEFT/post-training, distillation, reward learning and research reproduction.
- **C. LLM Inference/Optimization**: GPUs, CUDA/Triton, GEMM, kernels, Paged/FlashAttention internals, quantization, speculative decoding, disaggregated serving and profiling.
- **D. AI Platform/MLOps**: Kubernetes, orchestration, IaC, autoscaling, GPU scheduling, observability, disaster recovery and FinOps.
- **E. CV/Multimodal**: image processing, CNN/ViT, detection/segmentation, CLIP/VLM, multimodal RAG, diffusion/DiT/flow, speech/video.
- **F. Other ML**: recommender/ranking, graph, causal ML, forecasting, edge/on-device, RL, robotics and embodied AI.
- **Research literacy across tracks:** paper evaluation, baseline/ablation, reproducibility, data leakage, licensing, benchmark limitations and emerging model architectures (MoE, SSM, hybrid attention, reasoning-time compute, ultra-low-bit models).

## Cross-phase competencies (never postpone all of these until production)

**Always:** clean Python, Git, tests, logs, documentation, reproducibility, data safety, baseline evaluation, model limitations, dependency management and cost/latency awareness.  
**For every major project:** README, architecture diagram, setup, tests, baseline, metrics, error analysis, reproducible results, known limitations and justified trade-offs.  
**Assessment:** 4 × 25 rubric; >=75/100 and each criterion >=12/25; a working project requires its own acceptance tests. See [evaluation standard](MASTERY_LEVELS.md).

## Start from existing evidence, not a blank slate

The Tensor Fundamentals for LLM sub-scope passed an L2 test (54/60, 90%) on 2026-10-21, *not* the entire Linear Algebra topic. Current study starts with Q/K/V and scaled attention, then masking and gradient/autograd, rather than repeating lots of unrelated determinant or transpose arithmetic. See [active path](../progress/ACTIVE_PATH.md).

## How this overlays the original syllabus

The [original reference](ROADMAP_SOURCE.md), [37-module catalog](../indexes/ROADMAP_INDEX.md) and [219-subtopic index](../indexes/topics.json) remain intact. The [V2 phase mapping](../indexes/PHASE_INDEX.md) reorders what to learn; it does **not** delete subjects.