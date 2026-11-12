---
title: Accordions
description: Add collapsible sections for content readers may not need to see right away.
---

An accordion is a collapsible section: a clickable title, and a body that's hidden until the reader opens it.

Use accordions for content that's useful but not essential to every reader. For example if you want to write Frequently asked questions (FAQ), optional detail, or a long list of edge cases that would otherwise crowd the page.

## Add an accordion

```markdown {% process=false %}
{% accordion title="Who is the Ring-bearer?" %}
Frodo Baggins carries the One Ring from the Shire to Mount Doom, though Sam never leaves his side.
{% /accordion %}
```

**How it renders**

{% accordion title="Who is the Ring-bearer?" %}
Frodo Baggins carries the One Ring from the Shire to Mount Doom, though Sam never leaves his side.
{% /accordion %}

An accordion accepts the same content a normal page body does, i.e headings, paragraphs, lists, code blocks, images, callouts, even a nested `clip`, another accordion, etc.

## Open it by default

Add `defaultOpen=true` when the content should already be visible on page load, rather than requiring a click:

```markdown {% process=false %}
{% accordion title="The Fellowship" defaultOpen=true %}
Frodo, Sam, Merry, Pippin, Gandalf, Aragorn, Legolas, Gimli, and Boromir.
{% /accordion %}
```

**How it renders**

{% accordion title="The Fellowship" defaultOpen=true %}
Frodo, Sam, Merry, Pippin, Gandalf, Aragorn, Legolas, Gimli, and Boromir.
{% /accordion %}

## Group several accordions

Wrap a set of accordions in `accordions` to visually connect them into one block:

```markdown {% process=false %}
{% accordions %}
{% accordion title="What is the One Ring?" %}
Sauron forged it in the fires of Mount Doom, binding it to his own power so that whoever holds it can command the other Rings of Power.
{% /accordion %}
{% accordion title="Why can't the Ring simply be destroyed with a sword?" %}
It can only be unmade the same way it was made: cast back into the fires where it was forged.
{% /accordion %}
{% /accordions %}
```

**How it renders**

{% accordions %}
{% accordion title="What is the One Ring?" %}
Sauron forged it in the fires of Mount Doom, binding it to his own power so that whoever holds it can command the other Rings of Power.
{% /accordion %}
{% accordion title="Why can't the Ring simply be destroyed with a sword?" %}
It can only be unmade the same way it was made: cast back into the fires where it was forged.
{% /accordion %}
{% /accordions %}

By default, a group is exclusive: opening one item closes any other open item in the group, same as a typical FAQ list.

## Accordion attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `title`
* The clickable header text
* Any text
* Required
---
* `defaultOpen`
* Whether the section starts open
* `true`/`false` (default `false`)
* Optional
{% /table %}

## Next step

- [Create landing pages](/writing-content/landing-pages).
