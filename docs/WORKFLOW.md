# Workflow — V2 Context-Driven, Evidence-First

1. **Choose next task from [ACTIVE_PATH](../progress/ACTIVE_PATH.md)** and [V2 learning path](../curriculum/LEARNING_PATH_V2.md), not blindly by alphabetical/original roadmap order.
2. **Resolve the source topic ID** using [PHASE_INDEX](../indexes/PHASE_INDEX.md) → [ROADMAP_INDEX](../indexes/ROADMAP_INDEX.md) → the existing knowledge topic. Keep all original IDs/folders stable.
3. For each concept, ask: **where in an LLM/AI system is this used, why, what are the shapes/assumptions, how to implement, what can fail?**
4. Make a small working lab or notebook. Use tests, baseline and failure cases. Avoid repetitive mathematics once the core point is demonstrably understood.
5. Review with the four-part 100-point rubric (>=75 and each criterion >=12), plus project acceptance tests. Keep L2 conceptual evidence separate from L3 independent build/debug evidence.
6. Record only **observed** results in [assessments.jsonl](../progress/assessments.jsonl). Never invent scores, practical completion or benchmarks. Keep deep-dive backlog for math that is not an immediate dependency.
7. **Work in a branch and PR.** Knowledge/career changes require learner review before merge. Never push directly to main absent explicit authorization.
8. Preserve historical artifacts and the original roadmap as archival reference. A scaffold README is not completed knowledge content.
9. Follow [notebook requirements](NOTEBOOKS.md); store safe, real outputs, hardware/version/seeds for benchmarks, and link the registry. Do not commit credentials or sensitive data.
10. Prefer current official technical docs for changing APIs, then validate locally; label unverified assumptions and tool/version constraints.

**Shortcut:** Big Picture → Why → Relevant Math → Build → Debug → Evaluate → Revisit.