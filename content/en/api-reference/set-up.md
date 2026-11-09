---
title: Set Up an API Reference
description: Add an OpenAPI spec to your Mordoc project and see generated API pages in minutes.
---

This page takes you from an OpenAPI file to a running API reference.

You need an existing Mordoc project. If you do not have one, start with [Create a Project](/getting-started/create-project).

## Step 1: Add the spec

Copy your OpenAPI file into the `api/specs/` folder. Create the folders if they do not exist.

```text
api/specs/rings.yaml
```

Not sure the spec is ready? See [Prepare Your Spec](/api-reference/prepare-your-spec).

## Step 2: Register the spec

Create `config/api.yaml` and give the spec an `id` and its file name:

```yaml
- id: rings
  spec: rings.yaml
```

The `id` names the API in folders and URLs. Use letters, digits, hyphens, and underscores only. See [API Registry](/configuration/api-registry) for every option.

## Step 3: Link operations in the sidebar

Add the operations to your sidebar with `operation:` and the spec's `operationId`:

```yaml
- label: Rings API
  expanded: true
  children:
    - operation: forgeRing
    - operation: getRing
```

See [Link Operations in Navigation](/api-reference/link-operations-in-navigation) for groups, labels, and guide pages.

## Step 4: Run the site

```bash
npm run dev
```

Open the site and click one of the new sidebar links.

## Where the pages live

Each operation gets a page at `/api/<id>/<operation-slug>`. The slug is the `operationId` in kebab-case:

{% table %}
* `operationId`
* Page URL
---
* `forgeRing`
* `/api/rings/forge-ring`
---
* `getRing`
* `/api/rings/get-ring`
---
{% /table %}

You can change the `/api/<id>` part with `routePrefix`. See [API Registry](/configuration/api-registry).

{% callout type="tip" title="See it live" %}
The [Retrieve a ring](https://www.api-demo.mordoc.dev/api/rings/get-ring) page was generated from a spec with no extra work.
{% /callout %}

## More than one spec

Add one entry per spec. Each spec gets its own `id`, its own URL prefix, and its own enrichment folder:

```yaml
- id: fellowship
  spec: fellowship.yaml
- id: rings
  spec: rings.yaml
```

## Next step

[Link operations in navigation](/api-reference/link-operations-in-navigation).
