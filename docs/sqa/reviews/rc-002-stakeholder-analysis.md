# Review: Stakeholder Analysis SA-001

## Metadata
| Key | Value |
| --- | --- |
| ID | RC-002 |
| CrossReference | [SA-001], [QC-SA-001], [QC-LANG-001] |

## Version History
| Date | Status | Author | Reviewer | Change | Commit |
| --- | --- | --- | --- | --- | --- |
| 2026-10-08 | Accepted | Jens Tirsvad Nielsen | S01 | Initial version | [5f9d016] |

---

## Artifact Under Review

- Instance reviewed: [SA-001]
- Checklist used: [QC-SA-001] (`QC-SA-001`), and [QC-LANG-001] (`QC-LANG-001`) because the type is written in the PO language
- Scope: full review
- Language and domain: en / it (the Metadata rows of SA-001)
- Language reviewer: none (S01 reads the language and knows the domain)

## Checklist Results

| # | Criterion | Status | Evidence/Notes |
| --- | --- | --- | --- |
| 1 | Power/Interest grid is filled for every stakeholder, with no gaps or unclassified entries (Mandatory) | Pass | The Stakeholder Summary Table has 3 rows (S01, S02, S03), every cell filled, each with a quadrant. |
| 2 | Each stakeholder is assigned a unique, stable ID (e.g. S01-S11 style) reusable for RACI assignments in other artifacts (Mandatory) | Pass | S01 to S03 are unique and are the IDs used in [BC-001], the Project Plan, the milestones and the review records. |
| 3 | Roles and organizational context are defined with explicit Power and Interest levels, not just narrative description (Mandatory) | Pass | Role, organization, Power Level and Interest Level are explicit for each stakeholder; the rationale section explains each quadrant and agrees with the table. |
| 4 | Communication needs (channel, frequency, deliverable type) are mapped to project phases or milestones (Optional) | Pass | The Communication Requirements table gives channel, frequency and deliverable for S01, S02 and S03, tied to G1, G2 and G3. |
| 5 | Conflicting stakeholder interests are identified with documented mitigation or resolution strategies (Mandatory) | Pass | The Conflicting Interests table has 4 conflicts, each with stakeholders and a mitigation. |
| 6 | Stakeholder concerns are explicitly traced to Business Case objectives (Mandatory) | Pass | The Business Goal Alignment table traces 7 concerns to objectives O1 to O7 of [BC-001]. |
| 7 | Primary concerns are expressed in both business language and a recognized quality-attribute mapping (e.g. FURPS+) (Optional) | Pass | The Primary Concerns and FURPS+ Mapping table gives each concern in business language and a FURPS+ attribute. |
| 8 | Document is understandable and navigable by non-technical stakeholders reviewing their own entry (Optional) | Pass | The text is short and plain; each stakeholder can read their own row. One technical term (test double) appears in a conflict row for S01 and S02, who know it. |

## Language and Domain Results

| # | Criterion | Status | Evidence/Notes |
| --- | --- | --- | --- |
| 1 | The Metadata table has a `Language` row and a `Domain` row, and neither is a placeholder (Mandatory) | Pass | `Language` is `en` and `Domain` is `it` in the Metadata of SA-001; neither is a placeholder. |
| 2 | `Language` is a BCP 47 code and `Domain` is a value from the registry's domain list (Mandatory) | Pass | `en` is a BCP 47 code; `it` (Software and IT) is a row of the registry's domain list. |
| 3 | The content (prose and table cells) is written in the stated language (Mandatory) | Pass | All prose and table cells are English, the PO language (registry: `PO language` = `en`). |
| 4 | The register matches the one the registry gives for the artifact type (Mandatory) | Pass | Register is IT Professional English: concise, assumes a reader who knows software terms (FURPS+, pull request, test double) and still explains the project-specific ones. |
| 5 | Domain terms are the PO terms of the domain's dictionary, with no synonyms (Mandatory) | Pass | No Domain Dictionary exists (it is not part of this project; see PP-001 Open Issues), so no PO term has a synonym to replace. One word was kept for each concept: gateway or milestone for `MIL`, control function, key binding, pull request, course participants. Judged Pass rather than N-A because the process allows no N-A for criterion 5. |
| 6 | Metadata keys, section headings, IDs and statuses are in English (Mandatory) | Pass | Metadata keys, section headings, IDs and statuses are English; `check-languages.sh` and `sync-project.sh` read them without a finding. |
| 7 | No translated twin (`<name>.<language>.md`) exists beside the document (Mandatory) | Pass | `docs/` holds no translated twin (`*.en.md`, `*.da.md`). |
| 8 | A change of language or domain since the previous accepted version has a Version History row and was reviewed again (Mandatory) | N-A | First version; there is no earlier accepted version whose language could have changed. |
| 9 | A reviewer competent in the domain, and in the language, has confirmed that the domain terms are used correctly (Mandatory) | Pass | S01 reads English and works in the software and IT domain; S01 confirmed the document by accepting it in chat on 2026-10-08. Language reviewer: none. |
| 10 | Abbreviations are spelled out on first use, in the stated language (Optional) | Pass | FURPS+ and QC were expanded on first use during this review. IDs such as `S01` and `QC-BC-001` are defined by the framework. |

## Overall Verdict

Go — all Mandatory criteria of `QC-SA-001` and `QC-LANG-001` are Pass. The power and interest levels of S02 and S03 were proposed by the drafter and are accepted by S01 with this verdict. The reviewer is S01, who is also the author; this self-review is accepted in SA-001 (conflict 1) and PP-001 (Planning Assumptions). S01 gave the verdict by accepting the document in chat on 2026-10-08. The assistant that drafted the document transcribed the rows and evidence above for S01 and made the wording corrections named in the evidence; S01 owns the record.

## Action Items

| Action | Owner | Due |
| --- | --- | --- |
| None; every criterion is Pass or N-A | S01 | 2026-10-08 |

---

[SA-001]: ../../stakeholder-analysis.md
[QC-SA-001]: ../../../framework/qc/qc-stakeholder-analysis.md
[QC-LANG-001]: ../../../framework/qc/qc-language-domain.md
[5f9d016]: https://git.tirsystem.com/Tirsvad-Udemy-100-days-of-code/019-etch-a-sketch-up/commit/5f9d01636b37ac71e4d3d35374864a091c7d6f10
