# Agent Skills (mirrored from addyosmani/agent-skills)

This directory contains a snapshot of the engineering workflow skills from
[addyosmani/agent-skills](https://github.com/addyosmani/agent-skills), mirrored
into this repo so the Loop Generator's reference agents and personas can apply
them in-context.

## Source

- **Upstream:** https://github.com/addyosmani/agent-skills
- **License:** MIT License (see [LICENSE](./LICENSE))
- **Snapshot date:** 2026-06-13

## What's here

24 skills organized by development phase, plus 5 reference checklists used by
specific skills.

### Skills (24)

| Phase | Skill | One-liner |
|---|---|---|
| Define | `interview-me` | Surface what the user actually wants before any plan, spec, or code exists |
| Define | `idea-refine` | Refine ideas through structured divergent and convergent thinking |
| Define | `spec-driven-development` | Requirements and acceptance criteria before code |
| Plan | `planning-and-task-breakdown` | Decompose into small, verifiable tasks |
| Build | `incremental-implementation` | Thin vertical slices, test each before expanding |
| Build | `source-driven-development` | Verify against official docs before implementing |
| Build | `doubt-driven-development` | Adversarial fresh-context review of every non-trivial decision |
| Build | `context-engineering` | Right context at the right time |
| Build | `frontend-ui-engineering` | Production-quality UI with accessibility |
| Build | `api-and-interface-design` | Stable interfaces with clear contracts |
| Build | `observability-and-instrumentation` | Logs, metrics, and traces from day one |
| Verify | `test-driven-development` | Failing test first, then make it pass |
| Verify | `browser-testing-with-devtools` | Chrome DevTools MCP for runtime verification |
| Verify | `debugging-and-error-recovery` | Reproduce → localize → fix → guard |
| Review | `code-review-and-quality` | Five-axis review with quality gates |
| Review | `code-simplification` | Preserve behavior while reducing unnecessary complexity |
| Review | `security-and-hardening` | OWASP prevention, input validation, least privilege |
| Review | `performance-optimization` | Measure first, optimize only what matters |
| Ship | `git-workflow-and-versioning` | Atomic commits, clean history |
| Ship | `ci-cd-and-automation` | Automated quality gates on every change |
| Ship | `deprecation-and-migration` | Remove old systems and migrate users safely |
| Ship | `documentation-and-adrs` | Document the why, not just the what |
| Ship | `shipping-and-launch` | Pre-launch checklist, monitoring, rollback plan |
| Meta | `using-agent-skills` | Discovers and invokes the right skill for the current task |

### References (5)

Supporting checklists referenced by individual skills:

- `accessibility-checklist.md` (used by `frontend-ui-engineering`, `shipping-and-launch`)
- `orchestration-patterns.md` (used by `using-agent-skills`, `context-engineering`)
- `performance-checklist.md` (used by `performance-optimization`, `shipping-and-launch`)
- `security-checklist.md` (used by `security-and-hardening`, `shipping-and-launch`)
- `testing-patterns.md` (used by `test-driven-development`)

## How this fits the Loop Generator

The Loop Generator emits a contract-driven starter prompt that orchestrates a
coding agent through a workflow. These skills give that agent a structured
playbook for each phase of that workflow — interview → refine → spec → plan →
build → test → review → ship. When a persona or reference agent is invoked, it
can load the relevant skill from this directory directly.

## Updating the snapshot

This mirror is a point-in-time copy. To refresh from upstream:

```bash
# From the repo root
rm -rf skills/
git clone --depth 1 https://github.com/addyosmani/agent-skills /tmp/agent-skills-fresh
mkdir -p skills/references
for skill in /tmp/agent-skills-fresh/skills/*/; do
  name=$(basename "$skill")
  mkdir -p "skills/$name"
  cp "$skill"SKILL.md "skills/$name/SKILL.md"
  [ -d "$skill/scripts" ] && cp -R "$skill/scripts" "skills/$name/"
  for extra in "$skill"/*.md; do
    [ -f "$extra" ] && [ "$(basename "$extra")" != "SKILL.md" ] && cp "$extra" "skills/$name/"
  done
done
cp /tmp/agent-skills-fresh/references/*.md skills/references/
cp /tmp/agent-skills-fresh/LICENSE skills/LICENSE
```

## Attribution

These skills were authored by Addy Osmani and contributors. See
[addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) for the
canonical version and ongoing development. Used under the MIT License.
