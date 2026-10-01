# Super Agent Powers — General AI Agent Package

Restructuring from `super-agent-powers` into two native General AI Agent configuration layers: **Rules** (always active) and **Skills** (on-demand, self-triggered by the agent).

## Content Map

| Folder | Original Protocol | Why It's Here |
| --- | --- | --- |
| `rules/core-identity-anti-sycophancy.md` | A1, A2 | Persona & anti-validation must be active across 100% of responses |
| `rules/privacy-anonymity.md` | A4 | Personalization prohibition must be active across 100% of responses |
| `rules/response-structure.md` | A7, A10, A11 | Date/Role/TL;DR format must be consistent in every response |
| `rules/language-terminology.md` | A9 | Language rules must be consistent in every response |
| `skills/anti-hallucination-reasoning/` | A3 | Situational — relevant when factual claims are present |
| `skills/controlled-assumption-clarification/` | A5 | Situational — only when the prompt is ambiguous |
| `skills/context-compression/` | A6 | Situational — only upon the `EXECUTE CONTEXT COMPRESSION` command |
| `skills/action-recommendation-transparency/` | A8 | Situational — when actions/recommendations occur |
| `skills/coding-execution-standards/` | B1–B4 | Situational — only during coding tasks |
| `skills/skill-self-evolution/` | B5 | Situational — only after a complex task is verified |

## Rules Installation

**If Chief is using General AI Agent 2.0 (IDE with Agent Manager panel):**

File-based method (recommended, can be committed to Git and shared with the team):

```
<workspace-root>/.agents/rules/core-identity-anti-sycophancy.md
<workspace-root>/.agents/rules/privacy-anonymity.md
<workspace-root>/.agents/rules/response-structure.md
<workspace-root>/.agents/rules/language-terminology.md

```

Simply copy the `rules/` folder to `.agents/rules/` at Chief's project root — the frontmatter `trigger: always_on` in each file is automatically read by the General AI Agent as instructions that are always loaded.

UI method (alternative, per-file, without Git):
Agent icon (left sidebar) → Customizations → Rules tab → **+ Workspace** → Activation Mode: **Always On** → paste file contents (excluding the `---` frontmatter section) → Save. Repeat for all four files.

**If Chief is using General AI Agent CLI (`agy`):**
This CLI reads a single flat `GEMINI.md` or `AGENTS.md` file in the active directory (not the `.agents/rules/` folder). Combine the contents of all four `rules/*.md` files (without frontmatter) into a single `GEMINI.md`, separated by `##` sections. To apply across all projects: `~/.gemini/GEMINI.md`.

> Both paths (2.0 vs. CLI) share the same agent platform but have differently documented configuration locations — verify which version Chief is using before selecting a path above.

## Skills Installation

* **Workspace** (project-specific): copy the `skills/*` folder to `<workspace-root>/.agents/skills/` (latest default; singular `.agent/skills/` is still supported for backward compatibility).
* **Global** (cross-project — recommended for Chief's package since it is not project-specific): copy to `~/.gemini/general-ai-agent/skills/`.

No manual trigger required — the agent reads the `name` + `description` of each skill at the start of the session, and automatically loads the full contents of `SKILL.md` when Chief's task matches one of the descriptions. After copying new skills, start a new session/conversation so the General AI Agent can re-detect the list of skills.

## Notes

Files in `rules/` deliberately do not use Skill-style `name`/`description` frontmatter — the General AI Agent Rules format uses `trigger:` (`always_on | glob | model_decision | manual`), rather than a description-based detection mechanism.

# super-agent-powers
