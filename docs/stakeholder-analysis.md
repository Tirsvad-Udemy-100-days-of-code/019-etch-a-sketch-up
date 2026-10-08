# Stakeholder Analysis: Etch-A-Sketch

## Metadata
| Key | Value |
| --- | --- |
| ID | SA-001 |
| CrossReference | [BC-001] |
| Language | en |
| Domain | it |

## Version History
| Date | Status | Author | Reviewer | Change | Commit |
| --- | --- | --- | --- | --- | --- |
| 2026-10-08 | Accepted | Jens Tirsvad Nielsen | S01 | Initial version | [5f9d016] |

---

## Purpose

This analysis identifies who has influence over, or interest in, the Etch-A-Sketch project, and what each of them needs from it. It gives every stakeholder a stable ID (`S01`, `S02`, `S03`) that the Business Case [BC-001], the Project Plan, the milestones and the review records use for ownership, review assignment and traceability. The method is a power/interest grid, with each concern written in business language and mapped to a FURPS+ attribute (functionality, usability, reliability, performance, supportability, plus design, implementation, interface and physical constraints).

## Stakeholder Summary Table

| ID | Name | Role/Title | Organization | Power Level | Interest Level | Quadrant | Primary Concern (Business Language) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| S01 | Jens Tirsvad Nielsen | Course participant; Product Owner, developer and reviewer | Self (personal learning project) | HIGH | HIGH | Manage Closely | Learn event listeners by delivering the assignment, and keep the delivery small, reviewed and traceable. |
| S02 | Udemy course participants | Fellow learners who share code and compare solutions | Udemy course community | LOW | HIGH | Keep Informed | Readable, runnable code with the assignment's function names, and README instructions to run it. |
| S03 | GitHub viewers | Visitors who browse the repository for ideas | Public visitors of the repository | LOW | LOW | Monitor | A clear repository description, topics and README, and no runtime dependencies. |

## Power/Interest Classification Rationale

- **Manage Closely (S01):** S01 decides scope, writes the code, reviews it and accepts every gateway, so power is high. The result is S01's own learning outcome, so interest is high. S01 is engaged at every gateway.
- **Keep Informed (S02):** S02 cannot change scope or accept a gateway, so power is low. S02 uses the repository to compare solutions and needs it to run, so interest is high. S02 is served by the README and by the assignment's function names.
- **Monitor (S03):** S03 has no say in the project and no commitment to it, so power and interest are both low. S03 is served by the repository page (description, topics and README); no dedicated effort is needed beyond that.
- **Keep Satisfied:** no stakeholder is in this quadrant.

## Primary Concerns and FURPS+ Mapping

| ID | Concern | FURPS+ attribute |
| --- | --- | --- |
| S01 | The keys W, S, A, D and C steer, turn and clear as in the lecture | Functionality |
| S01 | Tests run without opening a window, and the code follows the Python conventions | Reliability |
| S01 | Delivery in small steps, each a branch and a pull request that closes its issues | + Implementation constraint |
| S02 | Readable code that uses the assignment's function names | Usability |
| S02 | The application starts after following the README on their platform | Supportability |
| S03 | A clear repository description, topics and README | Usability |
| S03 | No runtime dependencies to install | + Implementation constraint |

## Communication Requirements

| ID | Channel | Frequency | Deliverable | Phase / Milestone |
| --- | --- | --- | --- | --- |
| S01 | Working-tree review in the development session | At the end of every gateway | The documents or code of the gateway, with its review record | G1, G2, G3 |
| S01 | Pull request on the git host | One per gateway | Pull request with one `Closes #N` line per completed issue | G1, G2, G3 |
| S02 | `README.md` in the repository | Written at G2, completed at G3 | Set-up, run and test instructions for each platform | G2, G3 |
| S03 | Repository page (description, topics, README) | Set at G1, checked at G3 | Description, topics and README | G1, G3 |

## Conflicting Interests and Mitigations

| Conflict | Stakeholders | Mitigation |
| --- | --- | --- |
| S01 is author, developer and reviewer of every artifact, while the framework expects a reviewer who is not the author | S01 | Every review is made explicit with the quality control (QC) checklist and a review record with evidence; the pull request is a second look, and a reviewer other than the author merges it. The self-review is accepted for this single-person project and is stated in the Project Plan. |
| S02 wants the plain function names and short code of the lecture, while S01 wants typed, documented and testable code | S01, S02 | The assignment's names and the zero-argument signature are kept; type hints, Doxygen comments and test doubles are added without renaming anything. |
| S02 wants a short script to compare, while the project layout adds a package, `constants.py`, tests and configuration | S01, S02 | Keep few and short modules (`constants.py` and one module of control functions); the README section *Project layout* says what each file is for. |
| S03 wants a repository with no runtime dependencies, while S01 wants development tools (pytest, ruff, mypy) | S01, S03 | The tools are listed only in an optional `dev` group of `pyproject.toml`; the list of runtime dependencies stays empty. |

## Traceability Analysis

Actor mapping: S01 and S02 are the actors who draw with the keyboard when they run the application; S03 only reads the repository. No use case or user story is modelled for this project (the Project Plan records why).

### Business Goal Alignment

| Stakeholder | Concern | Business Case objective |
| --- | --- | --- |
| S01 | The keys steer, turn and clear as in the lecture | [BC-001] O1 |
| S01 | Tests run without a window; code follows the conventions | [BC-001] O4, O6 |
| S01 | Delivery in small, traceable steps | [BC-001] O7 |
| S02 | Readable code with the assignment's function names | [BC-001] O2 |
| S02 | The application starts after following the README | [BC-001] O3 |
| S03 | A clear repository description, topics and README | [BC-001] O5 |
| S03 | No runtime dependencies | [BC-001] O5 |

## Sign-Off

| Stakeholder ID | Decision | Date |
| --- | --- | --- |
| S01 | Pending review. S01 confirms the power and interest levels of S02 and S03, which S01 did not state in the brief. | |

---

[BC-001]: ./business-case.md
[5f9d016]: https://git.tirsystem.com/Tirsvad-Udemy-100-days-of-code/019-etch-a-sketch-up/commit/5f9d01636b37ac71e4d3d35374864a091c7d6f10
