# UiPath Learning Companion — Evaluation Case Study

**Yushan Wu · AI application evaluation · Course project, September 2026**

This case study presents my evaluation work on a team-built generative AI learning assistant for UiPath coursework. The assistant supports concept Q&A, next-step guidance, debugging and practice questions.

**My responsibility was evaluation, evidence checking and failure analysis. The wider team developed the application; this repository is my evaluation portfolio, not a claim that I built the entire product.**

## My contributions

- Compared A/B/C prompt-system variants using a common **20-case evaluation set**, with **60 outputs** in the historical comparison batch.
- Reviewed outputs against four dimensions: **correctness, grounding, learning usefulness and robustness**.
- Checked whether cited course evidence supported the actual answer, not just whether a citation ID existed.
- Investigated ambiguous questions, unsupported claims, incomplete answers and misleading diagnostics; prioritized findings for team iteration.
- Used AI tools to assist trace inspection, scoring drafts and report preparation. Scores are rubric-based assessments, not independently adjudicated ground truth.

## Evaluation approach

```text
Task and expected behavior
        ↓
Same evaluation cases across A/B/C
        ↓
Inspect answer, evidence, status and execution trace
        ↓
Score four dimensions and document failure reasons
        ↓
Prioritize product issues and recommend a separate retest
```

The five task types were course Q&A, next-step guidance, debugging, question generation and explanations. Details: [evaluation method](EVALUATION_METHOD.md).

## Historical results snapshot

| Variant | Cases | Mean score / 8 | Full-score cases |
| --- | ---: | ---: | ---: |
| A-1.0 | 20 | 2.25 | 0 / 20 |
| B-1.0 | 20 | 3.95 | 1 / 20 |
| C-1.3 | 20 | 6.70 | 12 / 20 |

These values come from the retained September 2026 evaluation records. They are **not a new test of the latest public repository**, and A/B/C differ in more than prompt wording: the course-grounded variant also used retrieval and application checks. The comparison therefore does not isolate a single causal change.

**The main finding:** a higher average did not mean every module was ready. C-1.3 met the recorded practice-module threshold, while concept Q&A and operational guidance did not meet their respective thresholds. All 60 outputs were returned without interface errors; that is a run-completeness result, not a quality pass rate.

[Version comparison data](version_comparison.csv) · [Module results](module_results.csv)

## What the failure analysis showed

- A well-formed answer can still make claims unsupported by its cited evidence.
- A safe rejection can protect the user while failing to complete the requested learning task.
- A question can teach the right concept but use an internally inconsistent example.
- A correct workflow recommendation can still expose incomplete supporting evidence to the user.

See [selected failure cases](FAILURE_CASES.md) for the distinction between historical C-1.2 review examples and the later C-1.3 comparison batch.

## Team attribution and source project

- [Original team project](https://github.com/Tonya0719/UiPath-Learning-Companion)
- [Wang Chenyu's public version](https://github.com/jasonwang7562-hash/UiPath-Learning-Companion)
- [My contribution boundaries](CONTRIBUTIONS.md)

This repository contains my case-study write-up, summarized findings and aggregate tables. It does not redistribute the complete application or the course-material collection. The published summaries paraphrase the retained review records; raw prompts, model traces and scoring workbooks are not bundled here.

This learning-assistant evaluation is separate from the **UiPath GitHub-issue competitor-analysis workflow**, where my responsibility was Workflow 3 and Agent integration.

[My profile](https://github.com/513-wys) · [LinkedIn](https://www.linkedin.com/in/yushan-wu-208ab5444/)
