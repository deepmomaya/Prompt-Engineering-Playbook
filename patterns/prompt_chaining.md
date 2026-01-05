# Prompt Chaining

Prompt chaining is a technique where a complex task is broken into
multiple smaller prompts, executed sequentially.

Each prompt performs a focused step, and its output becomes the input
to the next step.

This pattern improves reliability, debuggability, and control in
production LLM systems.

---

## Why Prompt Chaining Matters

Single, large prompts often:
- Mix multiple responsibilities
- Are hard to debug
- Fail silently
- Produce inconsistent outputs

Prompt chaining helps by:
- Separating concerns
- Making failures visible
- Improving reasoning quality
- Allowing validation between steps

Think of prompt chaining like a pipeline or workflow.

---

## When to Use Prompt Chaining

- Multi-step reasoning tasks
- Document processing pipelines
- Data extraction + transformation
- Decision-making workflows
- Any task with clear intermediate steps

---

## Basic Prompt Chaining Flow

Example steps:
1. Extract relevant information
2. Analyze or reason over extracted data
3. Produce a final structured output

Each step has its own prompt.

---

## Example Chain

### Step 1: Extraction Prompt
```
Extract the key facts from the following text.
Return the result as JSON.

Text:
{{input_text}}
```

### Step 2: Analysis Prompt
```
Analyze the extracted facts below.
Identify any risks or issues.

Facts:
{{extracted_facts}}
```

### Step 3: Final Output Prompt
```
Based on the analysis, produce a final recommendation.
Return the output in JSON format.

Analysis:
{{analysis}}
```

---

## Why This Works

- Each prompt has a single responsibility
- Intermediate outputs can be validated
- Errors are easier to trace
- Improves consistency on complex tasks
