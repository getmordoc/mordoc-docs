---
title: Landing Pages
description: Create full-width pages for homepages and overview pages.
---

Most Mordoc pages use the normal documentation layout: side navigation bar on the left, page content in the middle, and a table of contents on the right.

Sometimes you need a different kind of page. A homepage or product overview often works better as a landing page.

## What a landing page changes

A landing page is full-width.

It does not show:

* The side navigation
* The right-side table of contents
* The normal article header

That makes it useful for pages that introduce the site, show cards, or guide readers into the main documentation.

## Turn a page into a landing page

Add `layout: landing` to the page frontmatter:

```markdown
---
title: Home
description: Welcome to my documentation.
layout: landing
---
```

Use landing pages sparingly. Most documentation pages should use the normal layout.

## Add a hero

A hero is a large opening section, usually used at the top of a landing page.

You can add a hero section to your landing page using the `{% hero %}` tag.

```markdown {% process=false %}
{% hero
  title="My Product Docs"
  titleAccent="made simple"
  description="Find guides, reference material, and practical examples."
  background="/images/hero-bg.png"
%}
{% button path="/getting-started/create-project" %}
Get started
{% /button %}
{% /hero %}
```

## Hero attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `title`
* The main heading text
* Any text
* Required
---
* `titleAccent`
* Highlighted text shown on a new line under the title
* Any text
* Optional
---
* `description`
* Supporting text shown below the title
* Any text
* Optional
---
* `image`
* A supporting image, such as a product screenshot, shown below the buttons
* Image path
* Optional
---
* `background`
* A background image behind the whole hero
* Image path
* Optional
{% /table %}

Use `background` for a full-bleed image behind the whole hero. Use `image` for a separate supporting image, such as a product screenshot, shown below the buttons.

{% callout type="note" title="Colors are not attributes" %}
There's no `titleColor`, `titleAccentColor`, or `descriptionColor` attribute, and `background` never accepts a plain color, only an image path. A hero's colors are a design decision, not content, so they're set once in CSS. See [Hero](/customization/advanced/hero) under Advanced Customization.
{% /callout %}

## Sizing a background image

The hero has no fixed height. It grows or shrinks with the title, `titleAccent`, description, and buttons you include, and with the viewport width. A background image is scaled to cover that space, so it gets cropped to fill whatever height the hero ends up with.

Pick a wide, short aspect ratio and keep the important part of the image centered. Content near the top and bottom edges is the first to be cropped as the hero grows taller.

{% callout type="tip" title="Sidestep cropping with an abstract image" %}
An image with no fixed focal point, such as a texture, gradient, or pattern, holds up no matter how the hero resizes. Cropping barely changes how it looks.
{% /callout %}

## Add sections

A section groups content on a landing page, with an optional title and background.

You can add a section to your landing page using the `{% section %}` tag.

```markdown {% process=false %}
{% section title="Choose where to begin" background="/images/section-bg.png" %}
This section introduces the main paths through the documentation.
{% /section %}
```

## Section attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `title`
* A heading shown above the section content
* Any text
* Optional
---
* `background`
* A background image behind the section
* Image path
* Optional
{% /table %}

When a section has a `background` image, its title and text automatically switch to white for readability.

{% callout type="note" title="Colors are not attributes" %}
`background` never accepts a plain color, only an image path. A section's solid background color is a design decision, not content, so it's set once in CSS. See [Sections](/customization/advanced/sections) under Advanced Customization.
{% /callout %}

## Add cards to a landing page

Landing pages often use cards inside a section to guide readers toward where to go next:

```markdown {% process=false %}
{% section title="Explore the docs" %}
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" tag="Start here" %}
Create and run your first project.
{% /card %}
{% /cardGrid %}
{% /section %}
```

See [Cards and card grids](/writing-content/cards-and-card-grids) for the full card and card grid syntax.

## Add buttons

A button is a styled call to action, usually linking to another page.

You can add a button using the `{% button %}` tag.

```markdown {% process=false %}
{% button path="/getting-started/create-project" %}
Create a project
{% /button %}
```

Use `variant="secondary"` for a quieter button:

```markdown {% process=false %}
{% button path="/writing-content/markdown-basics" variant="secondary" %}
Learn Markdown
{% /button %}
```

## Button attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `path`
* The page or URL the button links to
* A path or URL
* Required
---
* `variant`
* Controls the button's visual style
* `primary`, `secondary` (default `primary`)
* Optional
{% /table %}

## When to use a landing page

Use a landing page for:

* The homepage
* A product overview
* A major section overview

## Next step

* [Create diagrams](/creating-diagrams/overview).
