# 001 — Exact word-count instruction broken in every sentence

| Field | Value |
|---|---|
| Category | GEN-INSTR (instruction-following failure) |
| Model and version | ChatGPT (chatgpt.com, default model) |
| Interface | Web app |
| Date tested | 2026-11-02 |
| Runs | 1 |
| Failure rate | 1 / 1 |
| Severity | Low |

## Prompt (exact)

```
Write exactly 3 sentences about black holes. Each sentence must contain exactly 10 words. Do not use the letter "z".
```

## Expected behaviour

Three sentences, each with exactly 10 words, and no letter "z".

## Actual behaviour

```
Black holes trap light through their immense gravitational pull.
Their gravity bends space and slows time near them.
Scientists study them to understand the universe and gravity.
```

- Sentence count: 3 (correct)
- Letter "z": not used (correct)
- Word count: **9, 9, 9** (all wrong; each should be 10)

The model followed the easy constraints but missed the counting constraint in every sentence, and gave no sign that it was unsure.

## How to reproduce

1. Open a new chat on chatgpt.com.
2. Paste the prompt exactly.
3. Count words per sentence by hand.

## Why it might happen (hypothesis)

Hypothesis only: models read text as tokens, not words, so exact word counts are hard to track while writing. The model may also stop when a sentence "sounds complete" rather than checking the count.

## Notes

- Only 1 run so far, in a chat that also contained other tests. Next step: 5 runs, each in a new chat, to measure the real failure rate.
