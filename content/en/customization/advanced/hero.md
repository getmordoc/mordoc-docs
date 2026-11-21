---
title: Hero
description: Style the default background and text colors for the hero banner on landing pages.
---

Hero renders at the top of a landing page. See [Landing Pages](/writing-content/landing-pages) for the Markdown syntax. Every color it uses is a site-wide design decision set here in CSS; the `{% hero %}` tag itself has no color attributes of its own.

## Open the override file

```text
config/styles/hero.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--hero-bg`
* Solid background color, used when a hero has no `background` image. Defaults to `#f5f5f5`, and `#1e1e1e` in dark mode: a little darker than the header.
---
* `--hero-title-color`
* Title text color. Defaults to `--color-fg`.
---
* `--hero-title-accent-color`
* Color of the title's accent line (`titleAccent` in Markdown).
---
* `--hero-desc-color`
* Description text color. Defaults to `#616161` in light mode, so it stays readable on the hero background, and `--color-fg-muted` in dark mode.
---
* `--hero-image-radius`
* Corner radius of a hero's foreground image, if it has one.
---
* `--hero-image-shadow`
* Drop shadow under that foreground image.
{% /table %}

## Example hero.css

A `config/styles/hero.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --hero-bg: #f8fafc;
  --hero-title-color: #1c1c1c;
  --hero-title-accent-color: #0f766e;
  --hero-desc-color: #6b7280;
  --hero-image-radius: 10px;
  --hero-image-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
}

.dark {
  --hero-bg: #0f172a;
  --hero-title-color: #ebebeb;
  --hero-title-accent-color: #2dd4bf;
  --hero-desc-color: #9ca3af;
}
```

## Next step

- [Style sections](/customization/advanced/sections).
