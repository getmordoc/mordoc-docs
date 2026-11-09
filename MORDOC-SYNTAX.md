# Mordoc Content Syntax Reference

This file describes the Mordoc-specific syntax used in content files. Read this when writing, editing, or discussing English content.

For rules on translating content into other languages, see `TRANSLATE.md` instead — that file covers what to translate/preserve and references this one for tag mechanics.

## Frontmatter

Every page starts with a YAML frontmatter block between `---` delimiters.

```markdown
---
title: My Page Title
description: A short description of the page.
layout: landing
---
```

**Fields:**
- `title` — required on every page.
- `description` — optional.
- `layout: landing` — optional flag marking a landing page.

## Variables

Variables are defined in `config/variables.yaml` and referenced in content with double curly braces.

**In body text:**
```markdown
Welcome to {% $productName %}.
```

**In link tags:**
```markdown
{% link path=$SUPPORT_PORTAL_URL %}Contact support{% /link %}
```

**In image tags:**
```markdown
{% image src=$IMAGE_LINK alt="Artwork" /%}
```

## Tags (Markdoc Components)

Mordoc uses Markdoc-style tags: `{% tagName attr="value" %}` ... `{% /tagName %}`.

---

### Callout

Highlights important messages. `type` is one of `note`, `tip`, `warning`, `danger`.

```markdown
{% callout type="note" title="Good to know" %}
Body text here.
{% /callout %}
```

**Attributes:** `type` (keyword: `note`/`tip`/`warning`/`danger`), `title` (text).

---

### Table

Mordoc's custom table syntax (different from standard Markdown tables).

```markdown
{% table %}
* Header 1
* Header 2
---
* Row 1, Cell 1
* Row 1, Cell 2
---
* Row 2, Cell 1
* Row 2, Cell 2
---
{% /table %}
```

Each `*` is a cell; `---` separates rows. Cells can contain nested content (callouts, code blocks, lists, images).

---

### Card and Card Grid

```markdown
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" icon="/icons/start.svg" tag="Start here" %}
Card body text here.
{% /card %}
{% /cardGrid %}
```

**`cardGrid` attributes:** `cols` (number of columns).
**`card` attributes:** `title` (text), `path` (route), `icon` (asset path), `tag` (short text label).

---

### Hero

Used at the top of landing pages.

```markdown
{% hero
  title="My Product Docs"
  titleAccent="made simple"
  description="Find guides and examples."
  background="/images/hero.png"
%}
{% button path="/getting-started" %}
Get started
{% /button %}
{% /hero %}
```

**Attributes:** `title`, `titleAccent`, `description` (text), `image` (asset path, a supporting image shown below the CTAs), `background` (asset path only, never a color). Colors are not attributes: title, title-accent, and description color are all set once in `Hero.module.css`'s tokens (`--hero-title-color`, etc.), not per-instance in Markdown.

---

### Section

Groups content on landing pages.

```markdown
{% section title="Everything you need" background="/images/section-bg.png" %}
Body text here.
{% /section %}
```

**Attributes:** `title` (text), `background` (asset path only, never a color; a solid background color is set once in `Section.module.css`'s `--section-bg` token, not per-instance in Markdown).

---

### Button

```markdown
{% button path="/getting-started" %}
Get started
{% /button %}

{% button path="/learn-more" variant="secondary" %}
Learn more
{% /button %}
```

**Attributes:** `path` (route), `variant` (`primary`/`secondary`).

---

### Clip

Muted, looping demo clip with a click-to-play/pause toggle — the recommended replacement for animated GIFs in content (autoplaying GIFs can't be paused, which fails WCAG 2.2.2).

```markdown
{% clip src="/videos/demo.mp4" thumbnail="/images/demo-thumb.jpg" title="Creating a project" alt="Demo of creating a new project" /%}
```

**Attributes:** `src` (asset path, required — the video file itself), `thumbnail` (asset path, shown paused before the reader clicks play), `title` (text, rendered as a caption below the clip), `alt` (text, accessible label for the play/pause toggle button). Self-closing — no body content.

---

### Video Embed

Embeds a video hosted on YouTube, Vimeo, or Loom (as opposed to `clip`'s self-hosted file). `src` is the video's ordinary public page URL, in whatever shape a reader would paste from their browser (`youtube.com/watch?v=...`, `youtu.be/...`, `vimeo.com/...`, `loom.com/share/...`). An unrecognized host, or a URL with no extractable video ID, falls back to a link-out card instead of a broken embed.

```markdown
{% videoEmbed src="https://youtu.be/dQw4w9WgXcQ" title="Product walkthrough" /%}
```

**Attributes:** `src` (URL, required), `title` (text, rendered as a caption below the embed), `alt` (text, overrides the accessible label — otherwise the provider name or `title` is used), `thumbnail` (asset path — only used on the fallback link-out card, when `src` isn't a recognized provider), `aspectRatio` (e.g. `"4 / 3"`, `"9 / 16"` — overrides the default 16:9 box; mainly needed for Loom). Self-closing — no body content.

---

### Accordion and Accordions

`accordion` is a single collapsible section: `title` drives the clickable header, and the body accepts the same broad content model as `section` (headings, paragraphs, lists, code blocks, images, other tags — even a nested accordion).

```markdown
{% accordion title="What is Mordoc?" %}
Body text here.
{% /accordion %}
```

**`accordion` attributes:** `title` (text, required), `defaultOpen` (boolean, default `false` — written unquoted, e.g. `defaultOpen=true`).

`accordion` works standalone, or grouped inside `accordions` for a visually connected block with coordinated open/close behavior:

```markdown
{% accordions %}
{% accordion title="First question" %}
Answer.
{% /accordion %}
{% accordion title="Second question" %}
Answer.
{% /accordion %}
{% /accordions %}
```

`accordions` has no attributes — it always makes the group exclusive, closing any other open item when one opens.

---

### Column and Columns

`columns` lays out its `column` children side by side, equal width, collapsing to a single stacked column on narrow viewports. It's an ordinary block-level tag — normal content, then a `columns` block, then normal content again, all work.

```markdown
{% columns divider=true %}
{% column %}
Left column content.
{% /column %}
{% column %}
Right column content.
{% /column %}
{% /columns %}
```

**`columns` attributes:** `divider` (boolean, default `false` — written unquoted, draws a vertical rule between columns). Column count follows however many `column` children are nested; there's no `cols` attribute to keep in sync.
**`column` attributes:** none — body accepts the same broad content model as `section`/`accordion`.

---

## Diagrams (`sequence-diagram` code blocks)

Fenced blocks tagged `sequence-diagram` hold diagram DSL, not literal code.

```
actor <id> [as "<label>"] [icon=<path>]
<from> -> <to>: <message text>
<from> --> <to>: <message text>
# comment text
```

- `actor <id> as "<label>" icon=<path>` declares a participant.
- `->` is a synchronous message, `-->` a response/async message.
- `\n` inside message text is a line break within the diagram bubble.
- `#` starts a comment.

Example:
```
actor frodo as "Frodo" icon=/icons/frodo.svg
frodo -> gandalf: I will take it,\nthough I do not know the way
```

Note: the default monospace font renders `->` with ligatures as a single arrow glyph — when writing example code elsewhere that shows arrow syntax, consider spelling out the style in words to avoid confusion.

---

## Navigation Files

Depending on the project, navigation files may include:

- `config/navigation/sidenav.yaml` — single site-wide sidebar (used when `topnav.yaml` does **not** exist)
- `config/navigation/topnav.yaml` — optional; when present, replaces `sidenav.yaml` with per-area sidenav files
- `config/navigation/headernav.yaml` — optional header links
- `config/navigation/footer.yaml` — optional footer columns (see Footer, below)
- Custom per-area sidenav files referenced from `topnav.yaml` (e.g., `config/navigation/field-manual.yaml`, `config/navigation/ship-systems.yaml`)

When `topnav.yaml` exists there is **no** `sidenav.yaml` — labels live in `topnav.yaml` and all custom sidenav files it references via the `sidenav:` field.

Each navigation entry has a `label` (display text), `path` (route), and may have `variant` or `expanded` flags.

An entry can instead use `operation: <operationId>` to link a generated API page (see API Reference, below). `label` is then optional and falls back to the operation's `summary`. An entry must not combine `operation` and `path`.

## API Reference

Mordoc generates one page per operation from OpenAPI specs. The spec is the source of truth; enrichment files only patch text or add things OpenAPI cannot express (badges, callouts).

**Project layout:**

```text
config/api.yaml                          registers specs
api/specs/<file>.yaml                    OpenAPI files, never hand-edited
api/enrichment/<id>/operations/<operationId>.md
api/enrichment/<id>/schemas/<SchemaName>.md
api/examples/<id>/<operationId>/request.<case>.json
api/examples/<id>/<operationId>/response.<status>[-suffix].json
```

**`config/api.yaml`:** a list of `id` (required, letters/digits/hyphens/underscores), `spec` (required, file in `api/specs/`), and optional `routePrefix` (default `/api/<id>`; `/` mounts at the site root). To use `strict: true` (every warning fails the build), move the list under `specs:`.

```yaml
- id: rings
  spec: rings.yaml
```

**Sidenav entry:**

```yaml
- label: Forge
  operation: forgeRing
```

### Params (enrichment files only)

`params` wraps field entries in an enrichment file. Do not use it in ordinary guide pages. Each `###` heading names a field; the text under it is the note.

```markdown
{% params %}
### smith_id
Must belong to a registered smith.
{% /params %}

{% params in="response" status="403" %}
### message
Explains which rule was broken.
{% /params %}
```

**Attributes:** `in` (`request` default, or `response`), `status` (text; required when `in="response"`), `mode` (`append` default, or `replace`). Use a dotted path for nested fields in operation files (`quest.destination`). In `schemas/` files the `params` wrapper is optional. Text outside `params` in an operation file replaces the operation's description.

### Badges

A badge is an annotation on a `###` heading in an enrichment file. One per entry; the value must be quoted text.

```markdown
### dark_lord_approval {% badge="conditional" %}
### corruption_level {% badge="Read-only" %}
```

`conditional` is reserved (the field needs an explanation in its description, or the build warns). Any other text is a free badge, shown verbatim in one style.

## Footer

`config/navigation/footer.yaml` is optional. When absent, Mordoc renders its own built-in default footer (a single "Powered by Mordoc" attribution line). When present, it replaces that default with up to three named columns, each an ordered list of lines:

```yaml
start:
  - "[Privacy policy](/privacy)"
  - Powered by [Mordoc](https://mordoc.dev)
center:
  - "[Support](/support)"
end:
  - "© 2026 Acme Inc."
```

**Keys:** `start`, `center`, `end` — all optional, rendered left-to-right in that order as stacked columns (writing-direction-relative, not `left`/`right`). An explicit empty file, or a file with no/all-empty zones, means the author wants no footer at all — distinct from the file being absent.

**Line syntax:** each line is plain text, optionally containing one `[text](url)` link run — everything outside the brackets renders as plain text, the bracketed part as a link. External URLs (`http://`, `https://`, `//`) open in a new tab; anything else is treated as an internal route. A line starting with an unquoted `[` must be quoted (`- "[text](url)"`) since YAML would otherwise read it as a list.

Footer lines are translated the same way navigation labels are — see `TRANSLATE.md`.

## Languages

`config/language.json` lists every language the site supports (default/source language plus targets). Content for a non-default language `<lang>` lives under `content/<lang>/...`, mirroring the same relative paths as `content/en/`.
