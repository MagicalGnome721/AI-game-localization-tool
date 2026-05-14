# AI Game Localization Tool

A browser-based tool for translating and localizing game text with AI, glossary control, QA checks, cache, translation memory, and Excel/CSV workflow support.

Live Demo: https://magicalgnome721.github.io/AI-game-localization-tool/index_v8_prompt_v4.html

## About

AI Game Localization Tool is a single-page HTML tool designed for game localization workflows.

It helps translate game text from Excel or CSV files using OpenAI models while keeping terminology, style, placeholders, tags, and formatting under control.

The tool is useful for RPG, MMO, fantasy, wuxia, UI text, item names, weapon names, NPC dialogue, system messages, quests, and game-specific terminology.

## Features

Custom prompts for different content types:

- Weapon and item names
- NPC dialogue
- System and UI messages
- Multi-segment text separated by `|`

Glossary control:

- Add custom glossary terms directly in the browser
- Force English terms into preferred target translations
- Import and export glossary JSON
- Save glossary into the HTML file
- Push glossary updates to the repository
- Re-translate rows affected by glossary changes

Translation workflow:

- Import Excel or CSV files
- Select the source column
- Translate in batches
- Use cache to skip already translated lines
- Use fuzzy translation memory for similar lines
- Export translated results back to Excel

Quality checks:

- Placeholder preservation, such as `%s` and `%d`
- Tag preservation, such as `<color=gold>...</color>`
- Multi-segment separator preservation using `|`
- Short output warnings
- Duplicate output warnings
- Basic style and terminology checks

## Supported Languages

- Vietnamese
- Arabic
- Korean
- Turkish
- Khmer

## Usage

Open the live demo in your browser:

https://magicalgnome721.github.io/AI-game-localization-tool/index_v8_prompt_v4.html

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

Glossary terms are best used for fixed terminology such as item names, titles, places, factions, skills, NPC roles, and game-specific terms.

Examples:

```text
Guild Master -> Bang Chủ
Stable Master -> Quản Mã
Silk Road -> Con Đường Tơ Lụa
Dragon Soul Forbidden Land Ticket -> Long Hồn Cấm Địa Lệnh
