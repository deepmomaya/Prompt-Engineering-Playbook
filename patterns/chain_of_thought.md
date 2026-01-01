# Chain-of-Thought Prompting Pattern

Some tasks require multi-step reasoning rather than direct answers.
Chain-of-Thought (CoT) prompting encourages the model to think step by step.

---

## When to Use

- Logical reasoning problems
- Multi-step calculations
- Root-cause analysis
- Decision-making tasks
- Complex explanations

---

## Core Prompt Template

```
Think step by step before producing the final answer.

Question:
{{question}}
```

---

## Why This Works

- Encourages intermediate reasoning
- Reduces shallow or incorrect answers
- Improves performance on complex tasks

---

## Safer Alternative

In production systems, avoid exposing internal reasoning.
Instead, request a final answer with concise justification.

```
Provide the final answer.
Include a brief, high-level explanation without revealing step-by-step reasoning.
```

Use it where reasoning matters,
and control how much internal thought is exposed.
