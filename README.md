# The Loop Generator

A reusable starter kit that turns a coding agent (Claude Code, Cursor, Codex, anything similar) into a patient interviewer, contract-writer, and loop-driven builder — designed for **non-technical humans** who want working software without reading a line of code.

The project runs like a small company: **mission and vision first**, then goals, then a binary definition of done, then a spec-driven plan, then the build loop. The human's power is not in the code, it's in the **contract** — a list of plain-English, YES/NO success criteria the agent may never weaken — and the **scoreboard** — one command the human can run themselves that prints YES or NO for every criterion, forever.

## How to use it

**Best way:** copy this whole repo (PROMPT.md + the `templates/` folder) into a fresh project folder, open your coding agent there, and paste the contents of [PROMPT.md](PROMPT.md) as your first message. The templates give every agent the same file formats, which is what makes agent-to-agent handoffs reliable.

**Lightest way:** just paste [PROMPT.md](PROMPT.md) on its own — it describes every format well enough for the agent to recreate them.

Answer its questions in plain English. It interviews first — no product code gets written until the contract is signed and the plan is agreed.

If you come back later in a new chat — or with a **completely different agent or model** — point it at the same folder and paste the prompt again: every file is written as a cold briefing (the Handoff Rule), so any agent resumes at the first unfinished phase with zero chat history. Each model writes its own playbook into `ENGINE.md`.

## What the agent does

Two rules never turn off: the **Question Rule** (heavy questioning while planning; once the plan is signed, the agent makes small calls itself, logs them in a vetoable `DECISIONS.md`, and batches non-urgent questions with each scoreboard — interrupting only when the answer changes what you'd get) and the **Handoff Rule** (every file on disk must let a stranger agent continue correctly; the chat is scratch paper, the files are the company).

- **Phase 0 — Know your engine.** The agent identifies which LLM it's running on, checks the provider's current documentation and best practices (not just memory), and writes a playbook into `ENGINE.md` for how to squeeze the best code out of that specific model — including how strong a fresh-eyes judge this environment can provide.
- **Phase 1 — Mission & vision.** The founding conversation. You give the app context; the agent asks questions until it can write `MISSION.md`: the mission (one sentence — who it helps and how), the vision (what wild success looks like beyond v1), and who it serves. This is the north star every later decision traces back to.
- **Phase 2 — Goals & scope.** Mission becomes version-1 goals: one core job plus a few supporting goals. The agent helps you cut; every cut idea goes to `LATER.md`. The project's **shape** gets named — personal tool, AI-content tool, web/SaaS product, mobile app — because shape changes what "done" must include: **if the mission involves customers or selling, "done" means deployed and reachable by a stranger, not working-on-your-machine.** Includes the ethics & risk check.
- **Phase 3 — Definition of done.** 8–20 binary success criteria in plain English — "the planner is 21 pages: YES/NO", "a beginner teacher can use it within five minutes: YES/NO" — each traced to the mission. Plus an **automatic engineering-quality group on every project**: automated tests, a passing linter, no secrets in the code, plain-language error messages, and a fresh-eyes code review before every checkpoint — you never have to know to ask. A devil's-advocate pass catches gaps before signing; then it's locked in `CONTRACT.md`. Only you can amend it, and every amendment is recorded.
- **The AI judge.** Subjective criteria ("reads like a high-quality recipe book") get a written rubric in `JUDGE.md` and are scored every iteration by the freshest eyes available — a different model, or a clean session that never saw the build — so quality climbs without waiting on you. The judge's YES is provisional; you give the final sign-off.
- **Phase 4 — The SDD plan.** Spec-driven development: before any code, the agent writes `PLAN.md` — a plain-language spec (including prompt design for AI-content tools and deployment for products), then an ordered action plan of small steps, each naming the criteria it serves and how it's verified. Riskiest unknowns first. Built to pass the handoff test: a different agent could build it cold.
- **Phase 5 — The loop.** Plan (with verification plan) → build (≤3 criteria per iteration) → run the full test suite and the judge → show the scoreboard with your batched questions under it. Repeats until every line is YES, with checkpoint commits (preceded by the fresh-eyes code review) at every improvement, and a hard escalation rule when it's stuck (a plain-English Stuck Report ending in ONE non-technical question for you).
- **Phase 6 — Handover.** Final scoreboard with evidence, a non-coder setup guide, the re-check command, a two-minute walkthrough of `DECISIONS.md`, the finalized `LATER.md`, your real-world homework, a recovery recipe for the day it breaks — and an offer to start version 2 from the vision in `MISSION.md`.

## Files it leaves in your project

| File | What it is |
|---|---|
| `ENGINE.md` | Which LLM is driving, its playbook, and its judging capability |
| `MISSION.md` | The mission, vision, and who it serves — the north star |
| `CONTRACT.md` | The signed definition of done, incl. auto engineering guardrails, plus amendment history |
| `JUDGE.md` | Rubrics for subjective quality and the fresh-eyes judge prompt |
| `PLAN.md` | The spec and the step-by-step action plan, with progress marked |
| `DECISIONS.md` | Small calls the agent made on your behalf — every one vetoable |
| `LATER.md` | Every postponed idea — raw material for version 2 |
| `./check` (or similar) | One command that prints the plain-English scoreboard |
| `STUCK.md` | Only appears if blocked — what failed and the one decision needed from you |

Skeletons for all of these live in [`templates/`](templates/) so every agent fills in the same formats.

## Changelog

- **v3.1** — shaped by a design interview: **handoff-ready by rule** (every file is a cold briefing; planner and builder can be different agents/models); **template kit** (`templates/` skeletons for every project file); **the AI judge** (subjective criteria get rubrics in `JUDGE.md`, scored each iteration by a different model or fresh session, human keeps final sign-off — same machinery does a fresh-eyes code review before every checkpoint); **automatic engineering-quality criteria** on every contract (tests, linter, no secrets, plain-language errors, code review); **project shapes** (personal / AI-content / web–SaaS / mobile) with shape-specific consequences — including **deployed = done** when the mission involves customers or selling; **two-mode Question Rule** (front-loaded questioning through planning, then autonomous building with a vetoable `DECISIONS.md` log and batched questions per scoreboard).
- **v3.0 — "The Company Model"** — restructured the whole flow to run like a company: new **Phase 1 mission & vision** interview producing `MISSION.md` (the north star — every criterion and trade-off must trace to it); goals & scope split into their own phase; the contract reframed as the **definition of done** with a worked example; new **Phase 4 SDD plan** (`PLAN.md`: plain-language spec + ordered, verifiable action plan, riskiest steps first) so the loop executes a plan instead of improvising; new **Phase 0 know-your-engine** — the agent identifies its own LLM, checks the provider's current docs, and writes a model-specific playbook to `ENGINE.md`, so the prompt squeezes the most out of any model; the always-on **Question Rule**; file-based resume now covers every phase, not just the contract.
- **v2.3** — integrated a 3-layer prompt engineering framework: **Spec** (agile bias toward smaller specs, definition-of-done checkpoint, explicit verification at every decision); **Verify** (quality dimensions defined before criteria, devil's-advocate review before signing, optional cross-model check, ≤3 criteria per loop iteration, pre-build verification plans); **Persist** (verification-plan-first rule, extractable working-style rules for `.claude.md` or equivalent).
- **v2.2** — the contract now lives on disk (`CONTRACT.md`) and survives chat sessions, with a resume-don't-restart protocol; [HUMAN] checks are wired into the loop's exit (bundled into one sign-off sitting); retry budget counts stagnation, not attempts — progress resets it; checkpoint commits on every scoreboard improvement; mid-build feature requests are formal amendments, never quiet extras; build/test with made-up data only whenever real people's data is involved; interview asks about running costs; concrete scoreboard example; Stuck Reports saved as `STUCK.md`; the agent stays inside the project folder.
- **v2 / v2.1** — interview-first design, ethics check, binary contract with [AUTO]/[HUMAN]/[INSPECT] tags, guardrails-first test suite, the loop with retry budget and Stuck Reports, handover protocol.
