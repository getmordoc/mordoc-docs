---
title: Überblick über die API-Referenz
description: Erzeugen Sie aus einer OpenAPI-Spezifikation eine vollständige API-Referenz und verbessern Sie sie anschließend mit einfachem Markdown.
---

Mordoc kann aus einer OpenAPI-Spezifikation eine vollständige API-Referenz erzeugen. Jede Operation in der Spezifikation wird zu einer eigenen Seite, ohne dass Sie Seiten von Hand schreiben müssen.

Jede erzeugte Seite zeigt:

* Die Abschnitte für Anfrage und Antwort, mit einem Feldbaum für jeden Body.
* Beispielanfragen und -antworten.
* Ein cURL-Beispiel für jedes Anfragebeispiel.
* Deep Links zu jedem Abschnitt und jedem Feld sowie Suchergebnisse, die das passende Feld öffnen.

{% callout type="tip" title="Live ansehen" %}
Alles auf dieser Seite läuft in der [Mordoc-API-Demo](https://api-demo.mordoc.dev/). Öffnen Sie dort beim Lesen eine Seite.
{% /callout %}

## Die Spezifikation ist die maßgebliche Quelle

Entwickler verwenden die OpenAPI-Spezifikation direkt, um gegen Ihre API zu entwickeln. Damit ist sie die einzige maßgebliche Quelle und der beste Ort, um jedes Problem mit einem Feld, einer Beschreibung oder einem Beispiel zu beheben. Eine Korrektur in der Spezifikation verbessert die Dokumentation, die erzeugten Clients und jedes andere Tool, das sie liest.

Streben Sie deshalb eine Spezifikation an, die von sich aus eine gute Referenz ergibt. Die Spezifikation allein erzeugt eine vollständige Referenz.

## Enrichment ist ein schneller Patch

Manchmal ist eine Beschreibung falsch oder dünn, und das API-Team kann sie heute nicht beheben. Mit Enrichment können Redakteure diesen Text im Dokumentationsprojekt patchen, damit Leser nicht warten müssen. Betrachten Sie diese Patches als kurzfristig. Sobald die Spezifikation korrigiert ist, löschen Sie den Patch.

{% table %}
* Enrichment verwenden für
* Lebensdauer
---
* Eine Beschreibung, Notiz oder ein Beispiel patchen, das in der Spezifikation falsch ist oder fehlt
* **Kurzfristig.** Entfernen Sie es, sobald die Spezifikation korrigiert ist.
---
* Dinge, die OpenAPI nicht ausdrücken kann, etwa `conditional` und eigene [Badges](/de/api-reference/badges) oder Callouts und Links zu Leitfadenseiten
* **Langfristig.** Dort gehören sie hin.
---
{% /table %}

Enrichment fügt niemals Felder hinzu, entfernt sie nicht und ändert auch nicht ihren Typ. Für die Struktur bleibt die Spezifikation die maßgebliche Quelle.

## Wo was liegt

Eine API-Referenz fügt Ihrem Projekt einige Dateien und Ordner hinzu:

```text
config/api.yaml                          registers your specs
api/specs/                               OpenAPI files, never hand-edited
api/enrichment/<id>/operations/          patches and badges for one operation per file
api/enrichment/<id>/schemas/             patches and badges for one shared schema per file
api/examples/<id>/<operationId>/         optional extra example payloads
```

Die `<id>` ist der Name, den Sie jeder Spezifikation in `config/api.yaml` geben. Siehe [Eine API-Referenz einrichten](/de/api-reference/set-up).

Die [Build-Hinweise der Demo](https://api-demo.mordoc.dev/guides/how-this-is-built) zeigen dieses Layout in einem echten Projekt.

## Was Sie als Nächstes lesen sollten

Wählen Sie die Seite, die zu Ihrer Rolle passt:

* **Sie sind für die API-Spezifikation verantwortlich:** [Ihre Spezifikation vorbereiten](/de/api-reference/prepare-your-spec).
* **Sie fügen einer Website eine API-Referenz hinzu:** [Eine API-Referenz einrichten](/de/api-reference/set-up).
* **Sie patchen Beschreibungen oder fügen Badges hinzu:** [Beschreibungen anreichern](/de/api-reference/enrich-descriptions).

## Nächster Schritt

[Ihre Spezifikation vorbereiten](/de/api-reference/prepare-your-spec).
