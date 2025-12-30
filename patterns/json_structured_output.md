# JSON Structured Output Pattern

In production systems, LLM outputs are often consumed by code.
Free-text responses are difficult to parse, validate, and trust.

The JSON Structured Output pattern enforces **machine-readable, predictable outputs**.

---

## When to Use

- API responses
- Data extraction
- Summarization pipelines
- Decision-making systems
- Any LLM output consumed by code

---

## Core Prompt Template

```
You must respond ONLY in valid JSON.
Do not include explanations, comments, or markdown.

Schema:
{
  "summary": string,
  "confidence": number,
  "risks": string[]
}

Input:
{{input}}
```

---

## Why This Works

- Removes ambiguity
- Enables strict parsing
- Improves reliability
- Reduces downstream errors

---

## Handling Invalid Output

Add a retry rule:
```
If your response is not valid JSON, correct it and return ONLY valid JSON.
```
