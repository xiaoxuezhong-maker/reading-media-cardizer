---
name: reading-media-cardizer
description: Turn reading notes, book excerpts, viewing logs, film notes, and media reflections into structured Obsidian-ready creative cards. Use when the user asks to整理读书笔记, 观影记录, 书摘, 影视笔记, 或把阅读/观影材料做成卡片、知识卡、主题卡、人物卡、作品卡、金句卡、创作素材卡.
---

# Reading Media Cardizer

## Core Rule

Treat the original note as source material. Do not delete, hollow out, or overwrite the original reading note or viewing record. Create linked cards or wiki pages from it, and leave the source intact unless the user explicitly asks for a repair to the source.

When working in an LLM Wiki-style Obsidian vault, read from `raw/` first and write synthesized cards to `wiki/` or the vault's established card output folder. Do not move summary language back into `raw/`.

## Workflow

1. Read the source note before writing anything.
2. Identify whether the source is primarily a book/reading note, a film/viewing note, or a mixed media note.
3. Extract only grounded facts from the source. If metadata is missing, mark it as unknown or verify it from a reliable source when current accuracy matters.
4. Choose the smallest useful card set. Do not create a large taxonomy unless the source actually supports it.
5. Preserve source links: every generated card should link back to the source note, and the source note should get links to the generated cards when editing the vault is in scope.
6. Write cards in Simplified Chinese by default when Chinese output is requested.
7. Verify that filenames, links, and destination folders match the local vault conventions.

## Card Types

Use these card types as a menu, not a mandatory checklist.

- `作品卡`: title, creator, date/year, source note, one-sentence orientation, why it matters.
- `摘录卡`: exact quote or close paraphrase, page/timecode if available, immediate context, personal resonance.
- `主题卡`: recurring idea, supporting excerpts/scenes, related works, creative use.
- `人物卡`: person/character, role, conflict, memorable detail, related cards.
- `场景卡`: scene/location/moment, sensory detail, emotional tone, visual or narrative use.
- `问题卡`: question raised by the note, why it remains open, possible follow-up.
- `创作素材卡`: image, line, structure, premise, editing idea, title idea, or video/story seed.
- `行动卡`: concrete follow-up such as reread, watch related work, clip segment, draft essay, or update index.

## Reading Notes

For books, essays, book excerpts, and reading diaries:

- Keep bibliographic metadata separate from interpretation.
- Preserve page numbers, chapter names, Kindle locations, or original timestamps when present.
- Distinguish the author's idea from the user's reaction.
- Prefer a few durable cards over many shallow cards.
- If the source contains travel, life planning, or other cross-vault material, keep the reading note as the source of truth and add links rather than moving content away.

Recommended card fields:

```markdown
---
type: reading-card
source: "[[source note]]"
work: ""
creator: ""
date: ""
tags: []
---

# Card Title

## 核心

## 原文依据

## 我的理解

## 可转化为创作

## 相关链接
```

## Viewing Notes

For films, TV, interviews, documentaries, and video notes:

- Preserve title, director/creator, release year, watch date, timecode, episode, and platform if present.
- Separate plot facts from the user's interpretation.
- For film cards, capture audiovisual detail: framing, color, sound, pacing, performance, editing, space, weather, texture.
- When the source note includes screenshots or posters, keep the existing attachment reference and do not invent missing media.
- If generating visual SVG or image cards is requested, place them in the vault's established media card output folder and keep the Markdown/source links in sync.

Recommended card fields:

```markdown
---
type: viewing-card
source: "[[source note]]"
work: ""
creator: ""
year: ""
watch_date: ""
tags: []
---

# Card Title

## 这一幕/这一点

## 画面与声音

## 我为什么记住它

## 可转化为创作

## 相关链接
```

## Output Placement

Follow the user's project conventions first. If no convention exists:

- Put synthesized Markdown cards under `wiki/cards/`, `wiki/books/`, `wiki/films/`, or another clear `wiki/` subfolder.
- Put generated SVG/image card assets under the existing attachment/card asset folder.
- Keep raw source notes in place.
- Update `wiki/index.md`, `wiki/log.md`, or nearby source indexes only when the task includes indexing.

## Quality Checks

Before finishing:

- Confirm the source note still contains its original content.
- Confirm every generated card has a source link.
- Confirm no raw note was rewritten with synthesized prose.
- Confirm filenames are readable, stable, and do not contain temporary numbering unless the project already uses it.
- Report the created/updated files and any uncertain metadata.
