# Evaluation method

## Scope

The historical comparison used a shared set of 20 reviewed cases for each of three variants, yielding 60 recorded outputs. The task distribution per variant was:

| Task | Cases |
| --- | ---: |
| Course Q&A | 7 |
| Next-step guidance | 3 |
| Debugging | 4 |
| Question generation | 3 |
| Question explanations | 3 |

The retained run handoff records A-1.0, B-1.0 and C-1.3, a common model configuration and the same evaluation-data hash across the batch. Model-service labels in historical files identify that run; this case study does not recommend or verify a current model offering.

## Rubric

Each dimension was scored from 0 to 2, for a total of 8. The descriptions below summarize how the dimensions were applied in the review; they are not a verbatim reproduction of course instructions.

| Dimension | Review question | Illustrative failure |
| --- | --- | --- |
| Correctness | Does the output correctly address the requested concept or task? | A generated question contains a logical contradiction. |
| Grounding | Do the supplied sources support the specific claims and steps? | A citation exists, but the displayed evidence does not support a precise instruction. |
| Learning usefulness | Does the learner receive usable guidance, practice or explanation? | A generation request ends safely with no practice question. |
| Robustness | Does the response handle missing information, unsupported requests, schema and boundaries appropriately? | A refusal loses requested fields or uses the wrong response language. |

## Review procedure

1. Read the task, expected behavior and allowed evidence.
2. Inspect the final answer, status, citations and relevant execution trace.
3. Record dimension-level scores with a concrete reason for each deduction.
4. Distinguish answer errors, missing evidence, retrieval problems, task non-completion and boundary handling.
5. Avoid charging the same underlying evidence-display problem to multiple dimensions without a separate reason.
6. Preserve the original result. Record corrections or rescores as a distinct review snapshot.
7. Recommend changes and test them in a separate, explicitly versioned retest.

AI assistance supported trace inspection, scoring drafts and write-up preparation. This portfolio does not claim blinded review, multiple independent human raters or measured inter-rater agreement.

## Module decision rules in the retained snapshot

- Concept Q&A: at least 6 of 7 cases at full score; C-1.3 recorded 3 of 7.
- Operational guidance (next-step plus debugging): at least 6 of 7 at full score; C-1.3 recorded 3 of 7.
- Practice (generation plus explanation): at least 5 of 6 at full score; C-1.3 recorded 6 of 6.

These are the recorded evaluation rules for this snapshot. They are not universal acceptance criteria for learning products.

## Interpretation limits

- Twenty cases per variant form a small evaluation, not a general reliability estimate.
- Prompt structure, retrieval and application behavior differ across variants; the observed differences do not isolate a single intervention.
- Aggregate scores do not establish better learning outcomes or performance with real students.
- Returned output and valid structure are separate from correctness and task completion.
- The public application later received changes. This report does not evaluate those later commits.
- A later relaxed rescore also exists in the working materials. The published aggregate tables deliberately retain the earlier independent-review snapshot; scores from different rubrics are not combined.
