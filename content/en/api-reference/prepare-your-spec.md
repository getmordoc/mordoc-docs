---
title: Prepare Your Spec
description: What the API team needs to provide so Mordoc can generate a good API reference.
---

This page is for the team that owns the API. Writers can hand it over as is.

Mordoc reads a standard OpenAPI file. If the file is valid and every operation has an `operationId`, you get a working reference.

## Where the spec goes

Put the spec in the `api/specs/` folder:

```text
api/specs/rings.yaml
```

Generate this file from your API code or tooling. Do not edit it by hand in the docs project, because the next export would overwrite your changes.

## Keep the spec as the source of truth

Developers build against this spec directly, so every improvement you make here helps them as well as the docs. Fix wrong or missing text in the spec, at its source.

If a fix cannot wait for the next release, writers can patch the text with [enrichment](/api-reference/enrich-descriptions) as a short-term measure. Those patches should be removed once the spec catches up.

## What is required

* **A valid OpenAPI file.** Only errors fail the build. Style warnings from the linter are ignored.
* **An `operationId` on every operation.** It must be unique across the whole spec.

The `operationId` becomes the page's URL and the name of its enrichment file, so choose it with care:

```yaml
paths:
  /rings:
    post:
      operationId: forgeRing
      summary: Forge a ring
```

This operation gets the URL `/api/rings/forge-ring`. Renaming the `operationId` later moves the page to a new URL.

The `summary` becomes the page title and the default sidebar label. Keep it short.

## What improves the docs for free

None of these are required, but each one makes the generated page better:

* **Real `description` text** on operations, parameters, and fields.
* **Named `examples`** on request and response bodies.
* **`servers`.** The first server's URL is used as the host in cURL samples. Without one, Mordoc uses `https://api.example.com`.
* **`deprecated: true`** on operations that are going away. The page marks them as deprecated.

{% callout type="tip" title="See it live" %}
The [Retrieve a member](https://www.api-demo.mordoc.dev/api/fellowship/get-member) page uses only the spec, with no enrichment at all.
{% /callout %}

## Webhooks

Mordoc documents webhooks from the top-level `webhooks` map of an OpenAPI 3.1 spec. The older `x-webhooks` extension from OpenAPI 3.0 is not read.

```yaml
webhooks:
  beaconLit:
    post:
      operationId: beaconLit
      summary: Beacon lit
```

A webhook works like any other operation:

* It needs an `operationId`, and that name must be unique across both `paths` and `webhooks`.
* You link it in the sidebar with `operation:`.
* You can enrich it the same way.

The page shows the webhook's name where a normal operation shows its URL, and it has no cURL sample.

{% callout type="tip" title="See it live" %}
Open the [Beacon lit](https://www.api-demo.mordoc.dev/api/watch/beacon-lit-event) webhook page.
{% /callout %}

## Next step

[Set up an API reference](/api-reference/set-up).
