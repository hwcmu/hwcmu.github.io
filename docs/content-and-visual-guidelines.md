# Content and visual guidelines

Established: 2026-11-08. Read this before researching, drafting, placing, or publishing portfolio content, or changing article cards. Follow the publication and evidence checks in [AGENTS.md](../AGENTS.md) as well.

This is the canonical reference for content roles and Persona card identity. Keep it aligned with the shared CSS and templates when those rules change. Do not infer a redesign from a new article.

## Content roles

| Section | Purpose | Placement rule |
| --- | --- | --- |
| Projects | Work Hairong has personally done, with a paper or another concrete outcome | Explain the question, personal contribution, methods, deliverables, and evidence. A literature observation alone is not a Project. |
| Notes | Valuable ideas from professional reading, connected and synthesized around a question | Explain what the literature contributes, where findings agree or differ, and what can reasonably be concluded. A Note need not be a tutorial, contain code, or originate in a personal project. |
| Persona | Personal reading, observations, reflections, and accessible environmental science writing | Preserve the author's perspective. Environmental explainers for general readers belong here, including water, energy, and everyday life. Having references does not automatically make a piece a Note. |
| Papers | Formal publication record | Keep bibliographic details and canonical paper, Code, and Project links together. |

The public site foregrounds professional work. Persona remains a small homepage entrance through the mask button; do not add it to the main navigation or give it a prominent homepage panel by default. Keep the current Home / Projects / Notes / Papers navigation model.

One subject may support several distinct pieces. For example, a completed energy analysis is a Project; a synthesis of literature on stock and flow measures is a Note; an explanation of energy use in everyday life is a Persona article. Cross-link useful companions, but do not duplicate the same article or require every subject to produce all three.

Distinguish source findings from the author's interpretation. Preserve public provenance for factual claims. A reference list alone is not verification, and a personal reflection is not a substitute for evidence for its factual claims.

## Topic, source, and series

- A topic describes the subject; a source identifies a book, paper, or other material; a series groups a deliberately connected set of articles. Do not use these interchangeably.
- `Reading Notes` is a content family, not a series identity. Use the book or a named writing project for a reading series.
- Use no more than three reader-facing tags per article. Keep frontmatter, card `data-tags`, and visible tag buttons aligned; do not add hidden filtering tags.
- Use one primary placement per article. Use links and tags for secondary relationships rather than duplicate publication.
- Include a readable series label. Decoration must never be the only way to identify a topic or series.
- Use `(n/total)` only for an actually planned multi-article series. Check the public reading order before publishing a later part. Do not publish an unreviewed earlier draft merely to fill a numbering gap; if earlier parts are unavailable, make that status clear or review the numbering with the author.
- Keep general article lists newest first. A dedicated series directory may present its explicit reading order, clearly distinguished from the chronological feed.

## Persona visual identity

Use the existing two-axis system:

- `data-skin`: broad-topic color family.
- `data-pattern`: series-specific linework.
- `data-series`: stable kebab-case series identifier.
- `.persona-entry-series`: concise visible book or series label.

Articles in one series reuse all three data values. Unrelated books or series can share a color family but must not silently share a series pattern. Register a new pattern here and in the shared CSS before using it; do not add article-specific inline CSS.

### Color registry

The hex value identifies the base color, not the final rendered card color. The shared CSS applies the alpha values below over the current theme. Use tokens rather than arbitrary per-card colors.

| `data-skin` | Family | Base color | `--skin-accent` alpha | `--skin-soft` alpha | `--skin-line` alpha | Status |
| --- | --- | --- | --- | --- | --- | --- |
| `reading` | Reading; muted wine | `#8E4E58` / `142, 78, 88` | 0.62 | 0.08 | 0.15 | Implemented |
| `systems` | Systems, technology, and governance; teal | `#187B76` / `24, 123, 118` | 0.62 | 0.09 | 0.14 | Implemented |
| `learning` | Learning and education; ochre | `#B87126` / `184, 113, 38` | 0.62 | 0.09 | 0.16 | Implemented |
| `history` | History and civilization; olive | `#635F37` / `99, 95, 55` | 0.62 | 0.09 | 0.17 | Implemented |
| `environment` | Environment and everyday life; sage | `#547567` / `84, 117, 103` | 0.62 | 0.08 | 0.14 | Reserved for future implementation |
| `reflections` | Personal observations outside an existing family; warm gray | `#786C62` / `120, 108, 98` | 0.62 | 0.07 | 0.14 | Reserved for future implementation |

Preserve the established family for existing series. Do not recolor history, learning, or systems articles merely because their source happens to be a book. Navigation groups and visual skins need not be identical: a future Reading filter may contain several established visual families.

Reserved families are selected defaults for future work, not active CSS selectors. Before assigning one to a card, implement its tokens in the shared stylesheet, choose and register its series pattern, and check light/dark and narrow/wide layouts. Never rely on the generic fallback as if the reserved color were already implemented.

Color supports recognition; visible text carries the meaning. Keep text contrast independently readable, and avoid full-card saturated fills.

### Texture geometry — implemented

All Persona card textures use the shared `::before` rule in [page-intro.css](../assets/css/extended/page-intro.css):

```css
position: absolute;
right: 0;
bottom: 0;
width: min(32%, 10rem);
height: 5.5rem;
max-height: 50%;
pointer-events: none;
opacity: 0.55;
```

- Keep textures confined to the lower-right corner. Do not restore `inset: 0` or stretch linework across the card.
- The width is capped at both 32% of the card and 10rem; height is capped at both 5.5rem and half the card height. These caps apply on mobile too.
- The pattern uses `--skin-line` and `--skin-soft`; its pseudo-element opacity further softens those colors. Do not replace them with opaque artwork.
- Keep `overflow: hidden` on the card, content above the texture, and decoration non-interactive. It must not block links or tag buttons.
- Keep the 4px left accent and existing subtle background wash. The corner restriction applies to linework, not the restrained color wash.
- Favor static linework. Do not introduce animated or full-card effects as part of routine publication.

### Existing series-pattern registry

| `data-series` | Visible identity | Skin | Pattern |
| --- | --- | --- | --- |
| `palantir` | Palantir | `systems` | `systems-grid` |
| `ai-education` | AI Education | `learning` | `learning-lines` |
| `guns-germs-and-steel` | Guns, Germs, and Steel | `history` | `history-strata` |
| `irresistible` | Irresistible | `reading` | `stopping-gaps` |
| `power-of-now` | The Power of Now | `reading` | `present-rings` |
| `before-departure-after-arrival` | The Alchemist · Before Departure, After Arrival | `reading` | `alchemist-path` |
| `scale-in-ai-age` | Scale · Scale in the AI Age | `reading` | `scale-network` |

### Reading pages

Keep the shared Persona reading layout: English-default card links, Back to Persona and the language toggle in the top action area, a book/topic kicker where useful, subtitle/dek, thin opening divider, first-paragraph drop cap, and strata separators before major sections. Keep series decoration on cards; do not spread it behind article text. Start from the [Persona template](../content/persona/_template.md).

## Notes and Projects presentation

Projects foreground contribution and artifacts through the shared Project header and highlights. Notes foreground a clear question and a concise description. Do not copy Persona's decorative series textures onto these sections by default, and do not make tools such as Python or Tableau the primary organizing principle for all work.

New classifications should help readers find material across the whole section, including paginated content. A topic control must not imply a global search while filtering only the current page.

### Topic filters and summaries — implemented

- Every published Note and Project defines a single visible `topic` in frontmatter, separate from its up-to-three `tags`.
- Notes use Clinical Data & Evaluation / Statistics & Modeling / Data & Computing Systems / AI & Research Methods.
- Projects use Clinical & Health / Environment & Energy / Data Products & Tools.
- Section topic controls are generated from published content. Cards display their primary topic; keyword buttons continue to filter by visible tags without silently widening their meaning.
- Notes and Projects render their complete, date-descending collections on one index page so both topic and keyword filters cover the entire section. Revisit the loading strategy if the collections become large; preserve complete filtering when doing so. The old `/blogs/page/2/` URL redirects to `/blogs/`.
- Use the authored `description` for Note and Project card summaries. Fall back to an automatic summary only when no description exists.

### Mathematics and series navigation — implemented

- Write inline math as `\(...\)` and display math as `$$...$$` or `\[...\]`. Single dollar signs remain ordinary text, avoiding accidental currency parsing.
- Hugo renders math to MathML at build time through the passthrough hook. Invalid formulas fail the build; no client-side math library is required. Verify actual equations in the browser after changes.
- Register numbered Persona series in `data/persona_series.yaml`, listing only published English source paths, their order, and the planned total. Paired Chinese pages are resolved by the shared navigation partial.
- The series directory follows part order, identifies the current article, and marks missing parts as not yet published without exposing draft titles or linking to drafts. Incomplete series cards also state which parts are available; update that status when another part is published.

## Proposed organization — not yet implemented or finalized

These are planning options, not instructions to migrate content or change navigation:

- Persona: Reading / Environment & Everyday Life / Reflections, with technology and society retained as topic labels where useful. Final grouping and naming remain open.
- Notes may become either evolving topical notes or self-contained essays; the author has not yet selected a uniform editorial model. Do not force either structure.
- Search and curated cross-section reading paths remain future work. The topic filtering, mathematics, and numbered-series navigation described above are implemented.

## Before publication or visual changes

1. Confirm section placement, audience, source status, and existing companion articles.
2. For Persona, consult the color and series registries. Reuse an existing series identity or register a deliberate new one.
3. Check language links, at most three aligned tags, dates, public series order, and readable labels.
4. For card-style changes or new patterns, inspect desktop and mobile, light and dark; verify no overflow, obstructed text, or blocked controls.
5. Build Hugo into a temporary destination and inspect the actual rendered route. Follow AGENTS.md for sensitivity review and narrow Git delivery.

Keep this document, the Persona template, shared CSS, and card metadata consistent. Update the status of reserved styles only after implementation and verification.
