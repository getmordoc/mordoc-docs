---
title: App Layout
description: Style the header, side navigation, and content area boxes that make up every Mordoc page.
---

Every page in a Mordoc site is built from the same three boxes. `config/styles/app.css` styles those boxes' placement, background, and border, without touching what's inside them.

```text
┌────────────────────────────────────────────────┐
│                  Header Area                   │
├────────────────┬───────────────────────────────┤
│                │                               │
│  Sidenav Area  │        Content Area           │
│                │                               │
│                │                               │
└────────────────┴───────────────────────────────┘
```

* **Header Area**: sticky across the top of every page.
* **Sidenav Area**: the side navigation, to the left of the content on desktop, off-canvas on mobile.
* **Content Area**: everything else, the article, its table of contents, and the footer.

What goes inside each box is its own component's job. This page only covers the box itself. See [Header](/customization/advanced/header), [Side Navigation](/customization/advanced/side-navigation), and [Content Layout](/customization/advanced/content-layout) for what's drawn inside each one.

## Open the override file

```text
config/styles/app.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--header-area-bg`
* Background of the Header Area box. Light grey by default: `#fafafa`, and `#272727` in dark mode.
---
* `--sidenav-area-bg`
* Background of the Sidenav Area box.
---
* `--sidenav-area-width`
* Width of the Sidenav Area box on desktop. Defaults to `16rem`.
{% /table %}


## Example app.css

A `config/styles/app.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --header-area-bg: #ffffff;
  --sidenav-area-bg: #ffffff;
  --sidenav-area-width: 18rem;
}

.dark {
  --header-area-bg: #0d0d0d;
  --sidenav-area-bg: #0d0d0d;
}
```

## Next step

- [Style the Header](/customization/advanced/header).
