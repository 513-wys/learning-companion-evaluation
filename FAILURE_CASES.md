# Selected failure cases

The following cases paraphrase retained **C-1.2 review records**, which precede the C-1.3 A/B/C comparison. They illustrate evaluation reasoning, not additional rows in the published aggregate table. Suggested product responses are recommendations, not claims that a fix was deployed.

## 1. Safe rejection, incomplete learning task

**Observation:** A request for a new practice question ended in a review-required state after the generated content failed a topic-alignment check. No final question or options reached the learner.

**Evaluation judgment:** The boundary check prevented a misleading question, but the requested practice task remained incomplete. The historical review scored usefulness 0 and robustness 2; those measure different outcomes.

**Product implication:** Track safe handling and successful task completion separately. A useful fallback could explain the limitation and suggest a supported topic.

## 2. A citation is present, but the evidence shown is incomplete

**Observation:** A multi-file spreadsheet workflow recommendation included reading, appending and clearing steps. The fuller source card supported the procedure, but the short evidence excerpt shown to the learner did not expose all those steps.

**Evaluation judgment:** Distinguish unsupported advice from incomplete evidence presentation. The review treated this as a grounding/display issue and avoided a second robustness deduction for the same reason.

**Product implication:** Check the evidence users actually see alongside the complete retrieved record. Present enough context for the recommendation to be verifiable.

## 3. Correct concept, inconsistent question example

**Observation:** A regex practice question described adding anchors to a five-digit pattern while its example string also contained a text prefix. Adding anchors alone would not make the stated pattern match that example.

**Evaluation judgment:** A broadly correct explanation of anchors did not rescue the inconsistent example. A generic human-review flag also did not demonstrate that the system identified this particular defect.

**Product implication:** Validate the concrete example, answer options and explanation together, including a minimal positive and negative input where possible.

## 4. Plausible debugging suggestions with weak causal support

**Observation:** For a spreadsheet retaining only the last record, the overwrite-versus-append diagnosis was directly relevant, while some additional suggestions were weakly connected to the actual symptom.

**Evaluation judgment:** A list of plausible checks is not automatically an evidence-backed diagnosis. The review retained a grounding deduction for the weakly supported alternatives.

**Product implication:** Rank hypotheses by symptom fit and source support, and attach a verification step to each proposed fix.

## 5. Refusal behavior needs its own regression checks

**Observation:** An earlier unsupported-topic response used the wrong language and lost requested metadata. A later C-1.2 response preserved the language, requested fields, unsupported status and empty evidence correctly.

**Evaluation judgment:** Refusal correctness includes presentation and field preservation, not just declining to answer. The later reviewed example received full marks, without implying general robustness on all unsupported requests.

**Product implication:** Include unsupported topics, missing information, response language and schema preservation in the test set.
