---
title: Search
description: Style the search bar in the header and the full-screen search modal it opens.
---

Search is one feature split across two files, because it's two different pieces of UI: the bar sitting in the header, and the full-screen modal it opens.

```text
┌───────────────────┐        ┌─────────────────────────────┐
│ 🔍 Search..   ⌘K │  --->  │ 🔍 [type to search...]  ✕  │
└───────────────────┘        ├─────────────────────────────┤
     Search Bar              │  Result title               │
                             │  matching excerpt…          │
                             │  Result title               │
                             │  matching excerpt…          │
                             └─────────────────────────────┘
                                     Search Modal
```

## Search Bar

```text
config/styles/search-bar.css
```

{% table %}
* Token
* What it controls
---
* `--search-bar-width`
* Width of the bar on desktop. Narrower by default at the `768px` breakpoint than at `1024px` and up.
---
* `--search-bar-height`
* Height of the bar.
---
* `--search-bar-radius`
* Corner radius of the bar.
---
* `--search-bar-padding`
* Horizontal padding inside the bar.
---
* `--search-bar-gap`
* Gap between the icon, placeholder text, and keyboard shortcut hint.
---
* `--search-bar-font-size`
* Font size of the placeholder text.
---
* `--search-bar-icon-size`
* Size of the search icon.
---
* `--search-bar-bg`
* Bar background.
---
* `--search-bar-bg-hover`
* Bar background on hover.
---
* `--search-bar-border`
* Bar border color.
---
* `--search-bar-border-hover`
* Bar border color on hover. Defaults to a translucent tint of `--accent`.
---
* `--search-bar-fg`
* Icon and placeholder text color.
---
* `--search-bar-kbd-height`
* Height of the `⌘K`-style keyboard shortcut chip.
---
* `--search-bar-kbd-padding`
* Horizontal padding of the shortcut chip.
---
* `--search-bar-kbd-font-size`
* Font size of the shortcut chip.
---
* `--search-bar-kbd-radius`
* Corner radius of the shortcut chip.
---
* `--search-bar-kbd-bg`
* Background of the shortcut chip.
{% /table %}

## Search Modal

```text
config/styles/search-modal.css
```

{% table %}
* Token
* What it controls
---
* `--modal-max-width`
* Maximum width of the modal panel.
---
* `--modal-overlay-bg`
* Backdrop behind the modal.
---
* `--modal-bg`
* Modal panel background. Defaults to `--color-bg`.
---
* `--modal-border`
* Modal panel border. Defaults to `--color-border`.
---
* `--modal-shadow`
* Drop shadow under the modal panel.
---
* `--modal-radius`
* Corner radius of the modal panel.
---
* `--modal-input-size`
* Font size of the search input.
---
* `--modal-result-radius`
* Corner radius of each result row.
---
* `--modal-result-hover`
* Background of a result row on hover. Defaults to `--color-bg-hover`.
---
* `--modal-result-selected`
* Background of the keyboard-selected result row.
---
* `--modal-kbd-radius`
* Corner radius of the small inline chips used for the `Esc` hint and matched keywords.
{% /table %}

## Example search-bar.css

A `config/styles/search-bar.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --search-bar-width: 256px;
  --search-bar-height: 36px;
  --search-bar-radius: 999px;
  --search-bar-padding: 12px;
  --search-bar-gap: 8px;
  --search-bar-font-size: 14px;
  --search-bar-icon-size: 16px;
  --search-bar-bg: #ffffff;
  --search-bar-bg-hover: #f5f5f5;
  --search-bar-border: #e0e0e0;
  --search-bar-border-hover: color-mix(in oklch, #0d9488 30%, transparent);
  --search-bar-fg: #616161;
  --search-bar-kbd-height: 20px;
  --search-bar-kbd-padding: 6px;
  --search-bar-kbd-font-size: 10px;
  --search-bar-kbd-radius: 4px;
  --search-bar-kbd-bg: #ffffff;
}

.dark {
  --search-bar-bg: #121212;
  --search-bar-bg-hover: #242424;
  --search-bar-border: #383838;
  --search-bar-fg: #9e9e9e;
  --search-bar-kbd-bg: #1e1e1e;
}
```

## Example search-modal.css

A `config/styles/search-modal.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --modal-max-width: 640px;
  --modal-overlay-bg: rgba(0, 0, 0, 0.45);
  --modal-bg: #ffffff;
  --modal-border: #e5e5e5;
  --modal-shadow: 0 24px 64px rgba(0, 0, 0, 0.22);
  --modal-radius: 16px;
  --modal-input-size: 16px;
  --modal-result-radius: 8px;
  --modal-result-hover: #f3f4f6;
  --modal-result-selected: #f0fdfa;
  --modal-kbd-radius: 4px;
}

.dark {
  --modal-overlay-bg: rgba(0, 0, 0, 0.65);
  --modal-bg: #161616;
  --modal-border: #2e2e2e;
  --modal-result-hover: #242424;
  --modal-result-selected: #0f2e2b;
}
```

## Next step

- [Style the side navigation](/customization/advanced/side-navigation).
