# Core workflow and mandatory gates

## Operating principle

Freeze upstream facts before spending effort downstream. Deep internal checking is required, but internal control language is not the manuscript's voice.

## Gate 0: research charter

Required record: `RESEARCH_CHARTER.md`.

Freeze the study question, design, population or biological system, primary outcome or main signal, intended contribution, evidence layers, confirmatory versus exploratory status, analysis unit, target readers, exclusions, and stop conditions. Identify the canonical source for data, code, results, manuscript text, figures, and references.

Pass when the project has one defensible main line and competing project versions are resolved or explicitly separated.

## Gate 1: source freeze

Inventory source files and build canonical identifiers for participants, samples, datasets, assays, and analysis versions. Resolve label mappings, inclusion/exclusion, provenance conflicts, duplicated sources, and raw-versus-processed distinctions. Raw data remain immutable.

Pass when every result used for writing points to an identified source and version. The reconciliation record remains internal unless a scientific fact is needed in Methods.

## Gate 2: analysis freeze

Lock the statistical unit, primary analysis, covariates, multiple-testing rule, sensitivity analyses, exploratory branches, software/version, and final result tables. Record sample size, effect size, uncertainty, P values where relevant, missingness, and exclusions.

Use four analysis roles:

1. primary;
2. robustness or sensitivity;
3. boundary-defining or negative;
4. explored but not promoted.

Pass when tables, figures, and text will draw from the same frozen result set.

## Gate 3: evidence freeze

Complete `EVIDENCE_CONTRACT.md` and the claim-evidence map. State the maximum claim supported by each evidence layer. Separate direct evidence, indirect support, and hypotheses. Separate association from causation, expression from function, mRNA from protein, co-expression from regulation, and public-data support from local experimental evidence.

Pass when every central claim has a source and no conclusion exceeds its evidence ceiling.

## Gate 4: framework and logic freeze

Complete `MANUSCRIPT_LOGIC_MAP.md`. Define the whole-paper chain from problem to gap, design, findings, interpretation, boundary, and contribution. For each section and paragraph, define its job, inputs, conclusion, and link to the next unit.

Pass when the logic survives removal of most transition phrases. A transition word may clarify a relation but cannot substitute for one.

## Gate 5: scientific draft and regression

Draft from the frozen result set and evidence contract. Keep Methods reproducible but proportionate; present Results in evidence order; interpret rather than relist in Discussion. After revisions, regress numbers, denominators, labels, units, statistical direction, tables, figures, citations, and conclusion strength.

Pass when the manuscript is scientifically stable and author-only decisions are explicitly recorded rather than guessed.

## Gate 6: author voice and AI-style pass

Only now apply `AUTHOR_STYLE_PROFILE.md`, Clinical Investigator Voice, plain English, terminology consistency, audit-language removal, and AI-style review. Preserve all facts, numbers, citations, identifiers, and claim strength. Do not optimize for an AI-detector score or promise evasion.

Pass when the prose sounds like the same medically trained author throughout without becoming vague, decorative, or artificially irregular.

## Gate 7: journal adaptation

Apply journal scope, word limits, section structure, reference style, figure/table limits, reporting checklist, title page, declarations, and supplement rules. Do not distort the scientific story merely to imitate a journal's tone.

Pass when journal-specific requirements are mapped and scientific content remains unchanged unless the author approves a substantive revision.

## Gate 8: document and submission validation

Reopen or render the final files. Check headings, page flow, tables, figures, captions, cross-references, equations, special characters, references, tracked changes, hidden text, metadata when requested, and file integrity. Separately verify ethics, consent, authorship, affiliations, funding, conflicts, data/code availability, cover letter, checklists, and required forms.

Pass only when both the document and administrative submission records are complete. Otherwise report the exact open gate.

## Change control

- New evidence or corrected data: reopen the earliest affected gate and all downstream gates.
- New wording only: reopen Gates 5-8 as needed.
- Journal formatting only: reopen Gates 7-8.
- Author metadata only: update the author and submission ledgers; do not reopen science unless the decision changes the study claim.
