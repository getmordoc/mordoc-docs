---
title: API Registry
description: Register OpenAPI specs and control where their pages appear.
---

The API registry tells Mordoc which OpenAPI specs to turn into API pages.

## Create the registry file

The registry lives here:

```text
config/api.yaml
```

Create it only when your project has an API reference. Without it, Mordoc skips all API features.

## Register a spec

The simplest file is a list of specs:

```yaml
- id: rings
  spec: rings.yaml
```

Each entry accepts these fields:

{% table %}
* Field
* Required
* What it does
---
* `id`
* Yes
* A short name for the API. Letters, digits, hyphens, and underscores only. It must be unique. It names the enrichment and example folders and is the default URL prefix.
---
* `spec`
* Yes
* The file name of the spec inside `api/specs/`.
---
* `routePrefix`
* No
* The URL prefix for this API's pages. Defaults to `/api/<id>`.
---
{% /table %}

## Change where pages appear

By default, an operation page lives at `/api/<id>/<operation-slug>`. Use `routePrefix` to change it:

```yaml
- id: rings
  spec: rings.yaml
  routePrefix: /reference
```

Now `forgeRing` opens at `/reference/forge-ring`.

{% table %}
* `routePrefix`
* URL of `forgeRing`
---
* not set
* `/api/rings/forge-ring`
---
* `/reference`
* `/reference/forge-ring`
---
* `/`
* `/forge-ring`
---
{% /table %}

Use `/` for a site that is only an API reference.

## Register more than one spec

Add an entry for each spec. Every `id` must be different:

```yaml
- id: fellowship
  spec: fellowship.yaml
- id: rings
  spec: rings.yaml
```

## Fail the build on any warning

To use the longer file shape, move the list under `specs` and add `strict`:

```yaml
strict: true
specs:
  - id: rings
    spec: rings.yaml
```

With `strict: true`, every API warning fails the build. That includes the warning for undocumented fields, so any field without a description fails a strict build. Use it only if you want that rule. See [Warnings and Errors](/api-reference/warnings-and-errors).

## Common mistakes

The build stops with a message that starts with `config/api.yaml` when:

* An entry has no `id` or no `spec`.
* An `id` has characters other than letters, digits, hyphens, and underscores.
* Two entries share an `id`.
* The file lists no specs.
* A `spec` file is missing from `api/specs/`.

## Next step

[Set up your languages](/configuration/languages).
