# Business Case: Etch-A-Sketch

## Metadata
| Key | Value |
| --- | --- |
| ID | BC-001 |
| CrossReference | [SA-001] |
| Language | en |
| Domain | it |

## Version History
| Date | Status | Author | Reviewer | Change | Commit |
| --- | --- | --- | --- | --- | --- |
| 2026-10-08 | Accepted | Jens Tirsvad Nielsen | S01 | Initial version | [5f9d016] |

## Executive Summary

Etch-A-Sketch is the Day 19 assignment of Udemy's *100 Days of Code: The Complete Python Pro Bootcamp*. The project delivers a small Python application in which the user steers a turtle on screen with the keyboard: W moves forward, S moves backward, A turns left, D turns right and C clears the drawing and returns the turtle to the centre. The result is published as a public repository that other course participants can set up, run, test and compare with their own solutions. The effort is small, the application has no runtime dependencies, and the delivery is planned in three gateways, each closed by one reviewed pull request. The recommendation is to proceed.

## Methodological and Standards Foundation

- **Framework:** the project follows the software quality assurance (SQA) and quality control (QC) framework mounted at `framework/`. The artifact chain (Business Case, Stakeholder Analysis, Project Plan, milestones, tasks, code) follows Larman's *Applying UML and Patterns*; each step is reviewed against the QC checklist of its type before the next step starts.
- **Quality model:** every QC criterion is tagged with a characteristic of ISO/IEC 25010:2023, the international product quality standard.
- **Stakeholder method:** power/interest grid, with concerns mapped to FURPS+ (functionality, usability, reliability, performance, supportability, plus design, implementation, interface and physical constraints; see the Stakeholder Analysis).
- **Code standards:** Python Enhancement Proposals (PEP) 8 (style), 257 (docstrings) and 484 (type hints); source comments use Doxygen commands; code is reviewed against `QC-PY-001` before each pull request.
- **Delivery:** one branch and one pull request per gateway; each pull request closes the issues it completes.

## Problem Statement

- The lecture teaches event listeners only by building something with them. The starter code binds one key (space) to one function and leaves the rest of the assignment open.
- Course participants share and compare solutions, but a bare script does not tell a reader which Python version it needs, how to set up an isolated environment, how to run it or how to check that it works.
- A solution without tests and without documented structure is hard to verify and hard to reuse in the later exercises of the course.

## Business Opportunity

A complete but small solution turns one lecture exercise into a reference that is easy to run and easy to compare. The same repository layout (`src/`, `tests/`, `docs/`, `pyproject.toml`, local `.venv`, tests, source documentation) can be reused for the remaining exercises of the course, and the public repository shows S01's progress to anyone browsing for ideas.

## Objectives

| # | Objective |
| --- | --- |
| O1 | The application moves the turtle with the W and S keys, turns it with the A and D keys, and clears the drawing and returns the turtle to the centre with the C key. |
| O2 | The code keeps the assignment's function names `move_forwards`, `move_backwards`, `turn_left` and `turn_right`, plus `clear` for the reset key. Each takes no arguments, because the `onkey` method accepts only functions without arguments. |
| O3 | The README explains, for Windows PowerShell, Linux Debian and macOS, how to create and use a local `.venv`, upgrade pip, run the application and run the tests. |
| O4 | Automated pytest tests cover the behaviour of every control function and run without opening a window. |
| O5 | The public repository is presentable: it has a description, topics and a README, and it needs no runtime dependencies. |
| O6 | The source has Doxygen comments and a `Doxyfile`, and the source documentation builds without warnings. |
| O7 | The delivery is traceable: each gateway is one branch and one pull request that closes the issues it completes. |

## Scope

### In Scope

- The application under `src/`: the five control functions, the key bindings and the program entry point.
- `constants.py` for every constant (step length, turn angle, key names).
- pytest tests under `tests/`.
- `pyproject.toml` for project configuration (Python 3.13 or newer, no runtime dependencies).
- A Python `.gitignore`, a `Doxyfile` and Doxygen comments in the source.
- `README.md` using S01's template, including how to create and use a local `.venv` and run `python -m pip install --upgrade pip`.
- A continuous integration workflow definition that runs the checks and the tests.
- The planning documents under `docs/` and the milestones and issues on the git host.
- Repository description and topics on the git host.

### Out of Scope

- The content of the next lesson (object state, several instances of the same object).
- Extra features such as colours, pen size, undo, saving drawings, mouse control or sound.
- Publishing a package to the Python Package Index (PyPI), hosting the generated source documentation online, or packaging as an executable.
- Automated tests of the graphical window itself; the window is checked by hand.
- Reading, importing or testing the `.env` file; it holds personal tokens for S01's own use and is not part of the project.

## Expected Benefits

### Tangible Benefits

- A running application that meets the lecture's behaviour (five keys, five functions).
- A pytest suite that checks every control function without a window.
- Set-up and run instructions for three platforms, so a reader can reproduce the result.
- Generated source documentation from the Doxygen comments.
- A repository with zero runtime dependencies.

### Intangible Benefits

- A working understanding of event listeners and of the turtle graphics methods `forward`, `backward`, `setheading`, `clear` and `home`.
- A reusable repository skeleton for the next exercises of the course.
- Practice in planning, reviewing and delivering work in small, traceable steps.
- A clearer exchange with fellow course participants and with visitors of the repository.

## Strategic Alignment

S01's organisation on the git host exists to document progress and practice while learning Python through the course. This project adds one more exercise to that record, and it does so with the same tooling and review discipline that the later exercises will use.

## Success Criteria

| # | Criterion | Target | Measure |
| --- | --- | --- | --- |
| 1 | Keyboard controls | 5 of 5 keys (W, S, A, D, C) bound to their functions | A pytest test that reads the registered key bindings |
| 2 | Function behaviour | At least 1 passing test for each of the 5 control functions | pytest report |
| 3 | Test run on a fresh environment | `pytest` exits with code 0 and 0 failures in a new `.venv` on Windows PowerShell | Command output recorded in the code review |
| 4 | Runtime dependencies | 0 packages in `[project] dependencies` | Reading `pyproject.toml` |
| 5 | Python version | `requires-python` is `>=3.13` | Reading `pyproject.toml` |
| 6 | README completeness | Every heading of S01's template present, in order, with 3 platform sub-sections | Review of `README.md` against the template |
| 7 | Source documentation | `doxygen Doxyfile` ends with 0 warnings; every public function has a Doxygen comment | Doxygen output and review |
| 8 | Code quality | `ruff check` and `ruff format --check` exit with code 0; all Mandatory criteria of `QC-PY-001` are `Pass`; review record `Go` | Command output and review record |
| 9 | Repository presentation | A non-empty description and at least 5 topics on the git host | Git host repository page |
| 10 | Delivery traceability | 3 of 3 gateways closed by a pull request with one `Closes #N` line per completed issue; 0 synced issues left open after the merges | Git host issue list |
| 11 | Secrets | 0 tracked files contain a token; `.env` is listed in `.gitignore` | `git ls-files` and `.gitignore` check |

## Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Tk support (`tkinter`, the graphical toolkit behind turtle graphics) is missing on a reader's machine (common on Debian and with some macOS Python builds), so `turtle` cannot start | A reader cannot run the application | The README names the extra package for each platform and tells the reader how to check `tkinter` |
| A continuous integration runner has no display, so a test that opens a window fails | The pipeline is red for the wrong reason | Tests use a test double instead of a real turtle and screen; only the manual run opens a window |
| The Python 3.13 requirement is not met on a reader's machine | The application or tests fail with a confusing error | `requires-python` stops the install with a clear message; the README shows how to check the version |
| The planning framework costs more effort than a 40-line application justifies | The schedule slips and the exercise loses momentum | Documents stay short, there are 3 gateways only, and each gateway has one review |
| A personal token from `.env` reaches the repository | The token is exposed on a public repository | `.env` is listed in `.gitignore`; no project file reads it; success criterion 11 is checked at each review |
| The git host has no continuous integration runner | The workflow definition cannot be proven on the host | The same commands are run locally and recorded in the review; the open point is kept in the Project Plan |
| Instructions for Linux Debian and macOS are not tested by S01 | The instructions contain an error that nobody sees | The README states which platform was verified; the continuous integration workflow runs on Linux |

## Assumptions

- S01 is available for the whole schedule (one week from 2026-10-08).
- "Python greater than 3.13" means Python 3.13 or newer (`>=3.13`); S01's installed version is 3.13.14.
- The step length and the turn angle are 10 (units and degrees), as in the lecture and the starter code.
- The function for the reset key is named `clear`; the brief does not list its name.
- The standard Python installation includes Tk, except where the README says otherwise.
- Readers who only want to build the source documentation install Doxygen themselves; it is not a Python package.

## Constraints

- Python 3.13 or newer, with a local virtual environment (`venv`) in `.venv`.
- pytest for tests; `constants.py` for constants; `pyproject.toml` for project configuration.
- Folder structure `src/`, `tests/` and `docs/`.
- No runtime dependencies unless they are needed.
- Doxygen comments in the source and a `Doxyfile`.
- No commit, push or pull request is made unless S01 asks for it.
- Nothing is written under `src/` or `tests/` until the milestone that contains the task is accepted and reviewed `Go` (plan-first gate).
- The repository lives on S01's git host; a reviewer, not the author, merges each pull request.

## Cost–Benefit Assessment

The assessment is qualitative on purpose: this is a personal learning project with no revenue and no budget, so a monetary return on investment would be invented. The value is learning and sharing, set against a small amount of S01's time.

| Costs | Benefits |
| --- | --- |
| About 6 to 8 hours of S01's time over one week for planning, set-up, code, tests and reviews (estimate to be confirmed) | A tested, documented and runnable Etch-A-Sketch application |
| No licence or hosting cost: Python, pytest, ruff, mypy and Doxygen are free and the repository is on the existing git host | Reproducible set-up on three platforms for S02 and S03 |
| Review and document overhead compared with the size of the application | A repository skeleton and a delivery routine for the next exercises |

## Stakeholders

The IDs are those of the Stakeholder Analysis [SA-001].

| Stakeholder ID (SA) | Interest in this project |
| --- | --- |
| S01 | The learning outcome (event listeners) and a small, reviewed and traceable delivery. |
| S02 | Wants readable, runnable code with the assignment's function names and clear run instructions, to compare with their own solution. |
| S03 | Wants a clear repository description, topics and README, and no runtime dependencies, to browse for ideas. |

## Recommendation

Proceed — the effort is small, the risks have mitigations, and the result serves S01's learning goal and the needs of S02 and S03.

---

[SA-001]: ./stakeholder-analysis.md
[5f9d016]: https://git.tirsystem.com/Tirsvad-Udemy-100-days-of-code/019-etch-a-sketch-up/commit/5f9d01636b37ac71e4d3d35374864a091c7d6f10
