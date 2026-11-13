---
title: Enrich Descriptions
description: Patch descriptions in generated API pages with Markdown files, and add badges the OpenAPI spec cannot express.
---

The OpenAPI spec is the source of truth for your API. Developers build against it directly, so the best fix for a wrong or missing description is a change in the spec itself.

Enrichment is for two different jobs:

* **A quick patch.** The spec text is wrong or thin and cannot be fixed right now. A Markdown file in the docs project fixes what readers see in the meantime. This is **short-term**. Once the spec is fixed, delete the patch.
* **Things OpenAPI cannot express.** Badges such as [`conditional`](/api-reference/badges), callouts, and links to guide pages have no place in the spec. Enrichment is their **long-term** home.

Enrichment is optional and used sparingly. An endpoint with 40 fields may need notes on just three.

{% callout type="warning" title="Remove patches when the spec is fixed" %}
A patch in a `schemas/` file replaces the spec's description. If the spec is later improved but the patch stays, readers keep seeing the old patch instead of the better spec text. Review your enrichment files whenever the spec changes.
{% /callout %}

{% callout type="tip" title="See it live" %}
The [List members](https://api-demo.mordoc.dev/api/fellowship/list-members) page mixes spec text with enrichment. The [Forge a ring](https://api-demo.mordoc.dev/api/rings/forge-ring) page adds a callout and notes.
{% /callout %}

## The file name is the target

Enrichment files live under `api/enrichment/<id>/`, where `<id>` is the spec's `id` from `config/api.yaml`. The file name tells Mordoc what the file describes:

```text
api/enrichment/rings/operations/forgeRing.md
api/enrichment/rings/schemas/Ring.md
```

* `operations/<operationId>.md` targets one operation.
* `schemas/<SchemaName>.md` targets one shared schema, everywhere it is used.

These files have no frontmatter. Write the Markdown directly.

## Describe a field

Put field notes in a `{% params %}` block. Each `###` heading names one field, and the text under it is the note:

```markdown {% process=false %}
{% params %}
### smith_id
Must belong to a smith registered with the guild of the requested `kind`.
{% /params %}
```

The heading must match the field name in the spec.

## Pick the right scope

A plain `{% params %}` block describes the operation's parameters and request body. To describe a response, name the status code:

```markdown {% process=false %}
{% params in="response" status="403" %}
### message
Explains which guild rule was broken.
{% /params %}
```

The `status` is required. It must be a response the operation declares.

## Point to nested fields

In an operation file, use a dotted path for a nested field:

```markdown {% process=false %}
{% params %}
### quest.destination
The place the fellowship must reach, for example `Mount Doom`.
{% /params %}
```

In a schema file, use the plain field name. If a plain name matches more than one field, Mordoc skips it and the warning lists the full paths to choose from.

To find the right schema file, look at the field on the generated page. It shows the schema name, for example `Region`.

## How enrichment combines with the spec

{% table %}
* Where you write it
* What happens to the spec's text
---
* `schemas/<SchemaName>.md`
* **Replaces** the field's description.
---
* `operations/<operationId>.md` in a `{% params %}` block
* **Appends** your text as a note below the description.
---
* `{% params mode="replace" %}`
* **Replaces** the description even in an operation file.
---
* Text outside any `{% params %}` block in an operation file
* **Replaces** the operation's own description at the top of the page.
---
{% /table %}

Use the operation-level text for introductions, callouts, and links. For example, this text appears at the top of the Forge a ring page:

```markdown {% process=false %}
Forges a new ring of the requested kind and metal.

{% callout type="warning" title="Handle with care" %}
A ring of kind `one` cannot be undone.
{% /callout %}
```

You can use any Markdown or Mordoc tag inside an entry: callouts, tables, code blocks, links, and variables.

A response's own description cannot be enriched. Its fields can.

## Add example payloads

Examples come from three places, in this order:

1. The spec's `examples`.
2. Files you add under `api/examples/`.
3. A sample generated from the schema, when a request or response has none, so the panel is never empty.

Add your own files when the spec lacks a useful case:

```text
api/examples/rings/forgeRing/request.the-one-ring.json
api/examples/rings/forgeRing/response.403-unlicensed.json
```

* Name request files `request.<case>.json`.
* Name response files `response.<status>.json`, with an optional suffix such as `403-unlicensed`.
* The case name becomes the label. `the-one-ring` shows as "The one ring".
* If a file has the same name as a spec example, your file wins.

The same files serve every language. A file with a wrong name or invalid JSON is skipped with a warning.

Mordoc also builds a cURL sample for each request example. You do not write these.

{% callout type="tip" title="See it live" %}
The [Light a beacon](https://api-demo.mordoc.dev/api/watch/light-beacon) page shows spec examples next to authored ones.
{% /callout %}

## What if a target is wrong?

A missing file target or an unknown field never breaks the build. Mordoc skips that entry and prints a warning. See [Warnings and Errors](/api-reference/warnings-and-errors).

## Keep patches short-lived

When you patch a description, tell the API team what you changed so they can fix it in the spec. When the new spec ships, delete the entry. Keep only badges, callouts, and other content the spec cannot hold.

## Next step

[Mark fields with badges](/api-reference/badges).
