# Mastery & Evidence Standard — L2 → L3

**L2 (Conceptual)**: independently explain why/how an operation works, predict behavior on a new case, identify assumptions and limitations, and solve a representative reasoning problem without notes.

**L3 (Engineering practical)**: independently build, test, interpret, debug and reproduce an implementation; demonstrate meaningful trade-off and failure analysis.

**Important distinction:** The V2 phases **0–12** are a study sequence. L2/L3 describe actual demonstrated mastery and are not phase or job grades. **Core/Working/Awareness/Advanced** describe depth *required by the career path*, not current completion.

## Standard assessment rubric for NEW topic checkpoints

| Criteria | Max | Evidence |
|---|---:|---|
| Conceptual understanding | 25 | Why/how, mechanism, limitation |
| Math & tensor reasoning | 25 | dimensions, equations, correctness |
| Implementation | 25 | independently built/tested runnable solution |
| Debugging & engineering judgment | 25 | failure handling, trade-off, edge case |
| **Total** | **100** | |

**Pass:** >=75/100 **and** >=12/25 on *each* criterion. Failure in any criterion means a targeted re-assessment is required, even if the total exceeds 75. Use at least one unfamiliar variant; don't simply memorize a tutorial.

For purely conceptual L2 checks the assessor may use an L2-specific format; clearly label the criteria used and do **not** pretend it certified L3. For a real major project, pass/fail also requires explicit acceptance tests and artifacts.

## Preserve historical assessments

The 2026-10-21 Tensor Fundamentals for LLM **54/60 (90%) L2 PASS** followed a *previous four-criterion rubric*, not the new 25/25/25/25 engineering rubric. Preserve the original score, criteria and scope in [assessments.jsonl](../progress/assessments.jsonl). Do not silently recalculate this assessment or infer a new L3 result.

## Status and record keeping

- Default module-level mastery is **unassessed**, not L0.
- A passed subtopic does not mark an entire module complete.
- Never promote a mastery level because a notebook exists, a video was watched or an AI assistant explained the content.
- Record: original roadmap_id, V2 phase, topic/subscope, date, level, criteria, score, pass flag, concrete evidence, independent work status, assessor and next gaps.
- Only update assessment records after an actual assessment; keep reviewed learning notes distinct from drafted PR content.
- Learning loop: big picture → concepts/math → implementation → break/debug → evidence → review → continue or revisit.

See [phase checkpoint template](../templates/PHASE_CHECKPOINT_TEMPLATE.md) and [workflow](../docs/WORKFLOW.md).