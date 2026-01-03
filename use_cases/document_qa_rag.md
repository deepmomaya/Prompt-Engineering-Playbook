# Document Q&A with RAG (Retrieval-Augmented Generation)

Document Question Answering (Document Q&A) is one of the most common and
high-impact production use cases for Large Language Models (LLMs).

Retrieval-Augmented Generation (RAG) combines document retrieval with
LLM reasoning to generate grounded, reliable answers.

This file explains how prompt engineering fits into a RAG-based system.

---

## What Is RAG?

RAG is a pattern where:
1. Relevant documents are retrieved from a data source
2. Retrieved content is injected into the prompt
3. The LLM generates an answer strictly based on that context

This approach:
- Reduces hallucinations
- Keeps answers up to date
- Avoids retraining models
- Improves trust and correctness

---

## Typical RAG Flow

1. User asks a question
2. System retrieves relevant documents
3. Retrieved text is passed to the LLM as context
4. LLM generates a grounded response

Prompt engineering controls how strictly the model uses the retrieved data.

---

## Base RAG Prompt Template

```
You are an assistant answering questions using ONLY the provided context.

If the answer cannot be found in the context, respond with:
"I do not have enough information to answer this."

Context:
{{retrieved_documents}}

Question:
{{user_question}}
```

---

## Why Prompt Design Matters in RAG

Poor prompts lead to:
- Ignoring retrieved context
- Hallucinating missing facts
- Mixing external knowledge with documents

Well-designed prompts:
- Enforce grounding
- Improve reliability
- Reduce incorrect answers

---

## Structured Output Example

```
Return the response in the following JSON format:
{
  "answer": string,
  "source_summary": string
}
```

Structured outputs make answers easier to evaluate and debug.

---

## Common Failure Modes

- Irrelevant retrieval results
- Context that is too large or too small
- Prompts that allow guessing
- Missing fallback behavior

Prompt guardrails help mitigate these issues.
