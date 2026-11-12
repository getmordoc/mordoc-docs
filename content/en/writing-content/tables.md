---
title: Tables
description: Create structured tables with Mordoc table syntax.
---

Tables are useful when readers need to compare related information.

Mordoc uses a table syntax that can hold simple text and richer content. This is different from basic Markdown table syntax.

## Create a simple table

A Mordoc table starts with `{% table %}` and ends with `{% /table %}`.

Use `*` for each cell. Use `---` to separate the header and rows.

```markdown {% process=false %}
{% table %}
* Header 1
* Header 2
* Header 3
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
---
{% /table %}
```

**How it renders**

{% table %}
* Header 1
* Header 2
* Header 3
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
---
{% /table %}

Each row should have the same number of cells as the header.

## Add more columns

You can add more columns by adding more header cells and matching row cells:

```markdown {% process=false %}
{% table %}
* Header 1
* Header 2
* Header 3
* Header 4
* Header 5
* Header 6
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
* Row 1, Cell 4
* Row 1, Cell 5
* Row 1, Cell 6
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
* Row 2, Cell 4
* Row 2, Cell 5
* Row 2, Cell 6
---
{% /table %}
```

Wide tables can be harder to read, especially on small screens. Use only as many columns as the reader needs.

## Add rich content

Table cells can contain more than plain text.

For example, a cell can include formatted text, lists, blockquotes, code blocks, callouts, and images.

````markdown {% process=false %}
{% table %}
* Content type
* Example
---
* Typography
* **Bold**, *italic*, `inline code`, and a [link](/getting-started/create-project).
---
* Unordered list
*
  - Alpha
  - Beta
    - Gamma nested
---
* Ordered list
*
  1. Step one
  2. Step two
     1. Sub-step a
     2. Sub-step b
---
* Blockquote
*
  > Quoted line one.
  >
  > Quoted line two.
---
* Code block
*
  ```ts
  export function isReady(pageCount: number): boolean {
    return pageCount > 0;
  }
  ```
---
* Callout note
*
  {% callout type="note" title="Inside table" %}
  Callout body with a list:

  - Allowed in callouts
  - Second item
  {% /callout %}
---
* Callout warning
*
  {% callout type="warning" title="Warning" %}
  ```json
  { "pages": 3 }
  ```
  {% /callout %}
---
* Callout danger
*
  {% callout type="danger" title="Danger" %}
  Critical constraint in a table cell.
  {% /callout %}
---
* Callout tip
*
  {% callout type="tip" %}
  Tip without a title.
  {% /callout %}
---
* Image
*
  ![Mordoc hero image](/images/hero-images/mordor.png)
---
* Mixed inline links
* External: [Example](https://example.com), internal: [Create a Project](/getting-started/create-project)
{% /table %}
````

**How it renders**

{% table %}
* Content type
* Example
---
* Typography
* **Bold**, *italic*, `inline code`, and a [link](/getting-started/create-project).
---
* Unordered list
*
  - Alpha
  - Beta
    - Gamma nested
---
* Ordered list
*
  1. Step one
  2. Step two
     1. Sub-step a
     2. Sub-step b
---
* Blockquote
*
  > Quoted line one.
  >
  > Quoted line two.
---
* Code block
*
  ```ts
  export function isReady(pageCount: number): boolean {
    return pageCount > 0;
  }
  ```
---
* Callout note
*
  {% callout type="note" title="Inside table" %}
  Callout body with a list:

  - Allowed in callouts
  - Second item
  {% /callout %}
---
* Callout warning
*
  {% callout type="warning" title="Warning" %}
  ```json
  { "pages": 3 }
  ```
  {% /callout %}
---
* Callout danger
*
  {% callout type="danger" title="Danger" %}
  Critical constraint in a table cell.
  {% /callout %}
---
* Callout tip
*
  {% callout type="tip" %}
  Tip without a title.
  {% /callout %}
---
* Image
*
  ![Mordoc hero image](/images/content-images/artwork.png)
---
* Mixed inline links
* External: [Example](https://example.com), internal: [Create a Project](/getting-started/create-project)
{% /table %}

## Next step

- [Use cards and card grids](/writing-content/cards-and-card-grids).
