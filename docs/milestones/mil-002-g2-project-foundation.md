# G2 Project foundation

## Metadata
| Key | Value |
| --- | --- |
| ID | MIL-002 |
| CrossReference | [BC-001] |
| Language | en |
| Domain | it |

## Version History
| Date | Status | Author | Reviewer | Change | Commit |
| --- | --- | --- | --- | --- | --- |
| 2026-10-08 | Accepted | Jens Tirsvad Nielsen | S01 | Initial version | [5f9d016] |

---

## Purpose

This gateway decides whether the repository's tooling is in place, so that code can be written, checked and run in the same way on every platform: project configuration, a Python `.gitignore`, the Doxygen set-up, the README, the continuous integration workflow and a local `.venv` that has been verified from scratch.

## Deliverable

`pyproject.toml`, `.gitignore`, `Doxyfile`, `README.md` with every section of S01's template, the continuous integration workflow `.github/workflows/ci.yml`, the package skeleton `src/etch_a_sketch/` with a smoke test under `tests/`, and the record of a from-scratch set-up in Windows PowerShell. The work is delivered in one pull request from the branch `g2-project-foundation`.

## Go / No-Go Criteria

| # | Criterion (objectively checkable) | Go | No-Go |
| --- | --- | --- | --- |
| 1 | The set-up commands of the README work in order on a new `.venv` in Windows PowerShell | `python -m venv .venv`, activation, `python -m pip install --upgrade pip` and `python -m pip install -e ".[dev]"` all exit with code 0 | Any command fails or the README is missing a step |
| 2 | The tests run | `pytest` exits with code 0 with at least 1 test collected | Exit code is not 0, or no test is collected |
| 3 | The code is formatted and linted | `ruff check .` and `ruff format --check .` exit with code 0 | Either command exits with a non-zero code |
| 4 | The project configuration is as required | `requires-python` is `>=3.13` and the runtime dependency list is empty | Another version range, or any runtime dependency |
| 5 | Local files stay out of the repository | `git check-ignore` reports `.venv/`, `.env`, `__pycache__/` and `docs/doxygen/` as ignored | Any of the four paths is not ignored |
| 6 | The source documentation builds | `doxygen Doxyfile` ends with 0 warnings | One or more warnings |
| 7 | The README follows S01's template | Every template heading is present, in order, with the three platform sub-sections | A heading is missing or out of order |
| 8 | No token reaches the repository | A search of the tracked files for the values in `.env` finds nothing | Any match |
| 9 | The pull request closes the issues of this gateway | The description has one `Closes #N` line for each completed issue | A completed issue is not named |

## Dependencies

| Depends on | Reason |
| --- | --- |
| MIL-001 | The plan-first gate allows files under `src/` and `tests/` only after the baseline is accepted with a Go review |

## Traceability

| Business Case objective / KPI / user story | Reference |
| --- | --- |
| O3 Set-up and run instructions for three platforms | [BC-001] Objectives; success criteria 3 and 6 |
| O4 Tests that run without a window | [BC-001] Objectives; success criterion 3 |
| O5 Presentable repository, no runtime dependencies | [BC-001] Objectives; success criteria 4, 5 and 11 |
| O6 Doxygen comments and `Doxyfile` | [BC-001] Objectives; success criterion 7 |
| O7 Traceable delivery | [BC-001] Objectives; success criterion 10 |

## Ownership

| Role | Stakeholder ID (SA) |
| --- | --- |
| Owner | S01 |
| Approving reviewer | S01 |

## Target Date

2026-10-11 — three days after the start on 2026-10-08, inside the one-week schedule of [BC-001] (Assumptions).

## Tasks

| # | Task | Summary | Needs its own Use Case/User Story? | Reference |
| --- | --- | --- | --- | --- |
| 1 | Add the Python .gitignore | Add a standard Python `.gitignore` plus `.venv/`, `.env`, the Doxygen output folder `docs/doxygen/` and the tool caches (pytest, ruff, mypy). `.env` holds S01's personal tokens and must never be tracked; no project file reads it. | No | BC-001 success criterion 11 |
| 2 | Add pyproject.toml | Configure the project in `pyproject.toml`: Python `>=3.13`, a `src` layout, an empty runtime dependency list, an optional `dev` group with pytest, ruff and mypy, and the settings of those tools. S03 sees no runtime dependencies and S02 installs with one command. | No | BC-001 success criteria 4 and 5 |
| 3 | Create the package and test skeleton | Create `src/etch_a_sketch/__init__.py` with a Doxygen file comment, and a smoke test under `tests/` that proves the editable install can be imported. This gives `pytest` something to run before the application exists. | No | |
| 4 | Add the Doxyfile | Add a `Doxyfile` for the Python source (input `src` and the README, HTML only, output in `docs/doxygen/`) and check that the build ends with no warnings. The README says that Doxygen is a system tool, not a Python package. | No | BC-001 success criterion 7 |
| 5 | Write the README | Replace the placeholder README with S01's template: requirements, set-up for Windows PowerShell, Linux Debian and macOS (create and use a local `.venv`, upgrade pip, install, and the Tk package where it is missing), run, tests, continuous integration, source documentation, project layout and license (GNU Affero General Public License 3.0). | No | BC-001 success criterion 6 |
| 6 | Add the continuous integration workflow | Add `.github/workflows/ci.yml`, which Gitea Actions and GitHub Actions both read. It checks out the code, installs Python 3.13 and `.[dev]`, then runs ruff, mypy and pytest on Linux. No display is needed because the tests do not open a window. | No | BC-001 success criterion 8 |
| 7 | Verify the set-up from scratch | Delete `.venv`, follow the README commands in Windows PowerShell in order, run the checks of the Go/No-Go criteria and record the output in the review. The Debian and macOS commands are not run by S01, and the README says which platform was verified. | No | |

---

[BC-001]: ../business-case.md
[5f9d016]: https://git.tirsystem.com/Tirsvad-Udemy-100-days-of-code/019-etch-a-sketch-up/commit/5f9d01636b37ac71e4d3d35374864a091c7d6f10
