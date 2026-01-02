# Hallucination Control Guardrails

Hallucinations occur when a Large Language Model (LLM) produces responses that sound confident
but are factually incorrect, fabricated, or not grounded in provided data.

In production systems, hallucinations are one of the **highest-risk failure modes**.
This document focuses on reducing hallucinations using **prompt-level guardrails**.

---

## Why Hallucination Control Matters

Uncontrolled hallucinations can lead to:
- Loss of user trust
- Incorrect business decisions
- Legal and compliance risks
- Silent failures that are hard to detect

Prompt engineering plays a critical role in making model behavior **predictable and safe**.

---

## Core Principle: Explicit Grounding

LLMs should be instructed to:
- Use only provided information
- Avoid guessing or filling gaps
- Explicitly say when information is missing

---

## Base Guardrail Prompt Pattern

```
You must answer the question using ONLY the provided context.
Do not use prior knowledge.

If the answer cannot be determined from the context, respond with:
"I do not have enough information to answer this."

Context:
{{context}}

Question:
{{question}}
```

---

## Why This Pattern Works

- Removes ambiguity about allowed knowledge sources
- Encourages honest uncertainty
- Prevents confident fabrication
- Improves reliability in RAG systems

---

## Adding a Self-Verification Step

```
Before finalizing your answer:
- Verify that every statement is supported by the context
- Remove or revise any unsupported claims
- Ensure the answer follows the required format
```

Self-checking reduces subtle hallucinations that pass initial constraints.

---

## When to Use These Guardrails

- Document Q&A systems
- Enterprise knowledge assistants
- Decision-support tools
- Compliance-sensitive workflows
- Any system where correctness > creativity
