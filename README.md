# Hairong's Portfolio

Hugo source for [hwcmu.github.io](https://hwcmu.github.io/), using the PaperMod theme.

## Find content

| Website area | Source | Local unpublished drafts | Public URL |
| --- | --- | --- | --- |
| Home | `content/_index.md` | — | `/` |
| Projects | `content/projects/` | `content/projects/drafts/` | `/projects/` |
| Notes / Blogs | `content/notes/` | `content/notes/drafts/` | `/blogs/` |
| Papers | `content/publications.md` | — | `/publications/` |
| CV | `content/cv.md` | — | `/cv/` |
| Persona | `content/persona/` | `content/persona/drafts/` | `/persona/` |

**Blogs files live in `content/notes/`, not `content/blogs/`.** The Notes section retains the `/blogs/` public URL. Individual articles can define their own URL, so check their frontmatter before renaming or moving them.

Published articles are edited in place. Their earlier unpublished versions are not kept as separate draft files by default; use Git history for earlier committed versions. The `drafts/` folders contain unpublished work, rather than copies of every published article.

## Folder map

| Path | Purpose |
| --- | --- |
| `content/` | Pages, articles, section indexes, and article templates |
| `assets/css/` | Custom site styles processed by Hugo |
| `layouts/` | Shared page layouts and partials overriding the theme |
| `static/images/` | Deliberately published images |
| `static/docs/` | Deliberately published document assets |
| `static/` | Other public assets copied to the website |
| `themes/PaperMod/` | Theme Git submodule |
| `archetypes/` | Hugo content-generation defaults |
| `data/`, `i18n/` | Hugo data and translation directories; currently empty |
| `hugo.yml` | Site configuration and main navigation |
| `.github/workflows/hugo.yaml` | Build and deploy `main` to GitHub Pages |
| `AGENTS.md` | Repository maintenance and publication rules |
| `local-assets/persona/` | Local working originals for Persona series; ignored by Git |
| `.private/` | Local private files and content inventory; ignored by Git |
| `public/` | Generated website output; ignored by Git |
| `resources/_gen/` | Generated Hugo resources; ignored by Git |
| `.code-review-graph/` | Local code-review tool data |

## Drafts and publication

Only the `_index.md` marker in each `drafts/` directory is tracked. Draft contents are ignored by Git, and the markers cascade `draft: true` and disable rendering and listing. Local drafts therefore need their own backup; pushing this repository does not back them up.

For a new Project or Persona article, start from its section's `_template.md`. New Project and Note drafts require `provenanceStatus` and `provenanceSources`; see `AGENTS.md` for the evidence requirements and publication checks. Publish a ready draft by moving it into the published section and completing the relevant publication checks.

A local file inventory, including unpublished filenames and Notes source-to-URL mappings, is kept at `.private/content-inventory.md`. It is not part of this public repository.

## Preview and verify

Initialize the theme after cloning:

```sh
git submodule update --init --recursive
```

Use Hugo extended v0.152.2 to match the deployment workflow:

```sh
hugo server
hugo list published
```

Build into a temporary directory without refreshing local `public/` output:

```sh
build_dir=$(mktemp -d "${TMPDIR:-/tmp}/portfolio-build.XXXXXX")
HUGO_RESOURCEDIR="$build_dir/resources" hugo --minify --destination "$build_dir/site" --cacheDir "$build_dir/cache"
```

The draft section markers keep drafts hidden even when `hugo server -D` is used. Review draft Markdown directly while it remains in those directories.
