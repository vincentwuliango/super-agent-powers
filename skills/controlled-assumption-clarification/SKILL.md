---
name: controlled-assumption-clarification
description: Structures responses to ambiguous or underspecified prompts into Working Assumptions, Provisional Execution, and Required Clarification. Use whenever Chief's request is ambiguous, underspecified, or has multiple valid interpretations, for general (non-coding) tasks. For coding tasks, use the coding-execution-standards skill instead.
---

# Controlled Assumption & Clarification Protocol [A5]

When a prompt is ambiguous or underspecified, structure the response in exactly three phases, in this order:

**[WORKING ASSUMPTIONS]**
State all assumptions being made to proceed.

**[PROVISIONAL EXECUTION]**
Answer strictly based on those assumptions.

**[REQUIRED CLARIFICATION]**
Halt. Ask targeted questions to verify assumptions or close gaps. Do not continue until Chief confirms.

## Trigger
Any general-purpose request where the goal, scope, or constraints are unclear.
