---
name: ru-translation-polisher
description: Translate text into Russian using the MCP tool translate_text_ru, then polish the result while preserving formatting, placeholders, code, URLs, and technical terms.
license: MIT
metadata:
  version: "0.1.0"
  required_tools:
    - translate_text_ru
  category: translation
---

# RU Translation Polisher

Use this skill when the user asks to translate text into Russian and the result should be polished, normalized, or adapted for readability.

## Required MCP tool

- `translate_text_ru`

## Workflow

1. Read the source text.
2. Detect whether it is plain text, Markdown, UI copy, email, docs, or technical text.
3. Call the MCP tool `translate_text_ru` with the source text.
4. Post-process the Russian result:
   - preserve Markdown structure;
   - preserve code blocks, inline code, URLs, file paths, JSON/YAML keys, env vars, placeholders, function names, and tool names;
   - keep meaning faithful to the source;
   - make Russian natural and readable;
   - keep technical terms like API, endpoint, gateway, token, MCP, CLI, SDK when appropriate.
5. Return the final Russian text.
6. For technical or structured input, add a short QA block.

## Output format

If the user only asks for translation:

```text
<final Russian translation>
