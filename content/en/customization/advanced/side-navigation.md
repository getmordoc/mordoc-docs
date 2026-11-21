---
title: Side Navigation
description: Style the colors and weight of the side navigation, inside the Sidenav Area box.
---

This page is about **appearance**: `config/styles/sidenav.css`. To add, remove, or nest the navigation items themselves, see [Side Navigation](/configuration/side-navigation) under Configuration instead.

Side Navigation renders inside the Sidenav Area box from [App Layout](/customization/advanced/app-layout), which owns the box's placement, width, and background. This file only styles the rows inside it: categories, group labels, links, and the active state.

Each top-level group is a category: its title is in capitals, with space above it. A thin line above each category can be turned on with `--sidenav-category-divider-style`.

## Open the override file

```text
config/styles/sidenav.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--sidenav-row-radius`
* Corner radius shared by every row type: group labels and links.
---
* `--sidenav-fg`
* Text color of links and linked group labels.
---
* `--sidenav-fg-muted`
* Color of the expand/collapse chevron.
---
* `--sidenav-category-fg`
* Text color of a category title. Defaults to `--sidenav-fg`.
---
* `--sidenav-category-font-weight`
* Font weight of a category title.
---
* `--sidenav-category-divider-style`
* Whether the thin line above each category shows: `none` by default, so only the space between categories shows; `solid` shows the line, and `dashed` or `dotted` work too.
---
* `--sidenav-category-divider-color`
* Color of that line, when it shows. Defaults to `--color-border`.
---
* `--sidenav-group-label-fg`
* Text color of a nested group label that only toggles, inside a category.
---
* `--sidenav-hover-bg`
* Background shown on hover for any row.
---
* `--sidenav-active-fg`
* Text color of the current page's link.
---
* `--sidenav-active-bg`
* Background of the current page's link: a light tint of the accent color by default.
---
* `--sidenav-font-weight`
* Font weight of links and group labels.
---
* `--sidenav-active-font-weight`
* Font weight of the current page's link.
{% /table %}

```css
:root {
  --sidenav-active-fg: #0f766e;
  --sidenav-active-bg: #ecfdf5;
}
```

{% callout type="note" title="Shape and size are intentionally fixed" %}
Row padding, row height, and font size are not exposed as tokens. Mordoc keeps those fixed so the sidebar reads consistently across every site rather than needing to be independently tuned. Only color and font weight are customizable here.
{% /callout %}

## Example sidenav.css

A `config/styles/sidenav.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --sidenav-row-radius: 6px;
  --sidenav-fg: #383838;
  --sidenav-fg-muted: #666666;
  --sidenav-group-label-fg: rgba(56, 56, 56, 0.7);
  --sidenav-hover-bg: #efefef;
  --sidenav-active-fg: #0f766e;
  --sidenav-active-bg: #ecfdf5;
  --sidenav-font-weight: 400;
  --sidenav-active-font-weight: 600;
  --sidenav-category-fg: #383838;
  --sidenav-category-font-weight: 600;
  --sidenav-category-divider-style: solid;
  --sidenav-category-divider-color: #e0e0e0;
}

.dark {
  --sidenav-fg: #d4d4d4;
  --sidenav-category-fg: #d4d4d4;
  --sidenav-category-divider-color: #2e2e2e;
  --sidenav-fg-muted: #9e9e9e;
  --sidenav-group-label-fg: rgba(214, 214, 214, 0.7);
  --sidenav-hover-bg: #1f1f1f;
  --sidenav-active-fg: #2dd4bf;
  --sidenav-active-bg: #0f2e2b;
}
```

## Next step

- [Style the content layout](/customization/advanced/content-layout).
