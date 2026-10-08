# G3 Etch-A-Sketch application

## Metadata
| Key | Value |
| --- | --- |
| ID | MIL-003 |
| CrossReference | [BC-001] |
| Language | en |
| Domain | it |

## Version History
| Date | Status | Author | Reviewer | Change | Commit |
| --- | --- | --- | --- | --- | --- |
| 2026-10-08 | Accepted | Jens Tirsvad Nielsen | S01 | Initial version | [5f9d016] |

---

## Purpose

This gateway decides whether the Etch-A-Sketch application meets the lecture's behaviour and the quality bar of the project: five keyboard controls with the assignment's function names, constants in `constants.py`, tests, Doxygen comments, README instructions that work, and a code review with the verdict Go.

## Deliverable

The application under `src/etch_a_sketch/` (`constants.py`, the control functions and the entry point `python -m etch_a_sketch`), the pytest tests under `tests/`, Doxygen comments in the source, the finished `README.md`, and a code review record against `QC-PY-001`. The work is delivered in one pull request from the branch `g3-etch-a-sketch-application`.

## Go / No-Go Criteria

| # | Criterion (objectively checkable) | Go | No-Go |
| --- | --- | --- | --- |
| 1 | The controls work in the running application | After `python -m etch_a_sketch`, W and S move the turtle 10 units forward and backward, A and D turn it 10 degrees left and right, C clears the drawing and returns the turtle to the centre with the pen down, and a click closes the window (checked by hand and recorded) | Any control behaves differently |
| 2 | The tests cover the controls | `pytest` exits with code 0; each of the 5 functions has at least 1 test; a test checks that 5 keys are bound | Exit code is not 0, or a function has no test |
| 3 | Constants are in `constants.py` | A review finds no step length, turn angle or key name outside `constants.py` | A literal is found elsewhere |
| 4 | The code is formatted, linted and typed | `ruff check .`, `ruff format --check .` and `mypy --strict src` exit with code 0 | Any command exits with a non-zero code |
| 5 | The source documentation builds | `doxygen Doxyfile` ends with 0 warnings and every public function has a Doxygen comment | A warning or an undocumented public function |
| 6 | The code review passes | The review record against `QC-PY-001` says Go and every Mandatory criterion is `Pass` | Go-with-conditions, No-Go or a failed Mandatory criterion |
| 7 | The README matches the code | The commands of *Run*, *Run the tests* and *Project layout* work as written in Windows PowerShell | A command or a file named in the README does not exist |
| 8 | The Business Case success criteria are checked | All 11 criteria of [BC-001] have a result in the review record | A criterion has no result |
| 9 | The pull request closes the issues of this gateway | The description has one `Closes #N` line for each completed issue | A completed issue is not named |

## Dependencies

| Depends on | Reason |
| --- | --- |
| MIL-002 | The configuration, the package skeleton, the Doxyfile and the README that this gateway completes |

## Traceability

| Business Case objective / KPI / user story | Reference |
| --- | --- |
| O1 Keyboard controls | [BC-001] Objectives; success criterion 1 |
| O2 The assignment's function names | [BC-001] Objectives; success criterion 2 |
| O4 Tests that run without a window | [BC-001] Objectives; success criteria 2 and 3 |
| O6 Doxygen comments | [BC-001] Objectives; success criterion 7 |
| O7 Traceable delivery | [BC-001] Objectives; success criteria 8 and 10 |

## Ownership

| Role | Stakeholder ID (SA) |
| --- | --- |
| Owner | S01 |
| Approving reviewer | S01 |

## Target Date

2026-10-14 — six days after the start on 2026-10-08, with one day of reserve before the end of the one-week schedule of [BC-001] (Assumptions).

## Tasks

| # | Task | Summary | Needs its own Use Case/User Story? | Reference |
| --- | --- | --- | --- | --- |
| 1 | Add constants.py | Create `src/etch_a_sketch/constants.py` with the step length (10), the turn angle (10) and the key names for forwards, backwards, left, right and clear. Every constant has a Doxygen comment, and no other file contains these values. | No | BC-001 O1 |
| 2 | Implement the control functions | Implement `move_forwards`, `move_backwards`, `turn_left`, `turn_right` and `clear` with the assignment's names. They take no arguments, because `onkey` accepts only functions without arguments. Forwards and backwards move by the step length, left adds the turn angle to the heading, right subtracts it, and clear erases the drawing and sends the turtle home without drawing a line. | No | BC-001 O1, O2 |
| 3 | Bind the keys and start the application | Add the entry point so that `python -m etch_a_sketch` creates the turtle and screen, starts listening, binds W, S, A, D and C (lower and upper case, so Caps Lock does not break the controls) and closes on a click. The window opens only when the application is started, never when the module is imported. | No | BC-001 O1 |
| 4 | Write the pytest tests | Test each control function against a test double for the turtle, so no window opens: movement, heading changes, and that clear leaves the pen down at the starting point. Test that five keys are bound and that the constants have the lecture's values. Name each test for the behaviour it checks. | No | BC-001 O4 |
| 5 | Add the Doxygen comments and build the source documentation | Add Doxygen comments to the package, the constants and the functions (what each does, its parameters and return value), then run `doxygen Doxyfile` and fix every warning. | No | BC-001 O6 |
| 6 | Review the code against QC-PY-001 | Run ruff, mypy and pytest, review the code against `QC-PY-001`, and record the result in a review record that also gives a result for each Business Case success criterion. The pull request is not opened before the verdict is Go. | No | BC-001 success criteria 1 to 11 |
| 7 | Finish the README and check the run | Fill *Run*, *Run the tests* and *Project layout* with the real commands and files, run the application by hand in Windows PowerShell and note the check. Confirm that the repository description and topics still match the finished project. | No | BC-001 O3, O5 |

---

[BC-001]: ../business-case.md
[5f9d016]: https://git.tirsystem.com/Tirsvad-Udemy-100-days-of-code/019-etch-a-sketch-up/commit/5f9d01636b37ac71e4d3d35374864a091c7d6f10
