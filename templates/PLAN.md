# PLAN — the spec and the action plan
<!-- Written in Phase 4, BEFORE any product code. The handoff test applies hard here: a different agent, on a different model, with zero chat history, must be able to build this correctly from the files alone. Anything a builder would have to guess gets written in or asked now. -->

## Part 1 — The spec: how the finished thing works

**What it is:** [one plain paragraph]

**What the user sees and does:** [walk through the core task as the user experiences it, step by step]

**What happens underneath:** [one plain sentence per moving part]

**The stack:** [each technology named, with a one-sentence justification — simplest stack that does the job]

**Where it lives / how it's reached:** [local app? deployed where? For products: how a stranger reaches it]

**For AI-content tools — the prompt design:** [what the LLM is asked, what context it receives, what its output must contain and in what format. Omit this section if no LLM generates the product.]

**What it deliberately does NOT do:** [the cuts — see LATER.md]

**Naming, formats, and conventions a builder must not guess:** [file locations, output formats, naming patterns, edge-case behavior]

## Part 2 — The action plan
<!-- Ordered so guardrails and the riskiest unknowns come first. Every step: small, independently verifiable, produces something explainable in one sentence. Mark steps done with a date as the build proceeds — this is how any future session knows exactly where the build stands. -->

| # | Step (what it produces) | Criteria it serves | How it's verified | Done |
|---|---|---|---|---|
| 1 | [...] | [e.g., A1, D8] | [which test / inspection / judge rubric] | |
| 2 | [...] | [...] | [...] | |

## Plan changes
<!-- If the build teaches us the plan was wrong, the change is recorded here and said out loud. The plan serves the contract, never the other way around. -->
| Date | What changed | Why |
|---|---|---|
