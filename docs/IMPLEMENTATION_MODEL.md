# Implementation Model

This document explains how the loop should behave during real project work.

## State Machine

The framework can be understood as a state machine:

```text
START
-> INTERROGATE
-> WRITE_SDD
-> REVIEW_SDD
-> APPROVE_SDD
-> WRITE_CONTRACT
-> REVIEW_CONTRACT
-> APPROVE_CONTRACT
-> WRITE_PLAN
-> APPROVE_PLAN
-> BUILD
-> CHECK
-> DECIDE
```

The `DECIDE` state chooses one of:

```text
CONTINUE
DEBUG
ASK_HUMAN
HANDOFF
```

## Continue

Continue when the next action is:

- inside the approved SDD;
- inside the locked contract;
- small enough to verify;
- safe under all guardrails;
- not a repeat of the same failure;
- not dependent on a new human decision.

## Debug

Debug when:

- tests fail;
- build fails;
- runtime behavior is wrong;
- previously passing criteria regress;
- the root cause is unclear.

The agent must stop feature work until the debug loop is complete.

## Ask Human

Ask the human when the answer changes product meaning:

- scope;
- cost;
- privacy;
- legal risk;
- deployment;
- user experience;
- contract criteria.

Questions must be non-technical and asked one at a time.

## Handoff

Handoff when:

- all criteria are YES;
- evidence exists for every YES;
- the check command passes;
- human checks are complete;
- review and simplification are complete;
- `HANDOFF.md` is complete.

## Recommended Agent Behavior

The agent should talk like this:

```text
I am targeting criteria 3 and 4 next.
I will verify them by running ./check and inspecting the exported file.
No new scope or risk change is needed, so I can continue.
```

When debugging:

```text
The build broke, so I am stopping feature work.
I am preserving the error in DEBUG.md, then I will reproduce and localize it.
```

When blocked:

```text
I hit the same failure twice. I created STUCK.md.
I need one non-technical choice from you before continuing.
```

