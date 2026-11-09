---
title: Warnings and Errors
description: Understand what the API reference build reports, why, and how to fix it.
---

The API reference build follows one rule: **problems that make the site wrong fail the build, and problems that make it less complete only warn.**

The site always publishes as the spec plus whatever enrichment could be applied.

## See more detail

By default, each warning prints as a single line. Add `--verbose` to see more, such as the full list of undocumented fields:

```bash
npm run build -- --verbose
```

## Errors that fail the build

Fix these before the site can build.

{% table %}
* What you see
* Why
* Fix
---
* `Spec "<file>" is not valid OpenAPI:`
* The spec has an error.
* Fix the spec at its source and export it again.
---
* `config/api.yaml: API "<id>" declares spec "<file>", but ... does not exist.`
* The registry points at a missing file.
* Put the file in `api/specs/` or correct the name.
---
* `<id>: <method> <path> has no "operationId".`
* An operation has no `operationId`.
* Add a unique `operationId`.
---
* `operationId "<name>" is used by both ... Operation ids must be unique.`
* Two operations share a name.
* Rename one in the spec.
---
* `Navigation references operation "<name>", which no registered spec declares.`
* A sidebar `operation:` entry has no matching operation.
* Check the spelling, or remove the entry.
---
* `Navigation entry "<label>" points at "<path>", which is not a route.`
* A `path:` under an API's URL prefix leads nowhere.
* Use `operation:` instead, or create the page.
---
* `Route collision at "<path>"`
* Two pages claim the same URL.
* Rename the page or change the `routePrefix`.
---
{% /table %}

## Warnings

These do not stop the build. The affected entry is skipped.

{% table %}
* What you see
* Fix
---
* `no operation with operationId "<name>" — file skipped.`
* Rename the file in `operations/` to match an `operationId`.
---
* `no component schema named "<name>" — file skipped.`
* Rename the file in `schemas/` to match a schema in the spec.
---
* `"<field>" does not match any field in ... entry skipped. Valid fields: ...`
* Use a field name from the list in the message.
---
* `"<field>" is ambiguous in ... Use the full dotted path.`
* Write the full path, such as `quest.destination`.
---
* `{% params in="response" %} requires a "status" attribute`
* Add the status, for example `status="403"`.
---
* `declares no <status> response`
* Use a status code the operation declares.
---
* `content before the first "###" entry inside a {% params %} block is ignored`
* Move that text outside the block.
---
* `has a non-text badge — badge dropped`
* Write the badge as quoted text.
---
* `is badged "conditional" but has no description`
* Explain the condition in the field's description.
---
* `filename must be "request.<case>.json" or "response.<status>.json"`
* Rename the example file.
---
* `invalid JSON`
* Fix the JSON in the example file.
---
* `<n> operation(s) reachable only by URL (no nav entry)`
* Add the listed operations to the sidebar, or ignore this if it is intentional.
---
* `<id>: <n>% of fields documented`
* Informational. Run with `--verbose` to see the missing fields.
---
{% /table %}

## Turn warnings into errors

If your team wants every warning to fail the build, set `strict: true` in `config/api.yaml`. See [API Registry](/configuration/api-registry).

## Next step

[Configure the API registry](/configuration/api-registry).
