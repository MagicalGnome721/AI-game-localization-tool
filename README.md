# Weapon Naming Tool

A browser-based localization and translation helper for game text, item names, weapon names, NPC dialogue, system messages, and glossary-controlled terminology.

Live Demo: https://magicalgnome721.github.io/weapon-naming-tool/index_v8_prompt_v4.html

## About

Weapon Naming Tool is a single-page HTML tool designed for internal game localization workflows. It helps translate Excel or CSV text using OpenAI models while keeping terminology, style, placeholders, tags, and formatting under control.

The tool supports multiple target languages, including Vietnamese, Arabic, Korean, Turkish, and Khmer. It is especially useful for fantasy, RPG, MMO, wuxia, and game UI text where consistent terminology matters.

## Main Features

Custom system prompts for different content types:

- Weapon and item names
- NPC dialogue
- System and UI messages
- Multi-segment text separated by `|`

Glossary control:

- Add custom glossary terms directly in the browser
- Force English terms into preferred target translations
- Save glossary into the HTML file
- Import and export glossary JSON
- Re-translate rows affected by glossary changes

Translation workflow:

- Import Excel or CSV files
- Select the source column
- Translate in batches
- Use cache to avoid translating repeated lines
- Use fuzzy translation memory for similar lines
- Export translated results back to Excel

Quality checks:

- Placeholder preservation, such as `%s` and `%d`
- Tag preservation, such as `<color=gold>...</color>`
- Multi-segment separator preservation using `|`
- Short output warnings
- Duplicate output warnings

## Supported Languages

- Vietnamese
- Arabic
- Korean
- Turkish
- Khmer

## Usage

Open the live demo in your browser:

https://magicalgnome721.github.io/weapon-naming-tool/index_v8_prompt_v4.html

Then:

1. Enter your OpenAI API key.
2. Select the target language.
3. Import an Excel or CSV file.
4. Choose the source text column.
5. Adjust the prompt or glossary if needed.
6. Click translate.
7. Review QA warnings.
8. Export the translated Excel file.

## Glossary Notes

Glossary terms should be used for fixed terminology such as item names, titles, places, factions, skills, and game-specific terms.

Examples:

```text
Guild Master -> Bang Chủ
Stable Master -> Quản Mã
Silk Road -> Con Đường Tơ Lụa
Dragon Soul Forbidden Land Ticket -> Long Hồn Cấm Địa Lệnh
