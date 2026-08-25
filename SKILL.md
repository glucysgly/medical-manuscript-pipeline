---
name: medical-manuscript-pipeline
description: Manage an end-to-end medical manuscript project with mandatory stage gates, separate evidence/author/submission ledgers, logic mapping, Clinical Investigator Voice, post-freeze humanization, and study-type branches. Use for a complete manuscript lifecycle, a multi-stage manuscript rescue, stage-gate audit, or submission-readiness workflow. Do not use for a single paragraph edit, one citation lookup, standalone analysis, generic humanization, or one-off document formatting.
---

# Medical Manuscript Pipeline

Treat the manuscript as a clinical research argument, not an audit report. Keep the backend traceable and the reader-facing prose direct, medically grounded, and proportionate to the evidence.

## Start

1. Confirm the study type, intended contribution, current project stage, canonical manuscript source, data/results source, target journal if known, and author-only decisions still missing.
2. Copy only the needed templates from `assets/templates/` into the project. Do not overwrite populated project records. Prefer an existing project `AUTHOR_STYLE_PROFILE.md`, then the workstation's approved personal profile, then the bundled template.
3. Read `references/core-workflow.md` and open only the references needed for the current stage or study type.
4. Select one phase executor as the primary supporting capability. Do not load every writing, search, analysis, humanization, and document Skill at once.

## Mandatory order

Run the gates in order: charter, source freeze, analysis freeze, evidence freeze, framework and logic freeze, scientific draft/regression, author voice and AI-style pass, journal adaptation, document and submission validation.

Do not humanize prose before the scientific content is frozen. Reopen an upstream gate only for new evidence, corrected data, a material scientific error, or an author decision that changes the claim.

Maintain three separate records throughout:

- `EVIDENCE_CONTRACT.md`: what each dataset, experiment, analysis, table, figure, and citation can support.
- `AUTHOR_DECISIONS.md`: choices that require an author, clinician, statistician, or institution.
- `SUBMISSION_READINESS.md`: journal and administrative readiness independent of scientific validity.

Use `MANUSCRIPT_LOGIC_MAP.md` before full drafting. A connector may label a real relation but may not manufacture one. Check both the whole-paper argument and the paragraph-level chain.

## Writing defaults

Use Clinical Investigator Voice: a medically trained researcher explaining what was done, what was observed, how it fits the field, and what it means within the study boundary. Prefer common words, stable terms, one main idea per sentence, and concise syntax. Preserve the author's recurring habits in `AUTHOR_STYLE_PROFILE.md`.

Keep the overall structure clear while allowing local variation in paragraph length and emphasis. A genuine unexpected finding may interrupt the expected narrative when its relevance is explained. Never manufacture disorder, errors, uncertainty, or statistical naivety to appear human.

Internal provenance, reconciliation, audit, manifest, and pipeline language stays in working records unless readers need the underlying scientific fact. Read `references/logic-and-author-voice.md` and `references/ai-style-and-audit-language.md` before the style stage.

## Section and study-type routing

For section frameworks, including the adaptable James five-step Discussion, read `references/writing-frameworks.md`.

Read exactly one applicable branch when possible:

- `references/branches/systematic-review.md`
- `references/branches/case-report.md`
- `references/branches/clinical-trial.md`
- `references/branches/public-bioinformatics.md`

Mixed studies may use more than one branch, but the evidence contract must keep their evidence roles separate.

## Completion

Report scientific, citation, logic, style, document-QA, author-input, and submission states separately. `document QA passed` never means `submission ready`. Do not claim completion while an upstream gate is open or a required author/institutional item is unresolved.
