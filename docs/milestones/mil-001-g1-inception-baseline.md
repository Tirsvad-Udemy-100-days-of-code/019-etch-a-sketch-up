# G1 Inception baseline

## Metadata
| Key | Value |
| --- | --- |
| ID | MIL-001 |
| CrossReference | [BC-001] |
| Language | en |
| Domain | it |

## Version History
| Date | Status | Author | Reviewer | Change | Commit |
| --- | --- | --- | --- | --- | --- |
| 2026-10-08 | Accepted | Jens Tirsvad Nielsen | S01 | Initial version | [5f9d016] |

---

## Purpose

This gateway decides whether the project may leave planning: the Business Case, the Stakeholder Analysis, the Project Plan and the three milestones are written, reviewed and accepted, and the work is broken into issues on the git host. Only after a Go may any file be written under `src/` or `tests/`.

## Deliverable

`BC-001`, `SA-001`, `PP-001` and `MIL-001` to `MIL-003`, each accepted after review; the PO language and domain set in the artifact registry; the repository description and topics set on the git host; the milestones and their issues created on the git host; and one pull request from the branch `g1-inception-baseline`.

## Go / No-Go Criteria

| # | Criterion (objectively checkable) | Go | No-Go |
| --- | --- | --- | --- |
| 1 | `BC-001`, `SA-001`, `MIL-001`, `MIL-002` and `MIL-003` each have a review record with the verdict Go, and `PP-001` is accepted by S01 | All five review records say Go and the latest Version History row of all five documents and of `PP-001` is `Accepted` | Any verdict is Go-with-conditions or No-Go, or any latest row is `Proposed` |
| 2 | The artifact registry states the PO language and domain, and every PO-language document has `Language` and `Domain` rows | `PO language` is `en`, `PO domain` is `it`, no placeholder remains | A placeholder remains in the registry or in a document |
| 3 | The milestones and issues are on the git host | `sync-project.sh --apply` has created 3 milestones and one issue per task row, and a second run creates no duplicate | A task row has no issue, or a duplicate exists |
| 4 | The repository is presentable to S03 | The repository has a non-empty description and at least 5 topics | The description is empty or fewer than 5 topics are set |
| 5 | The pull request closes the issues of this gateway | The description has one `Closes #N` line for each completed issue | A completed issue is not named, or a line lists several issues |

## Dependencies

| Depends on | Reason |
| --- | --- |
| None | First gateway; it depends only on S01's brief |

## Traceability

| Business Case objective / KPI / user story | Reference |
| --- | --- |
| O5 Presentable public repository | [BC-001] Objectives; success criterion 9 |
| O7 Traceable delivery in gateways | [BC-001] Objectives; success criterion 10 |

## Ownership

| Role | Stakeholder ID (SA) |
| --- | --- |
| Owner | S01 |
| Approving reviewer | S01 |

## Target Date

2026-10-09 — one day after the start on 2026-10-08, inside the one-week schedule of [BC-001] (Assumptions).

## Tasks

| # | Task | Summary | Needs its own Use Case/User Story? | Reference |
| --- | --- | --- | --- | --- |
| 1 | Set the PO language and domain | Record the Product Owner (PO) language (en) and domain (it) in the Languages section of the artifact registry, and add the Project Plan and Milestone rows. Every document of a PO-language type states its language and domain from these settings, and planning may not start without them. | No | |
| 2 | Write the Business Case | Write BC-001: problem, objectives O1 to O7, scope, success criteria, risks and the recommendation. It is the base that the Stakeholder Analysis, the Project Plan and the milestones trace to. | No | BC-001 |
| 3 | Write the Stakeholder Analysis | Write SA-001 with S01 (Manage Closely), S02 and S03, their concerns mapped to FURPS+ and to the Business Case objectives. It gives every other document the stakeholder IDs used for ownership and review. | No | SA-001 |
| 4 | Write the Project Plan | Write PP-001: the three gateways with window, owner and deliverable, the timeline, the scope coverage, the plan risks and the open issues. | No | PP-001 |
| 5 | Write the milestone documents | Write MIL-001 to MIL-003 with Go/No-Go criteria and the task rows that become the issues on the git host. The tasks of MIL-002 and MIL-003 are the only code and configuration work allowed by the plan-first gate. | No | MIL-001, MIL-002, MIL-003 |
| 6 | Review the baseline documents | Review BC-001, SA-001 and MIL-001 to MIL-003 against QC-BC-001, QC-SA-001, QC-MIL-001 and QC-LANG-001, record a review record for each, and mark the document Accepted on a Go. S01 accepts PP-001, which has no checklist yet. No code may be written before this is done. | No | |
| 7 | Set the repository description and topics | Set the description and the topics of the repository on the git host, so that S03 sees what the project is at first glance. Done on 2026-10-08 through the git host's application programming interface (a description and 10 topics). | No | |

---

[BC-001]: ../business-case.md
[5f9d016]: https://git.tirsystem.com/Tirsvad-Udemy-100-days-of-code/019-etch-a-sketch-up/commit/5f9d01636b37ac71e4d3d35374864a091c7d6f10
