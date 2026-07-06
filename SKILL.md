---
name: ready-bilingual-reading
description: Generate bilingual Chinese-English reading notes for English academic readings, including a bilingual mind map, paragraph-by-paragraph translation, vocabulary annotations, notes, glossary, sentence analysis, and bilingual flashcards.
---

# Ready Bilingual Reading

Use this skill when the user provides an English academic reading, course reading, article excerpt, chapter, PDF text, or notes and asks for Chinese-English reading support.

## Output Order

Always keep the output in this order:

1. Bilingual mind map
2. Full bilingual reading translation
3. References, if present
4. Bilingual flashcards
5. Chinese summary
6. Section notes
7. Bilingual glossary
8. Long sentence analysis

Do not include internal processing notes, local file paths, source-device paths, extraction logs, metadata diagnostics, or publication status in the final reading output.

## Non-Negotiable Completeness Rules

The user is asking for a complete bilingual reading output unless they explicitly request a summary-only version.

Always follow these rules:

- Do not produce only a Chinese summary.
- Do not replace paragraph-by-paragraph translation with a summary.
- Do not skip the English original.
- Do not skip the Chinese translation.
- Do not silently omit required modules from the output order.
- Do not shorten the task into "key points only" unless the user explicitly asks for key points only.
- Full bilingual translation is the core deliverable; summary, notes, glossary, and flashcards are supporting modules.

If the source is too long for one response:

- Process it in clear parts by chapter, section, page range, or logical chunk.
- Complete the full bilingual translation for the current part before moving to supporting modules for that part.
- State what part has been completed and where the next part should continue.
- Continue from the next unprocessed paragraph or section; do not repeat completed content.
- Never use length as a reason to provide only a summary.

## Bilingual Mind Map

At the beginning of the document, insert one bilingual mind map only.

Use the heading format:

```markdown
## Chapter/Section Title Bilingual Mind Map / 章节标题中英对照思维导图
```

The mind map must:

- Be one visual map only.
- Use English and Chinese together in each node.
- Put the knowledge summary and key explanations at the center.
- Summarize the whole processed section, not only the first paragraph.
- Avoid adding explanatory paragraphs before or after the map.

If image generation or PDF rendering is available, place the map as an image. If only text output is available, use a compact Mermaid mind map or a clearly structured text mind map.

## Full Bilingual Translation

Translate paragraph by paragraph. Each English paragraph must be followed immediately by its Chinese translation.

Use this format:

```markdown
**English**

Original English paragraph.

**中文**

对应的中文翻译。
```

Translation rules:

- Keep the original meaning, tone, qualification, and uncertainty.
- Do not turn correlation into causation.
- Do not omit negations.
- Preserve numbers, years, citations, names, DOI, URL, and dataset/software names.
- Do not summarize instead of translating.
- Do not invent missing text.
- If text extraction is unreliable, mark the uncertainty instead of guessing.

## Vocabulary Annotations in English Text

In the English original paragraphs, annotate selected uncommon, academic, or field-specific words with Chinese meanings.

Use this format:

```text
methodology（方法论）
research design（研究设计）
informed consent（知情同意）
```

Rules:

- Annotate only the English original part.
- Keep annotations restrained and useful.
- Prefer academic terms, key concepts, and uncommon words that affect comprehension.
- Do not annotate every common word.
- Usually annotate the same term only once per paragraph.
- Do not annotate the References section.

## References

If a References section is present:

- Keep it after the full bilingual translation.
- Keep reference entries in English.
- Do not translate article titles, DOI, URL, journal names, author names, or publisher names.
- Place bilingual flashcards immediately after References.

## Bilingual Flashcards

Flashcards must appear after References.

Each flashcard must include English and Chinese together:

```markdown
**Q / English:** English question.

**问 / 中文：** 中文问题。

**A / English:** English answer.

**答 / 中文：** 中文答案。
```

Do not use placeholders such as "See notes", "Review glossary", "TODO", or "Refer to the paper".

## Chinese Summary

After flashcards, provide a Chinese summary of the processed section.

Include:

- One-minute summary
- Core research question or central issue
- Core argument
- Main conclusions
- Method or mode of argument, if identifiable

## Section Notes

For each major section, provide:

```markdown
### Section title

- 页码/位置：
- 本节目的：
- 中文摘要：
- 核心论点：
- 关键证据：
- 与全文论点的关系：
```

## Glossary

Provide a bilingual glossary:

| English term | 中文翻译 | Meaning in this text | 位置 |
|---|---|---|---|

Prioritize theoretical concepts, methods, field-specific terms, and recurring academic vocabulary.

## Long Sentence Analysis

Select 3-5 useful long or difficult sentences.

Use this format:

```markdown
### Sentence 1

**Original**

Original sentence.

**主句**

Main clause.

**从句和修饰成分**

Structural explanation.

**逻辑关系**

Logical relationship.

**中文翻译**

Natural Chinese translation.

**Simplified English**

Simplified English version.
```

## Page Layout for PDF or Document Output

When producing a PDF or paginated document, start each major part on a new page:

- Bilingual mind map
- Full bilingual translation
- References
- Bilingual flashcards
- Chinese summary
- Section notes
- Glossary
- Long sentence analysis

Do not include a Zotero note module unless the user explicitly asks for it.

## Privacy and Safety

Never include:

- API keys, tokens, passwords, or credentials
- Local absolute file paths
- Usernames from local file paths
- Internal extraction logs
- Processing status checklists
- Private source metadata not needed for reading

If the source text contains private information, warn the user and redact it unless the user explicitly asks to preserve it.
