# The Loop Generator

A reusable starter prompt that turns a coding agent (Claude Code, Cursor, Codex, anything similar) into a patient interviewer, contract-writer, and loop-driven builder — designed for **non-technical humans** who want working software without reading a line of code.

The project runs like a small company: **mission and vision first**, then goals, then a binary definition of done, then a spec-driven plan, then the build loop. The human's power is not in the code, it's in the **contract** — a list of plain-English, YES/NO success criteria the agent may never weaken — and the **scoreboard** — one command the human can run themselves that prints YES or NO for every criterion, forever.

## How to use it

1. Open your coding agent in a fresh, empty project folder.
2. Paste the entire contents of [PROMPT.md](PROMPT.md) as your first message.
3. Answer its questions in plain English. It interviews first — no product code gets written until the contract is signed and the plan is agreed.

If you come back later in a new chat, paste the same prompt again in the same folder: it reads the files on disk (`MISSION.md`, `CONTRACT.md`, `PLAN.md`…) and resumes at the first unfinished phase instead of restarting. It even works across different models — each one writes its own playbook into `ENGINE.md`.

## What the agent does

The prompt operates on three reinforcing layers — **Spec** (build the right thing), **Verify** (prove it's good), and **Persist** (rules that survive every session) — plus a standing **Question Rule**: in every phase, including mid-build, the agent stops and asks (one or two plain-English questions at a time) instead of guessing.

- **Phase 0 — Know your engine.** The agent identifies which LLM it's running on, checks the provider's current documentation and best practices (not just memory), and writes a playbook into `ENGINE.md` for how to squeeze the best code out of that specific model. Any model that later resumes the project does the same.
- **Phase 1 — Mission & vision.** The founding conversation. You give the app context; the agent asks questions until it can write `MISSION.md`: the mission (one sentence — who it helps and how), the vision (what wild success looks like beyond v1), and who it serves. This is the north star every later decision traces back to.
- **Phase 2 — Goals & scope.** Mission becomes version-1 goals: one core job plus a few supporting goals. The agent helps you cut; every cut idea goes to `LATER.md`. Includes the ethics & risk check — privacy/safety/legal tripwires get redesigned around before anything is built.
- **Phase 3 — Definition of done.** 8–20 binary success criteria in plain English — "the planner is 21 pages: YES/NO", "a beginner teacher can use it within five minutes: YES/NO" — each traced to the mission, each with a how-we'll-prove-it note. A devil's-advocate pass catches gaps before signing. You read it, you change it, you approve it — then it's locked in `CONTRACT.md`. Only you can amend it, and every amendment is recorded.
- **Phase 4 — The SDD plan.** Spec-driven development: before any code, the agent writes `PLAN.md` — a plain-language spec of how the finished thing works, then an ordered action plan of small steps, each naming the criteria it serves and how it's verified. Riskiest unknowns first. You get the walkthrough in plain words.
- **Phase 5 — The loop.** Plan (with verification plan) → build (≤3 criteria per iteration) → run the full test suite → show the scoreboard. Repeats until every line is YES, with checkpoint commits at every improvement, `PLAN.md` updated as steps complete, and a hard escalation rule when it's stuck (a plain-English Stuck Report ending in ONE non-technical question for you).
- **Phase 6 — Handover.** Final scoreboard with evidence, a non-coder setup guide, the re-check command, the finalized `LATER.md`, your real-world homework, a recovery recipe for the day it breaks — and an offer to start version 2 from the vision in `MISSION.md`.

## Files it leaves in your project

| File | What it is |
|---|---|
| `ENGINE.md` | Which LLM is driving, and its playbook for doing its best work |
| `MISSION.md` | The mission, vision, and who it serves — the north star |
| `CONTRACT.md` | The signed success criteria, plus amendment history |
| `PLAN.md` | The spec and the step-by-step action plan, with progress marked |
| `LATER.md` | Every postponed idea — raw material for version 2 |
| `./check` (or similar) | One command that prints the plain-English scoreboard |
| `STUCK.md` | Only appears if blocked — what failed and the one decision needed from you |

## Changelog

- **v3.0 — "The Company Model"** — restructured the whole flow to run like a company: new **Phase 1 mission & vision** interview producing `MISSION.md` (the north star — every criterion and trade-off must trace to it); goals & scope split into their own phase; the contract reframed as the **definition of done** with a worked example; new **Phase 4 SDD plan** (`PLAN.md`: plain-language spec + ordered, verifiable action plan, riskiest steps first) so the loop executes a plan instead of improvising; new **Phase 0 know-your-engine** — the agent identifies its own LLM, checks the provider's current docs, and writes a model-specific playbook to `ENGINE.md`, so the prompt squeezes the most out of any model; the always-on **Question Rule**; file-based resume now covers every phase, not just the contract.
- **v2.3** — integrated a 3-layer prompt engineering framework: **Spec** (agile bias toward smaller specs, definition-of-done checkpoint, explicit verification at every decision); **Verify** (quality dimensions defined before criteria, devil's-advocate review before signing, optional cross-model check, ≤3 criteria per loop iteration, pre-build verification plans); **Persist** (verification-plan-first rule, extractable working-style rules for `.claude.md` or equivalent).
- **v2.2** — the contract now lives on disk (`CONTRACT.md`) and survives chat sessions, with a resume-don't-restart protocol; [HUMAN] checks are wired into the loop's exit (bundled into one sign-off sitting); retry budget counts stagnation, not attempts — progress resets it; checkpoint commits on every scoreboard improvement; mid-build feature requests are formal amendments, never quiet extras; build/test with made-up data only whenever real people's data is involved; interview asks about running costs; concrete scoreboard example; Stuck Reports saved as `STUCK.md`; the agent stays inside the project folder.
- **v2 / v2.1** — interview-first design, ethics check, binary contract with [AUTO]/[HUMAN]/[INSPECT] tags, guardrails-first test suite, the loop with retry budget and Stuck Reports, handover protocol.
