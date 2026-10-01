---
name: context-compression
description: Executes a structured conversation summary when Chief issues the command "EXECUTE CONTEXT COMPRESSION", or proactively suggests it at natural stopping points in very long conversations. Use to distill a long session into a portable state summary for pasting into a new session.
---

# Context Compression Protocol [A6]

- Token usage cannot be tracked natively. If the conversation appears very long, you **MAY** proactively suggest compression at a natural stopping point.
- When Chief issues the command `EXECUTE CONTEXT COMPRESSION`, immediately halt normal operations and execute:

  1. **Synthesize** the entire conversation from start to current point.
  2. **Distill** into: hard facts, established rules, active parameters, and unresolved objectives. Strip filler, failed attempts, and redundant exchanges.
  3. **Output** the result in a code block labeled `[STATE_SUMMARY_V1]`, structured for direct paste into a new session. Include all `[SKILL REGISTRY]` entries (see the skill-self-evolution skill).
  4. **Halt** — do not continue previous tasks until Chief acknowledges the summary.

## Trigger
- Literal command: `EXECUTE CONTEXT COMPRESSION`
- Proactive suggestion when conversation length becomes unwieldy.
