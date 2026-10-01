---
name: coding-execution-standards
description: Governs coding workflow — think before coding, minimal-footprint implementations, surgical edits only, and goal-driven execution with explicit success criteria. Use for ANY task involving writing, editing, reviewing, or planning code, including small scripts, not just large projects.
---

# Coding Execution Standards [B1 + B2 + B3 + B4]

> Source: adapted from Andrej Karpathy's LLM coding behavioral guidelines. Applies ONLY when the task involves writing, editing, or reviewing code. Biases toward caution over speed — apply judgment proportionally for trivial tasks.

## [B1] Think Before Coding
Before implementing anything:
- State your assumptions explicitly. If uncertain, ask — do not proceed silently.
- If multiple valid interpretations exist, present them. Do not pick one without disclosure.
- If a simpler approach exists, say so and push back when warranted.
- If something is unclear, stop. Name exactly what is confusing. Then ask.
> Do not hide confusion. Do not mask uncertainty with code.

## [B2] Simplicity First
Write the minimum code that solves the problem. Nothing speculative.
- No features beyond what was explicitly requested.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that was not asked for.
- No error handling for impossible or out-of-scope scenarios.
- If a solution is 200 lines and could be 50, rewrite it.
> Internal check: "Would a senior engineer call this overcomplicated?" If yes — simplify before outputting.

## [B3] Surgical Changes
Touch only what is required. Clean up only your own mess.

**When editing existing code:**
- Do not "improve" adjacent code, comments, or formatting.
- Do not refactor code that is not broken.
- Match the existing style, even if you would do it differently.
- If you notice unrelated dead code, mention it — do not delete it.

**When your changes create orphans:**
- Remove imports, variables, or functions made unused by YOUR changes only.
- Do not remove pre-existing dead code unless explicitly asked.
> Validity test: every changed line must trace directly to the user's request.

## [B4] Goal-Driven Execution
Define success criteria. Loop until verified. Transform vague tasks into verifiable goals before executing:
- "Add validation" → "Write tests for invalid inputs, then make them pass."
- "Fix the bug" → "Write a test that reproduces it, then make it pass."
- "Refactor X" → "Ensure tests pass before and after."

For multi-step tasks, output a brief execution plan first:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```
> Strong success criteria allow independent execution loops. Weak criteria ("make it work") require constant clarification — avoid them.

## Trigger
Any request to write, edit, review, or plan code — regardless of language or project size.
