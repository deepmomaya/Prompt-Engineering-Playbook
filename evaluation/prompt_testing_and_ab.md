# Prompt Evaluation and A/B Testing

Prompt engineering does not end with writing prompts.
In production systems, prompts must be measured, tested, and iterated
just like application code.

This document explains how to evaluate prompts and run A/B tests
to improve quality, reliability, and cost efficiency.

---

## Why Prompt Evaluation Matters

Without evaluation, prompt changes can:
- Quietly reduce accuracy
- Increase hallucinations
- Break downstream systems
- Increase latency and token cost

Prompt evaluation turns prompt engineering into an
engineering discipline instead of guesswork.

---

## Key Metrics to Measure

Common evaluation dimensions include:

- Correctness – Is the response factually correct?
- Grounding – Is the answer supported by context?
- Consistency – Does the prompt behave predictably?
- Format compliance – Does output follow the required schema?
- Latency – How long does the response take?
- Cost – How many tokens are consumed?

---

## Offline Prompt Testing

Offline testing evaluates prompts against a fixed dataset.

Typical workflow:
1. Prepare representative test inputs
2. Run prompts against each input
3. Capture outputs
4. Score outputs using rules or human review
5. Compare results across prompt versions

This is similar to unit testing for prompts.

---

## Online A/B Testing

A/B testing compares two prompt versions in production.

Example:
- Prompt A → current version
- Prompt B → new candidate

Metrics to compare:
- User satisfaction
- Error rate
- Hallucination frequency
- Token usage
- Response latency

Roll out winning prompts gradually.

---

## Prompt Versioning Best Practices

- Store prompts in source control
- Use clear version identifiers
- Log prompt version with each request
- Make rollbacks easy and fast

---

## Example Evaluation Prompt

```
Evaluate the response below.

Check for:
- Factual correctness
- Context grounding
- Format compliance

Return:
- A score from 1 to 5
- A short explanation
```
