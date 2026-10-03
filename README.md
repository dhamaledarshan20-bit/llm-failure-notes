# llm-failure-notes

A public log of large language model failures I find and document, with exact prompts, expected vs. actual behavior, and reproducibility notes.

Maintained by [Darshan Dhamale](https://github.com/dhamaledarshan20-bit) · dhamaledarshan20@gmail.com

## Why this exists

Model failures are only useful if other people can reproduce and learn from them. Every entry here includes the full prompt, the model and version tested, the date, and how often the failure occurred across repeated runs. Where I explain *why* a failure happens, I label it as a hypothesis unless I have evidence for it.

## Scope and ethics

- I document benign, reproducible failures: wrong reasoning, hallucination, instruction-following breaks, inconsistent refusals, prompt-injection behavior in harmless test setups.
- I do **not** publish working jailbreaks or outputs that give real uplift for weapons, malware, self-harm, or other serious harm.
- No API keys, personal data, or private third-party content appear in any entry.

## Failure categories

Categories follow the [OWASP Top 10 for LLM Applications (2025)](https://genai.owasp.org/llm-top-10/) where they fit, plus a few general ones.

| Code | Category |
|------|----------|
| LLM01 | Prompt injection |
| LLM02 | Sensitive information disclosure |
| LLM05 | Improper output handling |
| LLM06 | Excessive agency |
| LLM07 | System prompt leakage |
| LLM09 | Misinformation (including hallucination) |
| GEN-REASON | Reasoning, math, or logic error |
| GEN-INSTR | Instruction-following failure |
| GEN-REFUSE | Inconsistent or incorrect refusal |

## How each entry is written

Every entry lives in `failures/` and follows [`failures/TEMPLATE.md`](failures/TEMPLATE.md). Files are numbered in order: `001-short-name.md`, `002-short-name.md`, and so on.

## Index of entries

| # | Title | Category | Model tested | Failure rate | Date |
|---|-------|----------|--------------|--------------|------|
| – | No entries yet | – | – | – | – |

## Method

For each entry I run the same prompt multiple times (at least 5) with fixed settings, record how many runs fail, and note the temperature and any system prompt. A failure seen once is logged as "observed once", not as a reproducible failure.

## License

MIT. See [LICENSE](LICENSE).
