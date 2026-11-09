---
title: Eine API-Referenz einrichten
description: Fügen Sie Ihrem Mordoc-Projekt eine OpenAPI-Spezifikation hinzu und sehen Sie in wenigen Minuten erzeugte API-Seiten.
---

Diese Seite führt Sie von einer OpenAPI-Datei zu einer laufenden API-Referenz.

Sie benötigen ein bestehendes Mordoc-Projekt. Wenn Sie noch keines haben, beginnen Sie mit [Ein Projekt erstellen](/de/getting-started/create-project).

## Schritt 1: Die Spezifikation hinzufügen

Kopieren Sie Ihre OpenAPI-Datei in den Ordner `api/specs/`. Erstellen Sie die Ordner, falls sie nicht existieren.

```text
api/specs/rings.yaml
```

Sie sind nicht sicher, ob die Spezifikation bereit ist? Siehe [Ihre Spezifikation vorbereiten](/de/api-reference/prepare-your-spec).

## Schritt 2: Die Spezifikation registrieren

Erstellen Sie `config/api.yaml` und geben Sie der Spezifikation eine `id` und ihren Dateinamen:

```yaml
- id: rings
  spec: rings.yaml
```

Die `id` benennt die API in Ordnern und URLs. Verwenden Sie nur Buchstaben, Ziffern, Bindestriche und Unterstriche. Alle Optionen finden Sie unter [API-Registry](/de/configuration/api-registry).

## Schritt 3: Operationen in der Seitenleiste verlinken

Fügen Sie die Operationen mit `operation:` und der `operationId` der Spezifikation zu Ihrer Seitenleiste hinzu:

```yaml
- label: Rings API
  expanded: true
  children:
    - operation: forgeRing
    - operation: getRing
```

Informationen zu Gruppen, Labels und Leitfadenseiten finden Sie unter [Operationen in der Navigation verlinken](/de/api-reference/link-operations-in-navigation).

## Schritt 4: Die Website ausführen

```bash
npm run dev
```

Öffnen Sie die Website und klicken Sie auf einen der neuen Links in der Seitenleiste.

## Wo die Seiten liegen

Jede Operation erhält eine Seite unter `/api/<id>/<operation-slug>`. Der Slug ist die `operationId` in Kebab-Case:

{% table %}
* `operationId`
* Seiten-URL
---
* `forgeRing`
* `/api/rings/forge-ring`
---
* `getRing`
* `/api/rings/get-ring`
---
{% /table %}

Den Teil `/api/<id>` können Sie mit `routePrefix` ändern. Siehe [API-Registry](/de/configuration/api-registry).

{% callout type="tip" title="Live ansehen" %}
Die Seite [Retrieve a ring](https://www.api-demo.mordoc.dev/api/rings/get-ring) wurde ohne zusätzlichen Aufwand aus einer Spezifikation erzeugt.
{% /callout %}

## Mehr als eine Spezifikation

Fügen Sie für jede Spezifikation einen Eintrag hinzu. Jede Spezifikation erhält ihre eigene `id`, ihr eigenes URL-Präfix und ihren eigenen Enrichment-Ordner:

```yaml
- id: fellowship
  spec: fellowship.yaml
- id: rings
  spec: rings.yaml
```

## Nächster Schritt

[Operationen in der Navigation verlinken](/de/api-reference/link-operations-in-navigation).
