# System vs User vs Assistant Prompts

Modern LLM APIs separate prompts into **roles**.  
Understanding these roles is essential for building **reliable, production-grade** LLM applications.

---

## Prompt Roles

### System Prompt
Defines the assistant’s behavior and rules.

- Who the assistant is
- What it must or must not do
- Global constraints and safety rules

Think of it as **application configuration**.

Example:
```
You are a senior software engineer.
Provide accurate, concise answers.
If unsure, say "I do not have enough information."
Do not hallucinate.
```

---

### User Prompt
Represents the actual request or input.

- What task needs to be done
- What data is provided

Think of it as **function input**.

Example:
```
Explain how a hash map works in simple terms.
```

---

### Assistant Prompt
Contains previous model responses.

Used for:
- Multi-turn conversations
- Context preservation
- Prompt chaining

Think of it as **conversation state**.

---

## Why This Matters

- Stronger control over model behavior
- Cleaner and more maintainable prompts
- Better safety and consistency
- Easier debugging and testing

---

## Best Practices

- Keep system prompts stable and versioned
- Keep user prompts focused on the task
- Use assistant prompts only for relevant context
- Do not allow users to override system rules

Correct separation of prompt roles is a key difference between
**demo-level prompting** and **production-ready LLM systems**.
