---
title: API Reference Overview
description: Generate a complete API reference from an OpenAPI spec, then improve it with plain Markdown.
---

Mordoc can turn an OpenAPI spec into a full API reference. Every operation in the spec becomes its own page, with no pages to write by hand.

Each generated page shows:

* The request and response sections, with a field tree for every body.
* Example requests and responses.
* A cURL sample for each request example.
* Deep links to any section or field, and search results that open the matching field.

{% callout type="tip" title="See it live" %}
Everything on this page is running in the [Mordoc API demo](https://www.api-demo.mordoc.dev/). Open a page there while you read.
{% /callout %}

## The spec is the source of truth

Developers use the OpenAPI spec directly to build against your API. That makes it the single source of truth, and the best place to fix any problem with a field, a description, or an example. A fix made in the spec improves the docs, the generated clients, and every other tool that reads it.

So aim for a spec that renders a good reference on its own. The spec alone produces a complete reference.

## Enrichment is a quick patch

Sometimes a description is wrong or thin and the API team cannot fix it today. Enrichment lets writers patch that text from the docs project, so readers are not left waiting. Treat these patches as short-term. When the spec is fixed, delete the patch.

{% table %}
* Use enrichment for
* Lifespan
---
* Patching a description, note, or example the spec has wrong or missing
* **Short-term.** Remove it once the spec is fixed.
---
* Things OpenAPI cannot express, such as `conditional` and custom [badges](/api-reference/badges), or callouts and links to guide pages
* **Long-term.** This is the proper home for them.
---
{% /table %}

Enrichment never adds, removes, or changes the type of a field. The spec stays the source of truth for structure.

## Where things live

An API reference adds a few files and folders to your project:

```text
config/api.yaml                          registers your specs
api/specs/                               OpenAPI files, never hand-edited
api/enrichment/<id>/operations/          patches and badges for one operation per file
api/enrichment/<id>/schemas/             patches and badges for one shared schema per file
api/examples/<id>/<operationId>/         optional extra example payloads
```

The `<id>` is the name you give each spec in `config/api.yaml`. See [Set Up an API Reference](/api-reference/set-up).

The [demo's own build notes](https://www.api-demo.mordoc.dev/guides/how-this-is-built) show this layout in a real project.

## What to read next

Pick the page that matches your role:

* **You own the API spec:** [Prepare Your Spec](/api-reference/prepare-your-spec).
* **You are adding an API reference to a site:** [Set Up an API Reference](/api-reference/set-up).
* **You are patching descriptions or adding badges:** [Enrich Descriptions](/api-reference/enrich-descriptions).

## Next step

[Prepare your spec](/api-reference/prepare-your-spec).
