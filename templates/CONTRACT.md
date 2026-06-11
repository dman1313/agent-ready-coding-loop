# CONTRACT — the definition of done
<!-- Signed success criteria. LOCKED after approval: the agent may never weaken, remove, or reinterpret a criterion to make it pass. Only the human amends, and every amendment is recorded below. -->
<!-- Tags: [AUTO] = proven by a saved, re-runnable test. [JUDGE] = scored by a fresh-eyes AI judge against the rubric in JUDGE.md, human gives final sign-off. [HUMAN] = the human personally checks. [INSPECT] = the agent examines output and reports exactly what it saw. -->

**Check command:** `[./check or equivalent — the one command that prints the scoreboard]`
**Project shape(s):** [personal tool / AI-content tool / web app for others / mobile app]
**What "good" means here:** [the quality dimensions chosen in Phase 3, one line each]

## A. Hard guardrails — tested FIRST every loop; a NO here outranks everything
1. [criterion] — [TAG]
   - How we'll prove it: [...]
   - Traces to mission: [one sentence]

## B. Core features — the job the tool exists to do
<!-- For web/SaaS shapes, live criteria go here: "a stranger can open the URL and complete the core task," "a test purchase goes through." -->
2. [criterion] — [TAG]
   - How we'll prove it: [...]
   - Traces to mission: [one sentence]

## C. General
3. [Runs where it's supposed to run: …] — [TAG]
4. [A setup guide a non-coder can follow exists and works.] — [HUMAN]
5. [The human can run the check command themselves and read the scoreboard.] — [HUMAN]

## D. Engineering quality — added automatically to every project
6. The code has automated tests covering the core job, and they pass. — [AUTO]
7. A code-style checker (linter) passes with no errors. — [AUTO]
8. No passwords, keys, or secrets anywhere in the code or its history. — [AUTO]
9. When something goes wrong, the user sees a plain-language message, never a raw crash. — [AUTO/INSPECT]
10. A fresh-eyes code review found no serious problems at the latest checkpoint. — [JUDGE]

---
**Signed by the human on:** [date]

## Amendment history
<!-- Date — what changed — one-line reason — re-signed by the human. Additions count too. -->
| Date | Change | Reason |
|---|---|---|
