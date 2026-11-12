---
title: Columns
description: Lay out content side by side with the columns component.
---

Columns arrange content side by side, equal width, and stack into a single column automatically on narrow screens.

Use them to compare two short pieces of content, or to put a demo clip next to the steps that produce it.

## Add columns

Wrap two or more `column` tags in `columns`:

```markdown {% process=false %}
{% columns %}
{% column %}
{% image src="/images/content-images/cesky-krumlov.jpg" alt="Cesky Krumlov" /%}
{% /column %}
{% column %}
### Český Krumlov

A small town in South Bohemia, built around a sharp bend in the Vltava river. Its old town is packed onto the riverbank below a castle that has stood since the 13th century, and the whole center is a UNESCO World Heritage Site.

Visitors come for the narrow cobbled streets, the castle's painted tower, and the view from the bridge over the river. 
{% /column %}
{% /columns %}
```

**How it renders**

{% columns %}
{% column %}
{% image src="/images/content-images/cesky-krumlov.jpg" alt="Cesky Krumlov" /%}
{% /column %}
{% column %}
### Český Krumlov

A small town in South Bohemia, built around a sharp bend in the Vltava river. Its old town is packed onto the riverbank below a castle that has stood since the 13th century, and the whole center is a UNESCO World Heritage Site.

Visitors come for the narrow cobbled streets, the castle's painted tower, and the view from the bridge over the river. 
{% /column %}
{% /columns %}

{%callout type="note" %}
A column accepts the same content a normal page body does: headings, paragraphs, lists, code blocks, images, callouts, even a nested `clip` or `accordion`.
{% /callout %}

Column count follows however many `column` tags you nest.

## Add a divider

Set `divider=true` on `columns` to draw a vertical rule between columns:

```markdown {% process=false %}
{% columns divider=true %}
{% column %}
{% image src="/images/content-images/iceland.jpg" alt="Iceland" /%}
{% /column %}
{% column %}
### Iceland

A Nordic island nation shaped by volcanoes, glaciers, and the rift where the North American and Eurasian plates pull apart. Waterfalls, hot springs, and black sand beaches sit within a short drive of one another along the Ring Road.

Visitors come for the Northern Lights in winter, the midnight sun in summer, and the glacial lagoons in between.
{% /column %}
{% /columns %}
```

**How it renders**

{% columns divider=true %}
{% column %}
{% image src="/images/content-images/iceland.jpg" alt="Iceland" /%}
{% /column %}
{% column %}
### Iceland

A Nordic island nation shaped by volcanoes, glaciers, and the rift where the North American and Eurasian plates pull apart. Waterfalls, hot springs, and black sand beaches sit within a short drive of one another along the Ring Road.

Visitors come for the Northern Lights in winter, the midnight sun in summer, and the glacial lagoons in between.
{% /column %}
{% /columns %}

## Columns attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `divider`
* Draws a vertical rule between columns
* `true`/`false` (default `false`)
* Optional
{% /table %}

`column` itself takes no attributes.

## Keep columns short

Columns work best for content that's genuinely meant to sit side by side. For example: a short comparison, or a clip paired with the steps around it. For anything longer, plain stacked sections are usually easier to read.

## Next step

- [Group content with accordions](/writing-content/accordions).
