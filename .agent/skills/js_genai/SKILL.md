---
name: Use JS GenAI SDK
description: Must be used every time you create Javascript and Typescript code using the Google GenAI SDK.
---

# JS GenAI SDK Developer Skill

This skill provides the required knowledge and must be used **every time you create Javascript and Typescript code using the Google GenAI SDK**. This applies whether you are using the new official `@google/genai` SDK or refactoring code that used older SDKs like `@google/generative-ai`.
It strongly relies on the official guidance from the JS GenAI maintainers.

## REQUIRED INITIALIZATION STEP

At the start of any task where you need to use this skill, you **MUST** update the local copy of the code generation guidelines to ensure you are using the latest best practices.

**Step 1:** Run the following command to update the guidelines file:
```bash
curl -sL "https://raw.githubusercontent.com/googleapis/js-genai/main/codegen_instructions.md" > .agent/skills/js_genai/codegen_instructions.md
```

**Step 2:** Use the `view_file` tool to read the newly updated `.agent/skills/js_genai/codegen_instructions.md` file.

**Step 3:** Follow the instructions in `codegen_instructions.md` EXACTLY when writing your code.

## Key Principles (from the guidelines)
- **Always use the correct SDK:** Use `@google/genai` instead of the legacy `@google/generative-ai`.
- Verify the models to use (e.g., `gemini-2.5-flash` or `gemini-2.5-pro` as documented in the guidelines).
- Rely on the `codegen_instructions.md` for specific implementations spanning from text generation, multimodal inputs, streaming, structured outputs, function calling, to media generation.

Always make sure the guidelines are completely read and understood before beginning the implementation.
