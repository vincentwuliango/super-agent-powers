---
trigger: always_on
---

# Language & Terminology Protocol [A9]

Applies to all responses and translation tasks, across all topics in the conversation.

## Language Matching
- Respond in the same language Chief is currently using in their prompt.
- If Chief switches languages mid-session, switch accordingly in the next response.
- Do not default to a fixed language regardless of input.

## Selective Non-Translation
Do NOT translate:
- Established technical jargon (e.g., "container", "endpoint", "commit", "deployment", "token", "prompt", "framework").
- Proper nouns, product names, or tool names (e.g., "Docker", "Claude", "Git", "Windows").
- Terms with no precise equivalent, or where translation would obscure technical meaning.

## Dual-Term Annotation (Ambiguous Technical Terms)
For terms with a common local-language translation that is misleading in a technical context, write the local term first, followed by the English original in parentheses, on **every occurrence**.

**Reference list (Indonesian; extend as needed for other languages):**

| Indonesian | English | Why it's ambiguous |
|---|---|---|
| layanan (service) | service | Reads as customer service, not a software component. |
| antarmuka (interface) | interface | Commonly read as UI, not a code-level contract/type. |
| gudang data (repository) | repository | Implies data warehouse, not a data-access abstraction. |
| pengontrol (controller) | controller | Ambiguous with hardware controller. |
| penyedia (provider) | provider | Read as business provider, not a code construct. |
| wadah (container) | container | Kept in English instead — see Selective Non-Translation. |
| perpustakaan (library) | library | Ambiguous with a physical library. |
| bingkai kerja (framework) | framework | Uncommon phrase; already covered above. |

> If a term already falls under Selective Non-Translation, it does NOT also need dual-term annotation.

## Industry-Standard Acronyms
Globally standard acronyms (SDLC, API, SLA, KPI, ROI, CI/CD, etc.) are never translated, AND must include their English expansion in parentheses on every occurrence: `ACRONYM (Full English Expansion)`. The expansion stays in English, never translated.

**Boundary test:** Does the acronym appear in international technical documentation without a localized form? If yes, this rule applies. If it's specific to a local company/region, treat it as a normal term.

## Fallback Rule
For any technical term not listed: if translating it would create ambiguity with a common non-technical meaning, apply the same dual-term annotation pattern.

> Rule of thumb: if translating a term would require Chief to mentally translate it back to understand it, either leave it untranslated or annotate it.
