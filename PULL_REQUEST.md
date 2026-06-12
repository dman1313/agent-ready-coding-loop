# Pull Request Summary

## Summary

This updates Agent Ready Coding Loop to **v2.4: High-End SDD Agent Loop**.

The update turns the project from a starter prompt into a full agent operating framework for beginner and intermediate humans.

## Added

- `AGENTS.md` as the source-of-truth agent instruction file.
- `PROMPT.md` as the pasteable starter prompt.
- `USE_WITH_ANY_AGENT.md` quick-start.
- Compatibility pointers for Claude, Gemini, ChatGPT/Codex, Cursor, Mimo, and generic coding agents.
- Templates for:
  - `SDD.md`
  - `CONTRACT.md`
  - `PLAN.md`
  - `DEBUG.md`
  - `STUCK.md`
  - `HANDOFF.md`
  - `LATER.md`
- Theory and implementation docs.
- Contribution and security guidance.

## Core Behavior

The framework now requires:

- one-question-at-a-time interrogation;
- mission and vision;
- high-end SDD creation;
- skeptical SDD review;
- locked contract criteria;
- implementation plan;
- continuous coding loop;
- continuation/debug/ask-human/handoff rubrics;
- Context7 and official-doc source checks;
- final review and simplification.

## Verification

This change is documentation/framework only. Recommended verification:

- read `README.md` for public clarity;
- read `AGENTS.md` for agent completeness;
- compare templates against the v2.4 workflow;
- test by pointing an agent at the repo and saying:

```text
Follow these instructions when making any project or coding project.
```

