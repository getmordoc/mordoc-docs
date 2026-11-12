---
title: Images
description: Style the plain images placed in Markdown content.
---

An image is a standard Markdown `![]()` image. See [Images](/writing-content/images) for the Markdown syntax. This page covers its appearance.

## Open the override file

```text
config/styles/image.css
```

Images and [advanced images](/customization/advanced/advanced-images) are styled in this same file, and share `--image-radius` and `--image-shadow`.

## Tokens

{% table %}
* Token
* What it controls
---
* `--image-radius`
* Corner radius of the image.
---
* `--image-shadow`
* Shadow around the image.
{% /table %}

## Example image.css

A `config/styles/image.css` that sets every token on this page:

```css
:root {
  --image-radius: 4px;
  --image-shadow: none;
}
```

## Next step

- [Style advanced images](/customization/advanced/advanced-images).
