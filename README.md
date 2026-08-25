# Medical Manuscript Pipeline

> **Core purpose:** Use nine-stage scientific control to prevent AI-patterned structure, stitched-together logic, audit-style prose, and generic wording, so the final paper reads as coherent, author-consistent work by a real medical investigator. Human-like writing here means a stable author voice built on correct science—not deliberate mistakes or promises to evade AI detection.

[中文说明](README.zh-CN.md) | English

A stage-gated lifecycle controller for genuinely human-like medical manuscript writing. It does not treat “de-AI” as a final synonym-replacement pass. It reduces AI traces upstream by controlling when evidence is frozen, when the argument is built, when prose is drafted, and when the author's own language habits are applied.


## Why this Skill exists

Medical manuscripts often fail for reasons that are not solved by another polishing pass:

- the sample or dataset version changes after drafting has started;
- primary, sensitivity, exploratory, and negative analyses are mixed together;
- public-data support is described as independent validation;
- association, co-expression, enrichment, or mRNA findings are promoted into causal or functional claims;
- references are collected before the claim structure is stable;
- limitations are repeated until the paper reads defensively;
- internal provenance and reconciliation language leaks into the manuscript;
- AI-style editing happens before the science is stable and hides substantive changes;
- a technically valid DOCX is mistaken for a submission-ready paper.

The pipeline addresses these problems by freezing upstream decisions before downstream writing and by reporting scientific, author, document, and submission states separately.

## Core design

### 1. Nine mandatory gates

| Gate | Purpose | Minimum output |
|---|---|---|
| 0. Research charter | Define the question, design, contribution, evidence layers, canonical sources, and non-goals | `RESEARCH_CHARTER.md` |
| 1. Source freeze | Resolve samples, identifiers, datasets, assay sources, inclusions, exclusions, and versions | source inventory and canonical mappings |
| 2. Analysis freeze | Lock the statistical unit, main analysis, covariates, multiplicity, sensitivity analyses, and final result source | frozen result tables and analysis roles |
| 3. Evidence freeze | Define what every dataset, experiment, figure, table, and citation can and cannot support | `EVIDENCE_CONTRACT.md` and claim–evidence map |
| 4. Framework and logic freeze | Build the whole-paper, section, paragraph, and sentence-level argument | `MANUSCRIPT_LOGIC_MAP.md` |
| 5. Scientific draft and regression | Draft from frozen evidence and recheck numbers, labels, statistics, figures, tables, and citations | scientifically stable manuscript |
| 6. Author voice and AI-style pass | Apply the author's stable language habits only after science is frozen | author-consistent clean draft |
| 7. Journal adaptation | Apply journal scope, structure, word limits, reference style, checklist, and supplement rules | journal-adapted package |
| 8. Document and submission validation | Render and inspect files; separately verify ethics, authorship, funding, declarations, and required forms | `FINAL_VALIDATION.md` and submission decision |

New evidence, corrected data, or a material scientific error reopens the earliest affected gate and every downstream gate. Formatting-only changes do not reopen scientific gates.

### 2. Three separate ledgers

The Skill does not hide different kinds of uncertainty in one generic checklist.

- **Evidence ledger — `EVIDENCE_CONTRACT.md`:** records the design, unit, direct finding, maximum supported claim, unsupported inferences, and manuscript role of each evidence layer.
- **Author-decision ledger — `AUTHOR_DECISIONS.md`:** records questions that require an author, clinician, statistician, institution, or corresponding author rather than an AI assumption.
- **Submission ledger — `SUBMISSION_READINESS.md`:** records journal and administrative requirements independently of scientific validity and document QA.

This separation prevents “analysis completed,” “manuscript polished,” and “ready to submit” from being treated as the same state.

### 3. Logic before connectors

The manuscript is tested at four levels:

1. **Whole paper:** problem → gap → design → findings → bounded interpretation → contribution → decisive next step.
2. **Section:** each section answers a distinct reader question and hands a valid conclusion to the next section.
3. **Paragraph:** each paragraph has one job, a valid reasoning path, and an ending claim that follows from its evidence.
4. **Sentence:** transition words label real relations; they do not manufacture contrast, causality, progression, or importance.

A useful diagnostic is to remove most connectors. If the argument becomes unclear, the order or reasoning needs repair before another “however,” “therefore,” or “moreover” is added.

### 4. Clinical Investigator Voice

The default reader-facing voice is a medically trained investigator explaining what was done, what was observed, how it fits the field, and what it means within the evidence boundary.

The default language rules are:

- prefer common, precise words;
- use stable terminology for the same group, outcome, assay, gene, protein, model, and analysis;
- keep one main idea per sentence;
- use concise syntax when a short sentence is sufficient;
- keep the whole-paper structure clear while allowing natural local variation;
- give a genuine unexpected finding room when it matters;
- concentrate limitations where they change interpretation;
- never introduce artificial mistakes, disorder, vagueness, or statistical ignorance to appear human.

The workstation-level `AUTHOR_STYLE_PROFILE.md` stores durable author preferences. Project-specific terminology remains in the project and should not silently rewrite the global profile.

### 5. Humanization after scientific freeze

AI-style cleanup is a late scientific-preservation step, not an early drafting shortcut. It may remove repetitive summaries, stock transitions, symmetrical paragraph templates, inflated novelty, rare synonyms, long noun stacks, and internal audit language. It must preserve:

- facts and sample sizes;
- numerical values, directions, effect estimates, uncertainty, P values, and units;
- labels, identifiers, and technical distinctions;
- citations and table/figure numbering;
- the evidence ceiling and conclusion strength.

The Skill does not claim that a manuscript will become “undetectable” as AI-written. Its goal is accurate, natural, author-consistent scientific prose.

## Writing frameworks

Frameworks are scaffolds, not paragraph generators.

### Introduction

Use an adaptable funnel: clinical/biological problem → insufficiency of existing evidence → specific factor or approach → exact gap → what the study did.

### Methods

Organize by evidence layer: design → participants/datasets → measurements/assays → outcomes and definitions → analysis → quality and sensitivity checks → ethics and availability.

### Results

Use an evidence staircase: study flow and sample description → primary finding → complementary evidence → robustness → negative or boundary findings → short factual summary.

### Discussion: adaptable James five-step method

1. State the main findings without replaying the Results.
2. Compare them with the most relevant prior evidence.
3. Explain the contribution and, when justified, a plausible testable interpretation.
4. Address unexpected, negative, or conflicting findings and alternatives.
5. Concentrate limitations, clinical/scientific meaning, and the most decisive next step.

These are five functions, not a mandatory five-paragraph template. They may be combined or expanded according to the study.

### Conclusion

Briefly state the main result, its boundary, the evidence level, and the validation that would most meaningfully change confidence or practice.

## Study-type branches

The lifecycle is shared, but reporting and evidence gates differ by design.

### Systematic review and meta-analysis

Adds protocol-led eligibility, reproducible searches, deduplication, screening adjudication, full-text reasons, extraction, risk of bias, heterogeneity, synthesis rules, PRISMA reconciliation, and update date. Narrative conclusions are not frozen before the included evidence and bias assessment are complete.

### Case report

Adds a clinical timeline, differential diagnosis, intervention, outcome, follow-up, privacy protection, consent, and CARE-style completeness. A single case is not used to claim frequency, efficacy, or population-level causality.

### Clinical trial

Adds registration, protocol and SAP versions, prespecified outcomes, allocation, masking, analysis population, deviations, harms, participant flow, recruitment dates, CONSORT reconciliation, and sponsor role. Prespecified, amended, post hoc, and exploratory analyses remain distinct.

### Public-data bioinformatics

Adds accession and release date, sample metadata, donor/subject unit, preprocessing and annotation versions, batch structure, contrasts, multiplicity, code/environment, dataset independence, and public-versus-local evidence roles. Co-expression, enrichment, and predicted networks are not treated as demonstrated mechanisms.

## Included files

```text
medical-manuscript-pipeline/
├── SKILL.md
├── README.md
├── README.zh-CN.md
├── agents/openai.yaml
├── references/
│   ├── core-workflow.md
│   ├── writing-frameworks.md
│   ├── logic-and-author-voice.md
│   ├── ai-style-and-audit-language.md
│   └── branches/
│       ├── systematic-review.md
│       ├── case-report.md
│       ├── clinical-trial.md
│       └── public-bioinformatics.md
└── assets/templates/
    ├── RESEARCH_CHARTER.md
    ├── EVIDENCE_CONTRACT.md
    ├── AUTHOR_DECISIONS.md
    ├── SUBMISSION_READINESS.md
    ├── MANUSCRIPT_LOGIC_MAP.md
    ├── AUTHOR_STYLE_PROFILE.md
    ├── FINAL_VALIDATION.md
    ├── CLAIM_EVIDENCE_MAP.csv
    └── CLAIM_INFERENCE_REGISTER.csv
```

## When to use it

Use this Skill for:

- an end-to-end medical manuscript project;
- a manuscript that has accumulated data, analysis, evidence, writing, and document versions;
- a stage-gate audit or manuscript rescue;
- whole-paper logic reconstruction;
- coordinated journal and submission preparation;
- a systematic review, case report, clinical trial, or public-bioinformatics paper that needs lifecycle control.

Do not use it for:

- a single paragraph edit;
- one DOI or citation lookup;
- a standalone statistical or omics analysis;
- generic humanization;
- one-off Word formatting;
- a read-only diagnosis that has not authorized manuscript revision.

The pipeline is the lifecycle controller. Phase-specific Skills still perform literature search, data analysis, manuscript drafting, evidence-bound revision, peer review, citation verification, humanization, figures, or document processing. It should not load every capability at once.

## Installation

Copy the repository folder to your Codex skills directory:

```text
Windows: C:\Users\<user>\.codex\skills\medical-manuscript-pipeline
macOS/Linux: ~/.codex/skills/medical-manuscript-pipeline
```

Start a new or reloaded Codex task so the Skill catalog is refreshed.

Example requests:

```text
Use $medical-manuscript-pipeline to audit the current gate of this clinical manuscript.

Manage this systematic-review manuscript with stage gates and the three ledgers.

Build the whole-paper logic map before drafting the Discussion.

Apply the James five-step Discussion framework after confirming the evidence ceiling.
```

## Validation

With the bundled Codex skill validator:

```powershell
python -X utf8 C:\Users\<user>\.codex\skills\.system\skill-creator\scripts\quick_validate.py .
```

Validation of the folder confirms structure and frontmatter. It does not replace scientific review, source verification, statistical review, reporting guidelines, document rendering, or author approval.

## Safety and scientific boundaries

- Raw data remain immutable.
- The Skill does not invent data, references, identifiers, ethics information, author decisions, or submission status.
- Patient-identifiable or confidential data must not be uploaded without explicit authorization and appropriate de-identification.
- Diagnosis does not authorize rewriting.
- Association is not causation; mRNA is not protein or function; public-data concordance is not automatically external validation.
- Document QA passed does not mean submission ready.
- Human authors remain responsible for scientific meaning and submission approval.

## License

MIT License. See [LICENSE](LICENSE).
