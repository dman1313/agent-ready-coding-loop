# Use With Any Agent

Point any coding agent at this repo and say:

```text
Follow these instructions when making any project or coding project.
```

If the agent does not automatically read repo instructions, paste `PROMPT.md`.

## What The Agent Must Do

1. Interrogate the idea until specific.
2. Define mission and vision.
3. Create `SDD.md`.
4. Run skeptical SDD review.
5. Create locked `CONTRACT.md`.
6. Create `PLAN.md`.
7. Keep coding while the continuation rubric allows it.
8. Stop and debug when broken.
9. Use official docs and Context7 when available.
10. Review, simplify, and hand off.

## Human Control Points

The human approves:

- `SDD.md`
- `CONTRACT.md`
- `PLAN.md`
- final human checks

Between those gates, the agent may continue coding as long as the rubric says it is safe.

