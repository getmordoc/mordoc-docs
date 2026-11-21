---
title: Content Layout
description: Style the content area's own layout skeleton, both the article, TOC, footer grid and the full-width landing layout.
---

Content renders inside the Content Area box from [App Layout](/customization/advanced/app-layout). It owns one more level of layout: which of two skeletons a page uses, and where the table of contents and footer sit within it.

**Article pages** use a two-column grid, with the footer spanning only under the article column:

```text
┌───────────────────────────────────┬──────────────┐
│                                   │              │
│           Article                 │     TOC      │
│                                   │              │
├───────────────────────────────────┤              │
│              Footer               │              │
└───────────────────────────────────┴──────────────┘
```

**Landing pages** (`layout: landing` in frontmatter) use the full width instead, with no TOC column:

```text
┌──────────────────────────────────────────────────────┐
│                                                      │
│                   Hero / Sections                    │
│                                                      │
├──────────────────────────────────────────────────────┤
│                        Footer                        │
└──────────────────────────────────────────────────────┘
```

The TOC column also disappears below the `1280px` breakpoint on article pages, leaving just the article and footer stacked full width.

## Open the override file

```text
config/styles/content.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--toc-width`
* Width of the TOC column on article pages. Defaults to `16rem`.
---
* `--article-max-width`
* Maximum width of the article reading column. Also used by the 404 page and the loading skeleton, so they always match the real article's width.
{% /table %}

```css
:root {
  --article-max-width: 48rem;
}
```

{% callout type="note" title="404 page and loading placeholder" %}
The not-found page reuses `--article-max-width` above and the global color tokens from [Design Tokens](/customization/advanced/design-tokens); it has no tokens of its own. The shimmering placeholder shown while a page loads also reuses `--article-max-width`, and has two color tokens of its own in `config/styles/skeleton.css`: `--skeleton-bg` for the grey bars and `--skeleton-highlight` for the lighter band that moves across them.
{% /callout %}

## Example content.css

A `config/styles/content.css` that sets every token on this page. Neither is a color, so there's no separate dark-mode variant to set:

```css
:root {
  --toc-width: 18rem;
  --article-max-width: 48rem;
}
```

## Next step

- [Style the article page](/customization/advanced/article-page).
