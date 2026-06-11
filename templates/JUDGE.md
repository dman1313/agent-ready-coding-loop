# JUDGE — rubrics for subjective quality
<!-- One rubric per [JUDGE] criterion, written BEFORE building toward it and shown to the human at contract signing. Each loop iteration that touches a [JUDGE] criterion, the work is scored against its rubric with the freshest eyes available: (1) a different model, or (2) a fresh session/subagent given ONLY the rubric and the work — never the chat history — or (3) self-scoring as a harsh external reviewer, marked "self-scored" on the scoreboard. A passing score is provisional YES for the loop; the human still gives final sign-off at the end. -->

## Rubric for criterion [number]: "[criterion text]"

**Passing threshold:** [e.g., 24 of 30, with no line below 3]
**Latest score:** [score] — judged by [different model / fresh session / self-scored] on [date]

| # | What a YES looks like (concrete and observable) | Score 1–5 | Evidence |
|---|---|---|---|
| 1 | [e.g., Every section starts with what the teacher DOES, not theory] | | |
| 2 | [e.g., A step can be found in under 10 seconds by scanning headings] | | |
| 3 | [...] | | |

**Human feedback fed into this rubric:** [when the human's final check fails, what they said gets added as new rubric lines so the judge catches it next time]

---

## The judge prompt — paste this into the fresh session, with the rubric and the work attached

> You are a harsh, independent reviewer. You did not make this and you do not care about the effort behind it — only whether it meets the rubric. Score each rubric line 1–5. For every score, cite specific evidence from the work itself (quote it or name the page/screen). Do not average generously: if a line is between scores, take the lower one. Finish with: total score, pass/fail against the threshold, and the THREE most important things to fix, in order of impact.

## Code-review rubric (Group D fresh-eyes review — run before each checkpoint commit)

| # | What a YES looks like | Score 1–5 | Evidence |
|---|---|---|---|
| 1 | No bug a careful reader can spot in the changed code's logic | | |
| 2 | No security smell: no injection risk, no secrets, no unvalidated input handling user data | | |
| 3 | A new developer could understand each changed file's job in one minute | | |
| 4 | Errors are handled where they can occur, with plain-language messages | | |
| 5 | The change does only what its plan step says — no quiet extras | | |

**Passing threshold:** no line below 3.
