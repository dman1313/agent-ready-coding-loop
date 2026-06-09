# The Loop Generator

A reusable starter prompt that turns a coding agent (Claude Code, Cursor, Codex, anything similar) into a patient interviewer, contract-writer, and loop-driven builder — designed for **non-technical humans** who want working software without reading a line of code.

The core idea: the human's power is not in the code, it's in the **contract** — a list of plain-English, YES/NO success criteria the agent may never weaken — and the **scoreboard** — one command the human can run themselves that prints YES or NO for every criterion, forever.

## How to use it

1. Open your coding agent in a fresh, empty project folder.
2. Paste the entire contents of [PROMPT.md](PROMPT.md) as your first message.
3. Answer its questions in plain English. It interviews first — no code gets written until you've approved the contract.

If you come back later in a new chat, paste the same prompt again in the same folder: it finds `CONTRACT.md` and resumes where it left off instead of restarting.

## What the agent does

- **Phase 1 — Interview.** Asks what you want, who it's for, where it runs, what it can cost, what data it touches. Helps you cut scope; every cut idea is saved to `LATER.md`.
- **Phase 1.5 — Ethics & risk check.** Scans for privacy/safety/legal tripwires before anything is built, and redesigns around them instead of just refusing.
- **Phase 2 — Contract.** 8–20 binary success criteria in plain English. You read it, you change it, you approve it — then it's locked and saved to `CONTRACT.md`. Only you can amend it, and every amendment is recorded.
- **Phase 3 — Loop.** Plan → build → run the full test suite → show the scoreboard. Repeats until every line is YES, with checkpoint commits at every improvement and a hard escalation rule when it's stuck (a plain-English Stuck Report ending in ONE non-technical question for you).
- **Phase 4 — Handover.** Final scoreboard with evidence, a non-coder setup guide, the re-check command, the finalized `LATER.md`, your real-world homework, and a recovery recipe for the day it breaks.

## Files it leaves in your project

| File | What it is |
|---|---|
| `CONTRACT.md` | The signed success criteria, plus amendment history |
| `LATER.md` | Every postponed idea — raw material for version 2 |
| `./check` (or similar) | One command that prints the plain-English scoreboard |
| `STUCK.md` | Only appears if blocked — what failed and the one decision needed from you |

## Changelog

- **v2.2** — the contract now lives on disk (`CONTRACT.md`) and survives chat sessions, with a resume-don't-restart protocol; [HUMAN] checks are wired into the loop's exit (bundled into one sign-off sitting); retry budget counts stagnation, not attempts — progress resets it; checkpoint commits on every scoreboard improvement; mid-build feature requests are formal amendments, never quiet extras; build/test with made-up data only whenever real people's data is involved; interview asks about running costs; concrete scoreboard example; Stuck Reports saved as `STUCK.md`; the agent stays inside the project folder.
- **v2 / v2.1** — interview-first design, ethics check, binary contract with [AUTO]/[HUMAN]/[INSPECT] tags, guardrails-first test suite, the loop with retry budget and Stuck Reports, handover protocol.
