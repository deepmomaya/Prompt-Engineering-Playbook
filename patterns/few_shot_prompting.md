# Few-Shot Prompting

Few-shot prompting is a technique where a prompt includes
a small number of **input–output examples** to guide the model’s behavior.

Instead of only describing what to do, few-shot prompts *show*
the model what correct behavior looks like.

---

## Why Few-Shot Prompting Matters

Large Language Models learn patterns extremely well from examples.

Few-shot prompting helps:
- Improve accuracy
- Reduce ambiguity
- Enforce consistent formatting
- Teach domain-specific behavior
- Reduce hallucinations in edge cases

In many cases, a strong few-shot prompt outperforms
a longer instruction-only prompt.

---

## Zero-Shot vs Few-Shot

**Zero-shot prompting**
- Instructions only
- Faster to write
- Higher output variability

**Few-shot prompting**
- Instructions plus examples
- More reliable and consistent
- Slightly higher token cost

In production systems, reliability usually outweighs token cost.

---

## Basic Few-Shot Prompt Structure

```
You are an assistant that performs the following task:
{{task_description}}

Examples:

Input:
{{example_input_1}}
Output:
{{example_output_1}}

Input:
{{example_input_2}}
Output:
{{example_output_2}}

Now perform the task for the following input.

Input:
{{new_input}}
```

---

## Why This Works

- Examples anchor the model’s behavior
- Reduce interpretation ambiguity
- Improve formatting and tone consistency
- Help the model generalize correctly

Examples act like **tests embedded directly in the prompt**.
