---
title: Callouts
description: Highlight notes, tips, warnings, and important messages in Mordoc pages.
---

Callouts help important information stand out from the rest of the page.

Use them when a reader should pause, notice something, or be careful before continuing. Do not use a callout for every important sentence. Too many callouts make a page harder to scan.

## Add a basic callout

A callout starts with `{% callout %}` and ends with `{% /callout %}`.

```markdown {% process=false %}
{% callout type="note" title="Good to know" %}
The Fellowship of the Ring set out from Rivendell with nine companions.
{% /callout %}
```

The text between the opening and closing tags is the callout content.

## Choose a type

Mordoc supports four callout types:

* `note` for useful extra context
* `tip` for helpful suggestions
* `warning` for something readers should be careful about
* `danger` for serious or risky situations

The `type` value is optional. If you leave it out, Mordoc uses `note`.

The `title` value is also optional. Add one when it helps readers understand the callout quickly.

## Note

Use `note` for helpful information that supports the main text.

```markdown {% process=false %}
{% callout type="note" title="Good to know" %}
The Shire lies west of Bree, across the Brandywine River.
{% /callout %}
```

**How it renders**

{% callout type="note" title="Good to know" %}
The Shire lies west of Bree, across the Brandywine River.
{% /callout %}

## Tip

Use `tip` for advice that makes a task easier.

```markdown {% process=false %}
{% callout type="tip" title="Speak, friend, and enter" %}
When at the gates of Moria, say "Mellon."
{% /callout %}
```

**How it renders**

{% callout type="tip" title="Speak, friend, and enter" %}
When at the gates of Moria, say "Mellon."
{% /callout %}

## Warning

Use `warning` when readers should slow down or check something before continuing.

```markdown {% process=false %}
{% callout type="warning" title="Mind the water" %}
Do not linger by the lake outside the Doors of Durin. Something stirs beneath its surface.
{% /callout %}
```

**How it renders**

{% callout type="warning" title="Mind the water" %}
Do not linger by the lake outside the Doors of Durin. Something stirs beneath its surface.
{% /callout %}

## Danger

Use `danger` only for serious situations.

```markdown {% process=false %}
{% callout type="danger" title="Never put on the Ring" %}
Do not put on the One Ring. The moment you wear it, you draw the Eye of Sauron towards you.
{% /callout %}
```

**How it renders**

{% callout type="danger" title="Never put on the Ring" %}
Do not put on the One Ring. The moment you wear it, you draw the Eye of Sauron towards you.
{% /callout %}

## Keep callouts short

A good callout is usually one short paragraph or a small list. If the callout becomes long, it may need to be a normal section instead.

## Callout attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `type`
* The callout style
* `note`, `tip`, `warning`, `danger` (default `note`)
* Optional
---
* `title`
* A short heading shown above the callout body
* Any text
* Optional
---
{% /table %}

## Next step

* [Create tables](/writing-content/tables).
