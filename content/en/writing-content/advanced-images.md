---
title: Advanced Images
description: Add an image with a caption that readers can open larger.
---

An advanced image shows a caption below the image. Readers can click the image, or select it and press Enter, to open it larger. Use it for screenshots and diagrams that readers may want to look at more closely. For a plain image, see [Images](/writing-content/images).

## Add an advanced image

```markdown {% process=false %}
{% advancedImage src="/images/content-images/artwork.png" alt="Artwork" caption="The artwork, opened larger on click." /%}
```

**Here is how it renders**

{% advancedImage src="/images/content-images/artwork.png" alt="Artwork" caption="The artwork, opened larger on click." /%}

An advanced image stands on its own line. It can't be placed inside a sentence or a link.

## Attributes

{% table %}
* Attribute
* What it does
---
* `src`
* The path to the image, starting with `/`. Required.
---
* `alt`
* The text read by screen readers and shown if the image fails to load.
---
* `caption`
* The text shown below the image and below the larger version.
{% /table %}

To close the larger image, click anywhere, use the close button or press Escape.

## Next step

- [Add clips](/writing-content/clip).
