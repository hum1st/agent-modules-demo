---
name: demo-skill
description: >-
  Agent Modules demo greeting. Use when the user invokes demo-skill, /demo-skill,
  or asks for the Agent Modules demo hello. Reply with one localized greeting
  sentence that mentions Agent Modules.
license: MIT
metadata:
  author: hum1st
  source: agent-modules-demo
---

# demo-skill — localized hello from Agent Modules

## Goal

Send **exactly one short greeting sentence** to the user:

1. In the **language they are using** in this conversation (see detection below).
2. Clearly stating that the message **comes from Agent Modules** (keep the product name **Agent Modules** in Latin letters).

Do not add extra paragraphs, bullets, or follow-up questions unless the user asked for more.

## Detect the user's language

Pick **one** locale, in this order:

1. **Explicit locale** in the user's message (e.g. “用中文”, “in French”, “auf Deutsch” if you add German later).
2. **User / workspace rules** that require a reply language (e.g. “Always respond in Chinese-simplified”).
3. **Language of the user's latest message** (what they just wrote).
4. If still unclear, use **English**.

## Greeting lines (use verbatim for the chosen locale)

| Locale | Sentence |
|--------|----------|
| `en` | Hello! This greeting comes from Agent Modules. |
| `zh-CN` | 你好！这句问候来自 Agent Modules。 |
| `hi` | नमस्ते! यह अभिवादन Agent Modules की ओर से है। |
| `es` | ¡Hola! Este saludo proviene de Agent Modules. |
| `fr` | Bonjour ! Cette salutation vient d'Agent Modules. |
| `ar` | مرحبًا! هذه التحية من Agent Modules. |
| `bn` | হ্যালো! এই অভিবাদন Agent Modules থেকে এসেছে। |
| `pt` | Olá! Esta saudação vem do Agent Modules. |
| `ru` | Здравствуйте! Это приветствие от Agent Modules. |
| `ur` | سلام! یہ سلام Agent Modules کی طرف سے ہے۔ |

For a locale **not** in the table, write **one natural sentence** in that language with the same meaning (hello + from Agent Modules).

## Output rules

- **Only** the greeting sentence (no skill name, no markdown heading, no emoji unless the locale row already implies none).
- Do **not** run tools unless the user asked for something beyond the greeting.
- After sending the greeting, stop unless the user continues the conversation.
