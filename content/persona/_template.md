---
title: "English Article Title"
subtitle: "A concise dek beneath the title."
description: "Search and social description."
date: 2099-01-01
draft: true
personaKicker: "Essay · Topic"
# For book-derived essays, replace personaKicker with these structured fields:
# contentType: "reading-note"
# sourceBook: "English Book Title"
# sourceBookZh: "中文书名"
url: "/persona/article-slug/"
translationUrl: "/zh/persona/article-slug/"
translationLabel: "中文"
translationCta: "Read in Chinese"
series: ["Persona"]
tags: ["Topic One", "Topic Two", "Topic Three"]
provenanceStatus: "blocked"
provenanceSources: []
build:
  list: never
  render: never
---

<!--
Reusable Persona template

- Publish English at /persona/... and make it the card's default destination.
- Create a paired Chinese file using the same structure, usually with .zh.md.
- In the Chinese file, reverse translationUrl and use translationLabel: "English".
- Keep Back to Persona and the language toggle in the shared template; do not add a custom top bar.
- Keep exactly three visible tags and mirror them in frontmatter, card data-tags, and card buttons.
- Set `provenanceStatus` in both language files. Use `verified` only after checking every publication-relevant claim against the public URLs listed in `provenanceSources`; use `not-applicable` with an empty list only when no external claim needs verification.
- Add the new card to content/persona/_index.md in reverse chronological order with `data-date`.
- Treat `Reading Notes` as a content family, not a series name. For book-derived pieces, use the book or an explicitly named multi-article project as the second `series` value.
- Give each card a two-axis visual identity: `data-skin` selects the restrained broad-topic color family, while `data-pattern` selects the series-specific linework. Add a stable kebab-case `data-series` key and a concise visible `.persona-entry-series` label. Reuse the same pattern within one series; do not reuse it for an unrelated book merely because both pieces are reading notes.
- Use `(n/total)` or `（n/total）` in the visible title only when a multi-article series and its total are actually planned. A standalone first piece does not need `(1/?)`.
- The body may be reorganized freely, but retain the shared kicker, subtitle, opening divider, drop cap, and h2 strata styling.
- For a single-file bilingual HTML article, use inlineLanguageToggle: true instead of a paired page.
-->

Opening paragraph. The shared Persona layout applies the drop cap automatically.

## First Section

Develop the essay with as many or as few sections as the piece needs.
