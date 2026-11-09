---
title: Badges
description: Mark API fields as conditional, read-only, beta, or anything else readers should notice.
---

A badge is a small label next to a field name. Use it for a quick signal that does not belong in a full sentence.

OpenAPI has no way to express a conditional field or a custom label, so badges live in enrichment files. Unlike description patches, they are **long-term**: keep them for as long as the field needs them.

## Add a badge

Write the badge in the field's `###` heading inside an enrichment file:

```markdown
{% params %}
### dark_lord_approval {% badge="conditional" %}
Required only when `kind` is `one`.
{% /params %}
```

Rules:

* One badge per field.
* The value must be quoted text.

## Conditional

`conditional` is a reserved word for a field that applies only in some situations:

```markdown
### dark_lord_approval {% badge="conditional" %}
Required only when `kind` is `one`.
```

It shows as an amber label. A bare label does not tell readers what the condition is, so always explain it in the field's description. If you do not, the build warns you.

{% callout type="tip" title="See it live" %}
On [Forge a ring](https://www.api-demo.mordoc.dev/api/rings/forge-ring), the `dark_lord_approval` field is conditional.
{% /callout %}

## Your own badges

Any other text becomes a badge exactly as you write it:

```markdown
### corruption_level {% badge="Read-only" %}
A value from 0 to 100 that grows each day a ring is worn.
```

All of these badges share one style. Pick short words, such as `Read-only` or `Beta`.

{% callout type="tip" title="See it live" %}
The [Retrieve a ring](https://www.api-demo.mordoc.dev/api/rings/get-ring) page shows `Read-only` and `Beta` badges.
{% /callout %}

## Deprecated is separate

You do not write a `Deprecated` badge. It comes from `deprecated: true` in the spec. See [Prepare Your Spec](/api-reference/prepare-your-spec).

## If a badge is wrong

An empty badge is ignored. A badge that is not quoted text is dropped, and the build prints a warning.

## Next step

[Troubleshoot warnings and errors](/api-reference/warnings-and-errors).
