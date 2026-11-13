---
title: Link Operations in Navigation
description: Add generated API pages to your sidebar and mix them with ordinary guide pages.
---

Generated API pages do not appear in the sidebar on their own. You add them to the navigation file, the same way you add any other page.

## Link an operation

Use `operation:` with the spec's `operationId` instead of `path:`:

```yaml
- label: Rings API
  expanded: true
  children:
    - operation: forgeRing
    - operation: getRing
```

Mordoc finds the page and fills in the link for you. If you rename the `operationId`, the build tells you instead of leaving a broken link.

## Choose a label

The `label` is optional. Without one, the sidebar uses the operation's `summary` from the spec:

```yaml
- operation: forgeRing
```

To use a shorter label, add one:

```yaml
- label: Forge
  operation: forgeRing
```

Short labels work well under a clear group name, for example `Forge` and `Retrieve` under `Rings API`.

## Add a group page

A group can link to its own page, as with any other group. Combine `path` with `children`:

```yaml
- label: Rings API
  path: /api/rings
  children:
    - operation: forgeRing
```

Here `/api/rings` must be a real page, so write one in `content/en/api/rings/index.md`. A path under an API's URL prefix that is not a page fails the build. See [Side Navigation](/configuration/side-navigation).

{% callout type="tip" title="See it live" %}
The [Rings of Power API](https://api-demo.mordoc.dev/api/rings) group in the demo sidebar has its own page and a list of operations.
{% /callout %}

## Mix in guide pages

Pages such as authentication, errors, and pagination are ordinary Markdown pages. Link them with `path:` next to your operations:

```yaml
- label: Guides
  children:
    - label: Authentication
      path: /guides/authentication
```

Write them like any other page. See [Write Pages](/getting-started/write-pages).

{% callout type="tip" title="See it live" %}
The demo's [Authentication](https://api-demo.mordoc.dev/guides/authentication) guide sits in the sidebar beside the API groups.
{% /callout %}

## What if an operation is not linked?

The page is still built and still searchable. Anyone with the URL can open it. The build prints a warning listing the operations that are not in the sidebar.

## Works with top navigation

`operation:` works in `sidenav.yaml` and in the per-area sidenav files used with top navigation. See [Top Navigation](/configuration/top-navigation).

## Next step

[Enrich descriptions](/api-reference/enrich-descriptions).
