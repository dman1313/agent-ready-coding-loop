# File Manifest

## Core

- `README.md`: explains the framework and how to use it.
- `assets/agent-ready-coding-loop-flow.svg`: GitHub README flowchart image.
- `assets/agent-ready-coding-loop-flow-social.png`: Twitter/X-friendly share image.
- `PROMPT.md`: pasteable starter prompt for agents that do not auto-load repo instructions.
- `AGENTS.md`: source-of-truth instructions for any coding agent.
- `USE_WITH_ANY_AGENT.md`: short quick-start for pointing any agent at the repo.
- `ACKNOWLEDGEMENTS.md`: citations and prior-work notes.
- `CONTRIBUTING.md`: contribution guidance for public collaboration.
- `SECURITY.md`: security reporting and secret-handling guidance.
- `PULL_REQUEST.md`: ready-to-use PR summary for the v2.4 upgrade.

## Docs

- `docs/THEORY.md`: explains the theory behind the framework.
- `docs/IMPLEMENTATION_MODEL.md`: explains the loop as a state machine.

## Compatibility Pointers

- `CLAUDE.md`: Claude Code compatibility pointer.
- `GEMINI.md`: Gemini CLI compatibility pointer.
- `CHATGPT.md`: ChatGPT/Codex compatibility pointer.
- `MIMO.md`: Mimo compatibility pointer.
- `GENERIC_AGENT.md`: generic coding-agent pointer.
- `.cursor/rules/agent-ready-loop.mdc`: Cursor project rule.

## Templates

- `templates/SDD.md`: high-end spec-driven development document.
- `templates/CONTRACT.md`: locked YES/NO success criteria.
- `templates/PLAN.md`: implementation plan and rubrics.
- `templates/DEBUG.md`: non-trivial debugging record.
- `templates/STUCK.md`: blocker report with one human question.
- `templates/HANDOFF.md`: run, re-check, recovery, and maintenance guide.
- `templates/LATER.md`: postponed version 2 ideas.

## Install Into The Main Repo

Copy these files to the root of `dman1313/agent-ready-coding-loop`, preserving the `.cursor/rules/` and `templates/` folders.
