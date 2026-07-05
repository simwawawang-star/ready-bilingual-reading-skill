# Ready Bilingual Reading Skill

Ready Bilingual Reading is a prompt-based Skill for turning English academic readings into Chinese-English study materials.

It is designed for students and readers who want:

- A bilingual mind map at the beginning
- Paragraph-by-paragraph English/Chinese reading
- Chinese meanings annotated inside selected English academic words
- References kept in English
- Bilingual flashcards
- Chinese summary, section notes, glossary, and long sentence analysis

## What This Skill Does

For an English reading, this Skill produces:

1. One bilingual mind map
2. Full bilingual translation
3. References, if included in the source
4. Bilingual flashcards
5. Chinese summary
6. Section notes
7. Bilingual glossary
8. Long sentence analysis

It does not require an API key, token, password, or external service.

## Project Structure

```text
ready-bilingual-reading-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── examples/
│   ├── example-input.md
│   └── example-output.md
└── docs/
    └── PUBLISHING_CHECKLIST.md
```

## How To Use

1. Open `SKILL.md`.
2. Give the Skill an English academic reading or excerpt.
3. Ask it to generate bilingual reading materials.
4. If creating a PDF, make each major section start on a new page.

Example request:

```text
Please process this reading with the Ready Bilingual Reading Skill.
Keep the English original, translate paragraph by paragraph into Chinese,
annotate uncommon academic words, and include bilingual flashcards.
```

## Privacy Notes

Before publishing to GitHub, do not include:

- API keys or tokens
- Passwords
- Local absolute paths from your own computer
- Private PDFs or copyrighted course readings
- Generated outputs containing private notes
- Cache folders such as `__pycache__`

## Dependencies

This Skill itself has no required Python dependency. It is primarily a `SKILL.md` instruction file.

If you later add optional scripts for PDF rendering or image generation, document those scripts separately and update `requirements.txt`.

## License

This project is licensed under the MIT License. See `LICENSE`.

## Safe Example

See:

- `examples/example-input.md`
- `examples/example-output.md`

The example is synthetic and safe to publish.

## Publishing Status

This folder is prepared as a GitHub-ready candidate, but you should manually review the checklist in `docs/PUBLISHING_CHECKLIST.md` before publishing.
