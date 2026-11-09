---
title: API-Registry
description: Registrieren Sie OpenAPI-Spezifikationen und legen Sie fest, wo ihre Seiten erscheinen.
---

Die API-Registry teilt Mordoc mit, welche OpenAPI-Spezifikationen in API-Seiten umgewandelt werden sollen.

## Die Registry-Datei erstellen

Die Registry liegt hier:

```text
config/api.yaml
```

Erstellen Sie sie nur, wenn Ihr Projekt eine API-Referenz hat. Ohne sie überspringt Mordoc alle API-Funktionen.

## Eine Spezifikation registrieren

Die einfachste Datei ist eine Liste von Spezifikationen:

```yaml
- id: rings
  spec: rings.yaml
```

Jeder Eintrag akzeptiert diese Felder:

{% table %}
* Feld
* Erforderlich
* Was es bewirkt
---
* `id`
* Ja
* Ein kurzer Name für die API. Nur Buchstaben, Ziffern, Bindestriche und Unterstriche. Er muss eindeutig sein. Er benennt die Enrichment- und Beispielordner und ist das Standard-URL-Präfix.
---
* `spec`
* Ja
* Der Dateiname der Spezifikation innerhalb von `api/specs/`.
---
* `routePrefix`
* Nein
* Das URL-Präfix für die Seiten dieser API. Standardmäßig `/api/<id>`.
---
{% /table %}

## Ändern, wo Seiten erscheinen

Standardmäßig liegt eine Operationsseite unter `/api/<id>/<operation-slug>`. Mit `routePrefix` ändern Sie das:

```yaml
- id: rings
  spec: rings.yaml
  routePrefix: /reference
```

Jetzt wird `forgeRing` unter `/reference/forge-ring` geöffnet.

{% table %}
* `routePrefix`
* URL von `forgeRing`
---
* nicht gesetzt
* `/api/rings/forge-ring`
---
* `/reference`
* `/reference/forge-ring`
---
* `/`
* `/forge-ring`
---
{% /table %}

Verwenden Sie `/` für eine Website, die ausschließlich aus einer API-Referenz besteht.

## Mehrere Spezifikationen registrieren

Fügen Sie für jede Spezifikation einen Eintrag hinzu. Jede `id` muss anders sein:

```yaml
- id: fellowship
  spec: fellowship.yaml
- id: rings
  spec: rings.yaml
```

## Den Build bei jeder Warnung scheitern lassen

Um die längere Dateiform zu verwenden, verschieben Sie die Liste unter `specs` und fügen Sie `strict` hinzu:

```yaml
strict: true
specs:
  - id: rings
    spec: rings.yaml
```

Mit `strict: true` lässt jede API-Warnung den Build scheitern. Das schließt die Warnung für undokumentierte Felder ein, sodass jedes Feld ohne Beschreibung einen strikten Build scheitern lässt. Verwenden Sie dies nur, wenn Sie diese Regel wollen. Siehe [Warnungen und Fehler](/de/api-reference/warnings-and-errors).

## Häufige Fehler

Der Build stoppt mit einer Meldung, die mit `config/api.yaml` beginnt, wenn:

* Einem Eintrag `id` oder `spec` fehlt.
* Eine `id` andere Zeichen als Buchstaben, Ziffern, Bindestriche und Unterstriche enthält.
* Zwei Einträge dieselbe `id` haben.
* Die Datei keine Spezifikationen auflistet.
* Eine `spec`-Datei in `api/specs/` fehlt.

## Nächster Schritt

[Ihre Sprachen einrichten](/de/configuration/languages).
