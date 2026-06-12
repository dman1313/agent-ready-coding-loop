# Theory Behind Agent Ready Coding Loop

Agent Ready Coding Loop is based on a simple observation:

> The hardest part of working with a coding agent is usually not getting it to write code. It is getting it to understand what should be built, how success will be proven, and when it must stop.

This framework turns that observation into a repeatable process.

## 1. The Human Should Control Outcomes, Not Code

Beginner and intermediate humans often cannot judge whether code is correct by reading files. That does not mean they cannot direct software projects.

They can judge:

- whether the project goal is right;
- whether the workflow makes sense;
- whether the output matches what they asked for;
- whether the app feels useful;
- whether a plain-language scoreboard says YES or NO.

The framework gives the human control through artifacts:

- `SDD.md`: the human-readable shared understanding.
- `CONTRACT.md`: the locked proof checklist.
- `PLAN.md`: the route the agent will take.
- `./check`: independent evidence.
- `HANDOFF.md`: future recovery and continuation.

The agent owns the code. The human owns the direction.

## 2. Strong Interrogation Prevents Weak Specs

Weak prompts produce weak projects.

The interrogation phase exists because humans often start with a feeling, not a specification:

- "I want an app for my business."
- "I need a dashboard."
- "I want AI to help with documents."

Those are valid starting points, but they are not buildable yet.

The agent must gently but firmly narrow the idea:

- who is this for?
- what job does it do?
- what is version 1?
- what is out of scope?
- what does success look like?
- what would failure look like?
- what data is involved?
- what can the human verify?

This is not gatekeeping. It is protection against building the wrong thing confidently.

## 3. Mission And Vision Create Coherence

Projects need both focus and direction.

The **mission** answers:

> What must version 1 accomplish?

The **vision** answers:

> What could this become later if version 1 succeeds?

Mission prevents overscope. Vision prevents random work.

If something serves the vision but is not required for the mission, it goes to `LATER.md`.

## 4. SDD.md Is The Shared Understanding

`SDD.md` is the high-end spec-driven development file. It is not a bureaucratic document. It is the shared understanding that future agents can reload.

It captures:

- mission;
- vision;
- user;
- scope;
- requirements;
- data and risk;
- UX;
- architecture;
- testing strategy;
- assumptions;
- open questions;
- decisions.

The agent cannot code until the human approves the SDD.

This matters because a coding agent can execute very quickly in the wrong direction. The SDD slows the project down just enough to keep it pointed correctly.

## 5. CONTRACT.md Turns Understanding Into Proof

The SDD says what should be true.

The contract says how the project proves it.

Each criterion must be:

- binary: YES or NO;
- plain English;
- tied to the SDD;
- tagged as `[AUTO]`, `[HUMAN]`, or `[INSPECT]`;
- supported by evidence.

The contract is locked after approval. The agent may not weaken, remove, or reinterpret it to make the project look complete.

## 6. PLAN.md Enables Autonomous Progress

The plan breaks the contract into small implementation slices.

Each slice must include:

- target criteria;
- files likely touched;
- verification method;
- dependencies;
- risk notes.

This lets the agent continue coding without asking the human every few minutes, because the human has already approved the route.

## 7. The Continuation Rubric Is The Engine

Most agent workflows either stop too often or continue too recklessly.

This framework uses a continuation rubric:

The agent keeps coding only if:

- a contract criterion is still NO;
- the next step is inside the approved SDD and contract;
- the next step is small;
- the verification method is known;
- no guardrail is failing;
- no repeated failure pattern has appeared;
- no new human decision is required;
- risk, cost, data use, and scope do not change.

This is what makes the loop a loop.

The agent keeps moving, but only inside the rails.

## 8. Debugging Is A First-Class Phase

Broken work must not be buried under more work.

When tests fail, builds break, behavior is confusing, or a YES turns NO, the agent enters debug mode:

```text
Preserve evidence
-> Reproduce
-> Localize
-> Reduce
-> Fix root cause
-> Add guard test
-> Run full scoreboard
-> Resume
```

For non-trivial failures, the agent writes `DEBUG.md`.

If the same failure repeats or progress stalls, the agent writes `STUCK.md` and asks one non-technical question.

## 9. Doubt Is A Feature

Coding agents are often too agreeable.

This framework requires skeptical reviews before:

- approving `SDD.md`;
- approving `CONTRACT.md`;
- making non-trivial technical decisions;
- final handoff.

The agent asks:

- what is vague?
- what could disappoint the human?
- what assumption could be wrong?
- what is unsafe or fragile?
- what could fail even if the code runs?

The point is not negativity. The point is catching failures while they are still cheap.

## 10. Source Checks Reduce Stale Patterns

Agents often know old APIs and outdated framework patterns.

For framework, API, library, auth, deployment, payment, AI tooling, database, or browser decisions, the agent should:

1. check official documentation;
2. use Context7 when available for current, version-specific docs and examples;
3. cite important sources;
4. mark unverified decisions.

The source rail makes the build more current and trustworthy.

## 11. Handoff Makes The Work Durable

The project is not done just because code runs once.

The agent must leave behind:

- the final scoreboard;
- run instructions;
- re-check instructions;
- recovery instructions;
- important decisions;
- known limitations;
- version 2 ideas;
- notes for future agents.

That is what lets a future session resume instead of restarting.

## Summary

Agent Ready Coding Loop is a way to turn agentic coding from a single prompt into a project operating system.

The human supplies judgment.

The agent supplies engineering discipline.

The artifacts keep both aligned.

