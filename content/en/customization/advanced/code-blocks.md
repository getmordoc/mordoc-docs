---
title: Code Blocks
description: Style the colors, header, and copy button of a fenced code block.
---

Code Block wraps every fenced code block in your Markdown content. See [Markdown Basics](/writing-content/markdown-basics). This page covers its colors, header bar, border, and copy button.

## Open the override file

```text
config/styles/code-block.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--cb-bg`
* Background of the header bar showing the language name: a darker grey than the code.
---
* `--cb-code-bg`
* Background of the code itself: light in light mode, dark in dark mode.
---
* `--cb-fg`
* Color of code that is not highlighted.
---
* `--cb-fg-muted`
* Color of the language name and the copy button.
---
* `--cb-hover-bg`
* Background of the copy button on hover.
---
* `--cb-border`
* Border around the whole block and under the header bar. Defaults to `--color-border`.
---
* `--cb-token-comment`, `--cb-token-punctuation`, `--cb-token-constant`, `--cb-token-string`, `--cb-token-operator`, `--cb-token-keyword`, `--cb-token-function`, `--cb-token-variable`
* Highlight colors for comments, punctuation, constants and numbers, strings, operators, keywords, functions, and variables. Mordoc sets one group for light mode and one for dark mode; choose colors that are easy to read on `--cb-code-bg`.
---
* `--cb-radius`
* Corner radius of the whole block.
---
* `--cb-copy-button-radius`
* Corner radius of the copy button.
{% /table %}

## Example code-block.css

A `config/styles/code-block.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --cb-bg: #eeeeee;
  --cb-code-bg: #fafafa;
  --cb-fg: #1f2328;
  --cb-fg-muted: #59636e;
  --cb-hover-bg: rgba(0, 0, 0, 0.06);
  --cb-border: #e5e5e5;
  --cb-radius: 6px;
  --cb-copy-button-radius: 4px;

  --cb-token-comment: #59636e;
  --cb-token-punctuation: #1f2328;
  --cb-token-constant: #0550ae;
  --cb-token-string: #0a3069;
  --cb-token-operator: #8250df;
  --cb-token-keyword: #c62828;
  --cb-token-function: #673ab7;
  --cb-token-variable: #953800;
}

.dark {
  --cb-bg: #121212;
  --cb-code-bg: #1e1e1e;
  --cb-fg: #eceff1;
  --cb-fg-muted: #a1a1aa;
  --cb-hover-bg: rgba(255, 255, 255, 0.08);
  --cb-border: #2e2e2e;

  --cb-token-comment: #8b949e;
  --cb-token-punctuation: #cdd9e5;
  --cb-token-constant: #79c0ff;
  --cb-token-string: #7ee787;
  --cb-token-operator: #d2a8ff;
  --cb-token-keyword: #ff7b72;
  --cb-token-function: #d29922;
  --cb-token-variable: #ffa657;
}
```

You don't need to set every token like this example does. Add only the ones you actually want to change; every token left out keeps Mordoc's default.

## Next step

- [Style diagrams](/customization/advanced/diagrams).
