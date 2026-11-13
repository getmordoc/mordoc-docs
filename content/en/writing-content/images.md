---
title: Images
description: Add images and icons, including ones with a variable-driven source.
---

Put content images in `public/`, then reference them with a path that starts with `/`.

## Basic images

```markdown
![Artwork](/images/content-images/artwork.png)
```

The text in brackets is the image's `alt` text. Keep it descriptive, since it is read by screen readers and shown if the image fails to load.

**Here is how it renders**

![Artwork](/images/content-images/artwork.png)

The [Images and Files](/getting-started/images-and-files) page walks through adding an image step by step.

## The image tag

You can also write an image as a tag. It renders the same plain image, and its `src` can be a [variable](/configuration/variables).

```markdown {% process=false %}
{% image src="/images/content-images/artwork.png" alt="Artwork" title="Shown on hover" /%}
```

**Here is how it renders**

{% image src="/images/content-images/artwork.png" alt="Artwork" title="Shown on hover" /%}

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
* `title`
* The text shown when a reader hovers over the image.
{% /table %}

For a caption below the image and click to enlarge, use an [advanced image](/writing-content/advanced-images).

## Icons

Icons work the same way as any other image: place the file in `public/`, then reference its path.

```text
public/icons/shield.svg
```

Small SVGs are the most common choice, since they stay sharp at any size.

You won't insert an icon into page text directly. Instead, certain components take an icon file through an attribute, such as `icon` on a [card](/writing-content/cards-and-card-grids) or an actor's icon in a [sequence diagram](/creating-diagrams/sequence-diagrams).

## Images with variables

Sometimes an image's source should come from a reusable value instead of being written directly, for example a logo URL that might change later. See [Variables](/configuration/variables) for how to define a variable and use it in an image.

## Next step

- [Add advanced images](/writing-content/advanced-images).
