---
name: skill-self-evolution
description: Captures reusable problem-solving skills discovered during the session into a structured [SKILL REGISTRY], and applies previously-acquired skills when a matching trigger reappears. Use after completing a complex verified task, resolving an error through iteration, or discovering a non-obvious solution.
---

# Self-Evolution & Skill Synthesis [B5]

> Scope: applies only within the active session. Skills do not persist across sessions automatically — Chief must manually carry the `[SKILL REGISTRY]` into new sessions via copy-paste or the context-compression skill's `EXECUTE CONTEXT COMPRESSION` command.

## Trigger Conditions
Execute this protocol when ANY of the following occur:
- A complex task is completed and verified as correct.
- An error is resolved after iteration.
- A non-obvious solution is discovered through reasoning.

## Execution Sequence

**Step 1 — Skill Abstraction**
Strip away situational variables from the successful process. Identify the core, reusable principle or logic.

**Step 2 — Skill Documentation**
Output a block in this exact format:
```
[NEW SKILL ACQUIRED]
- Skill Name   : [Concise technical name]
- Trigger      : [Problem type or scenario where this skill applies]
- Core Logic   : [Generalized steps or parameters, context-independent]
- Verified Via : [Brief description of the task that validated this skill]
```

**Step 3 — Skill Application**
At the start of each response, scan the session's `[SKILL REGISTRY]` (all accumulated `[NEW SKILL ACQUIRED]` blocks in context). If the current task matches a documented Trigger, explicitly state:
> "Applying learned skill: [Skill Name]" — then execute accordingly.

## Skill Registry Management
- All `[NEW SKILL ACQUIRED]` blocks in a session collectively form the `[SKILL REGISTRY]`.
- When `EXECUTE CONTEXT COMPRESSION` is triggered (see context-compression skill), include all `[SKILL REGISTRY]` entries in the `[STATE_SUMMARY_V1]` output.

## Trigger
After any complex verified task, iterative bug fix, or non-obvious discovered solution — within the current session only.
