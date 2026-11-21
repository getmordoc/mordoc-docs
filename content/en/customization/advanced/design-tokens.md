---
title: Design Tokens
description: Override the global color tokens every component falls back to, beyond the accent color.
---

[Basic customization](/customization/basic/theme-css) covers `--accent`, the one color almost every site changes. The same file, `config/styles/theme.css`, also holds a small set of other global tokens: the colors every component falls back to unless it sets its own.


## Open the theme file

```text
config/styles/theme.css
```

Add only the tokens you want to change, inside `:root`:

```css
:root {
  --color-bg: #fbfaf7;
  --color-border: #e8e3d8;
}
```

## Surfaces and text

{% table %}
* Token
* What it controls
---
* `--color-bg`
* The page background, behind everything.
---
* `--color-surface`
* A subtly different background used for raised or recessed panels: the search modal's input row, table headers in your written content, and similar interface elements.
---
* `--color-border`
* Hairline borders used throughout the site: panel edges, dividers, the line under the header.
---
* `--color-fg`
* Primary text throughout the interface: headings, navigation labels, buttons.
---
* `--color-content-fg`
* Article body text specifically: Markdown paragraphs and list text. Kept separate from `--color-fg` so you can tune heading contrast and reading-copy contrast independently.
---
* `--color-fg-muted`
* Secondary or meta text, and muted icons: descriptions, timestamps, breadcrumbs, placeholder text.
---
* `--color-bg-hover`
* Background shown on hover for interactive rows: dropdown items, menu buttons, and similar controls that aren't links or buttons.
{% /table %}

## Dark mode

Override any of these again inside `.dark` for a value that only applies in dark mode:

```css
:root {
  --color-bg: #fbfaf7;
}

.dark {
  --color-bg: #14120f;
}
```

## Example theme.css

An example with all the tokens that you can set in `theme.css` for both light and dark mode:

```css
:root {
  --accent: #b45309;

  --color-bg: #fbfaf7;
  --color-surface: #f2ede4;
  --color-border: #e8e3d8;

  --color-fg: #211f1a;
  --color-content-fg: #3a362e;
  --color-fg-muted: #7a7266;

  --color-bg-hover: #efe9de;
}

.dark {
  --accent: #f0a659;

  --color-bg: #14120f;
  --color-surface: #1d1a15;
  --color-border: #2c281f;

  --color-fg: #f3efe6;
  --color-content-fg: #d8d2c4;
  --color-fg-muted: #948c7c;

  --color-bg-hover: #221f19;
}
```

## Next step

- [Customize the app layout](/customization/advanced/app-layout).
