# RAG L2 Diagnostic — retrospective of three conversational rounds

**Recorded:** 2026-11-04 (Asia/Bangkok)  
**Original knowledge module:** [11. Embeddings, Search & RAG](../../knowledge/03-generative-ai-and-llm-engineering/11-embeddings-search-and-retrieval-augmented-generation/README.md), especially 11.6 (pipeline), 11.8 (evaluation/debugging), 11.9 (production).  
**V2:** Phase 7 (RAG + LLM Evaluation); additional Phase 9 (inference) and Phase 11 (judgment).  
**Evidence:** user's written responses and in-chat feedback for Diagnostic Challenge 1, Round 2 experimental design, and the final counterfactual. No runnable code or external system artifacts were reviewed.  
**Assessor:** conversational AI feedback; user review through PR required.

## Outcome and important limits

- **Status: PROVISIONAL L2 DIAGNOSTIC — not a formal L2 PASS.**
- **L3 implementation: UNASSESSED.** No independent code, benchmark logs, test suite or real production traces were examined.
- **Module-level mastery remains unassessed.** Evidence here concerns parts of RAG architecture, debugging and experimental judgment; not all of module 11.
- The previous assistant gave **68/100** (Round 1), **77/100** (Round 2) and **65/100** (final decision task). **These used different rubrics**, so their simple/weighted average is *not* a formal comparable score. The previously mentioned **~72/100** is only a descriptive estimate; **do not** use it as a pass/fail grade under the V2 75/100 gate.
- Source data are *reasoning answers and illustrative scenarios*, not evidence of measured system quality.

## What was actually tested

| Round | Task | Previously communicated provisional score | What this supports |
|---|---|---:|---|
| 1 | Diagnose relevant retrieval + wrong generation, lexical/SKU retrieval weaknesses and P95 latency | 68/100 | Architecture knowledge, initial bottleneck hypotheses |
| 2 | Design three tests for a 7B model with gold evidence among 5 chunks | 77/100 | Controlled-test thinking, distractor/position sensitivity, decoding and prompt hypotheses |
| Final | Decide whether 7B should be replaced using hypothetical gold-only 95%, unrelated 90%, plausible-distractor 62% | 65/100 | Evidence discipline and model-selection decision reasoning |

The final 95/90/62 percentages were **hypothetical teaching data**, not user measurements.

## Demonstrated strengths (reasoning evidence)

1. **Pipeline decomposition:** understands retrieval/context/generation as distinct stages and recognizes generator-side issues even when relevant documents are retrieved.
2. **Dense vs lexical retrieval:** correctly identifies a risk for IDs, SKUs, names and internal terms; considers sparse/hybrid retrieval and fusion. Distinguishes candidate matching from semantic matching.
3. **Failure-mode hypotheses:** plausible distractors, positional bias / lost-in-the-middle, model capacity, prompts, sampling stability, context order.
4. **Experiment instincts:** proposes explicit gold vs unrelated vs plausible distractor comparisons and sweeps evidence location through Top-5; asks for unstated experimental assumptions rather than accepting unsupported premises.
5. **Breadth of inference awareness:** names KV caching, GQA/MQA, PagedAttention, batching and GPU-side optimizations, plus cloud API quotas.
6. **Critical skepticism:** rejects an unsupported jump from an error rate to '7B reasoning is weak; scale up' and questions decoding determinism.

These observations describe **what was written in answers**; they do not independently establish that these techniques were implemented or measured.

## Main gaps / accuracy corrections

1. **Evidence relevance ≠ sufficiency.** A relevant retrieved chunk is not necessarily sufficient to answer. Confirm that the full, uncontradicted evidence reaches the actual model prompt before attributing error solely to the LLM.
2. **One-factor-at-a-time and confounders.** Hold constant model, prompts, questions, gold evidence, chunk positions/lengths when relevant, decoding configuration, judge, and hardware/runtime; distinguish a gold-only baseline (shorter context) from length-matched controlled comparisons.
3. **Lost-in-the-middle:** positional sensitivity is not simply a consequence of 'context too small'; measure token offsets/position effects while controlling distractor identity.
4. **Temperature 0:** often produces more stable output but does not guarantee identical outputs in every engine/batching/numerical condition. Crucially, **reproducibility and answer correctness are separate metrics**; nondeterminism is not proven to explain a 28-point accuracy gap.
5. **RRF assumptions:** no hybrid retrieval/RRF was specified in Round 1, so confirm the actual pipeline before tuning fusion. RRF fuses **rankings**; weighted RRF depends on the implementation.
6. **P95 bottleneck:** avoid asserting search over 1M docs always takes 100–200 ms or that PostgreSQL with 10M docs is necessarily unsuitable. Instrument stage latency, queue time, TTFT/TPOT, token counts, rate-limit errors, retries, concurrency and GPU metrics before selecting optimizations.
7. **Evaluation:** add answer correctness/faithfulness/citation support, Recall@K/MRR/NDCG per query type, repeated-run consistency, paired evaluation and confidence/uncertainty analysis.
8. **Answer leakage:** the evaluation model should receive **gold evidence**, not the literal **gold answer**, when testing grounded QA.
9. **Inspecting a `reasoning` JSON field** may help inspect supplied explanations, but not every model/API exposes such a field, and an explanation is not guaranteed to be a faithful record of underlying computation.
10. **Model replacement:** diagnose relevant failure modes and directly A/B benchmark 7B against a candidate model on **identical paired inputs**, with quality, latency and cost success thresholds. Poor-looking reasoning output alone is not proof that a bigger model is the right solution.

## Practical learning prescription (not an automatic PASS)

**Do not restart the entire RAG syllabus.** Prioritize:

- Targeted **RAG evaluation/experimentation**: paired datasets and hypothesis-driven tests, stage-specific diagnosis, uncertainty/stratification, faithfulness and citations.
- **Production observability/performance diagnosis**: trace separate retrieval/reranking/context/LLM stages, analyze queue/TTFT/TPOT, baseline latency and error budgets.
- **Model choice engineering judgment**: quality gain vs latency/cost, explicit go/no-go thresholds, model vs retrieval changes.
- **Implementation challenge later**: build a small test harness for gold-only, length-matched unrelated, plausible distractors and 5 position conditions; write tests, capture real output/metrics and make a documented selection decision.

Keep the [original module](../../knowledge/03-generative-ai-and-llm-engineering/11-embeddings-search-and-retrieval-augmented-generation/README.md) at **mastery: unassessed**, and any [Production RAG project](../../projects/02-production-rag/README.md) at **scaffold/not completed** until independently verified evidence exists.

## Next diagnostic

Move to **LLM Fundamentals**, not more introductory RAG definitions. Check encoder/decoder architectures, training vs inference, prefill vs decode, GQA & KV cache, LoRA/fine-tuning, tokenization and controlled model choices. First use an open-ended L2 engineering scenario, then target follow-ups based on weak areas; later require hands-on L3 separately. See [next diagnostic](../LLM_DIAGNOSTIC_PLAN.md).

## Assessment integrity

The new V2 standard (4 × 25, PASS >=75 with each category >=12) was **not executed in full** during these conversational rounds. Do not convert these provisional scores into a certified score or mark full RAG L2/L3 as passed.
