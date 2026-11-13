---
title: Advanced Images
description: Style the caption and the larger view of advanced images.
---

An advanced image shows a caption and opens larger on click. See [Advanced Images](/writing-content/advanced-images) for the Markdown syntax. This page covers its appearance.

## Open the override file

```text
config/styles/image.css
```

Advanced images and [images](/customization/advanced/images) are styled in this same file, and share `--image-radius` and `--image-shadow`.

## Tokens

{% table %}
* Token
* What it controls
---
* `--image-radius`
* Corner radius, shared by the image and its larger view.
---
* `--image-shadow`
* Shadow around the image.
---
* `--image-caption-color`
* Caption text color. Defaults to `--color-fg-muted`.
---
* `--image-overlay-bg`
* Backdrop behind the larger view.
---
* `--image-close-button-radius`
* Corner radius of the larger view's close button.
{% /table %}

## Example image.css

A `config/styles/image.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --image-radius: 4px;
  --image-shadow: none;
  --image-caption-color: #6b7280;
  --image-overlay-bg: rgba(0, 0, 0, 0.82);
  --image-close-button-radius: 6px;
}

.dark {
  --image-caption-color: #9ca3af;
}
```

## Next step

- [Style the hero](/customization/advanced/hero).
