---
title: Beschreibungen anreichern
description: Patchen Sie Beschreibungen in erzeugten API-Seiten mit Markdown-Dateien und fügen Sie Badges hinzu, die die OpenAPI-Spezifikation nicht ausdrücken kann.
---

Die OpenAPI-Spezifikation ist die maßgebliche Quelle für Ihre API. Entwickler bauen direkt darauf auf, daher ist die beste Korrektur für eine falsche oder fehlende Beschreibung eine Änderung in der Spezifikation selbst.

Enrichment dient zwei verschiedenen Aufgaben:

* **Ein schneller Patch.** Der Text der Spezifikation ist falsch oder dünn und lässt sich im Moment nicht korrigieren. Eine Markdown-Datei im Dokumentationsprojekt behebt in der Zwischenzeit, was Leser sehen. Das ist **kurzfristig**. Sobald die Spezifikation korrigiert ist, löschen Sie den Patch.
* **Dinge, die OpenAPI nicht ausdrücken kann.** Badges wie [`conditional`](/de/api-reference/badges), Callouts und Links zu Leitfadenseiten haben in der Spezifikation keinen Platz. Enrichment ist ihre **langfristige** Heimat.

Enrichment ist optional und sollte sparsam eingesetzt werden. Ein Endpunkt mit 40 Feldern braucht vielleicht nur bei dreien Anmerkungen.

{% callout type="warning" title="Patches entfernen, wenn die Spezifikation korrigiert ist" %}
Ein Patch in einer `schemas/`-Datei ersetzt die Beschreibung der Spezifikation. Wird die Spezifikation später verbessert, der Patch bleibt aber bestehen, sehen Leser weiterhin den alten Patch statt des besseren Spezifikationstextes. Überprüfen Sie Ihre Enrichment-Dateien, sobald sich die Spezifikation ändert.
{% /callout %}

{% callout type="tip" title="Live ansehen" %}
Die Seite [List members](https://www.api-demo.mordoc.dev/api/fellowship/list-members) mischt Text aus der Spezifikation mit Enrichment. Die Seite [Forge a ring](https://www.api-demo.mordoc.dev/api/rings/forge-ring) ergänzt einen Callout und Anmerkungen.
{% /callout %}

## Der Dateiname ist das Ziel

Enrichment-Dateien liegen unter `api/enrichment/<id>/`, wobei `<id>` die `id` der Spezifikation aus `config/api.yaml` ist. Der Dateiname teilt Mordoc mit, was die Datei beschreibt:

```text
api/enrichment/rings/operations/forgeRing.md
api/enrichment/rings/schemas/Ring.md
```

* `operations/<operationId>.md` zielt auf eine einzelne Operation.
* `schemas/<SchemaName>.md` zielt auf ein gemeinsam genutztes Schema, überall dort, wo es verwendet wird.

Diese Dateien haben kein Frontmatter. Schreiben Sie das Markdown direkt.

## Ein Feld beschreiben

Setzen Sie Feldanmerkungen in einen `{% params %}`-Block. Jede `###`-Überschrift benennt ein Feld, und der Text darunter ist die Anmerkung:

```markdown {% process=false %}
{% params %}
### smith_id
Must belong to a smith registered with the guild of the requested `kind`.
{% /params %}
```

Die Überschrift muss dem Feldnamen in der Spezifikation entsprechen.

## Den richtigen Geltungsbereich wählen

Ein einfacher `{% params %}`-Block beschreibt die Parameter und den Request-Body der Operation. Um eine Antwort zu beschreiben, nennen Sie den Statuscode:

```markdown {% process=false %}
{% params in="response" status="403" %}
### message
Explains which guild rule was broken.
{% /params %}
```

Der `status` ist erforderlich. Er muss eine Antwort sein, die die Operation deklariert.

## Auf verschachtelte Felder verweisen

Verwenden Sie in einer Operationsdatei einen Punkt-Pfad für ein verschachteltes Feld:

```markdown {% process=false %}
{% params %}
### quest.destination
The place the fellowship must reach, for example `Mount Doom`.
{% /params %}
```

Verwenden Sie in einer Schemadatei den einfachen Feldnamen. Wenn ein einfacher Name auf mehr als ein Feld passt, überspringt Mordoc ihn, und die Warnung listet die vollständigen Pfade zur Auswahl auf.

Um die richtige Schemadatei zu finden, sehen Sie sich das Feld auf der erzeugten Seite an. Dort steht der Schemaname, zum Beispiel `Region`.

## Wie Enrichment mit der Spezifikation zusammenwirkt

{% table %}
* Wo Sie es schreiben
* Was mit dem Text der Spezifikation passiert
---
* `schemas/<SchemaName>.md`
* **Ersetzt** die Beschreibung des Feldes.
---
* `operations/<operationId>.md` in einem `{% params %}`-Block
* **Hängt** Ihren Text als Anmerkung unter der Beschreibung **an**.
---
* `{% params mode="replace" %}`
* **Ersetzt** die Beschreibung auch in einer Operationsdatei.
---
* Text außerhalb eines `{% params %}`-Blocks in einer Operationsdatei
* **Ersetzt** die eigene Beschreibung der Operation am Seitenanfang.
---
{% /table %}

Verwenden Sie den Text auf Operationsebene für Einführungen, Callouts und Links. Dieser Text erscheint zum Beispiel am Anfang der Seite Forge a ring:

```markdown {% process=false %}
Forges a new ring of the requested kind and metal.

{% callout type="warning" title="Handle with care" %}
A ring of kind `one` cannot be undone.
{% /callout %}
```

Innerhalb eines Eintrags können Sie beliebiges Markdown oder beliebige Mordoc-Tags verwenden: Callouts, Tabellen, Code-Blöcke, Links und Variablen.

Die eigene Beschreibung einer Antwort kann nicht angereichert werden. Ihre Felder dagegen schon.

## Beispiel-Payloads hinzufügen

Beispiele stammen aus drei Quellen, in dieser Reihenfolge:

1. Den `examples` der Spezifikation.
2. Dateien, die Sie unter `api/examples/` hinzufügen.
3. Einem aus dem Schema erzeugten Beispiel, wenn eine Anfrage oder Antwort keines hat, damit das Panel nie leer ist.

Fügen Sie eigene Dateien hinzu, wenn der Spezifikation ein nützlicher Fall fehlt:

```text
api/examples/rings/forgeRing/request.the-one-ring.json
api/examples/rings/forgeRing/response.403-unlicensed.json
```

* Benennen Sie Anfragedateien `request.<case>.json`.
* Benennen Sie Antwortdateien `response.<status>.json`, mit einem optionalen Suffix wie `403-unlicensed`.
* Der Fallname wird zum Label. `the-one-ring` wird als „The one ring“ angezeigt.
* Hat eine Datei denselben Namen wie ein Beispiel der Spezifikation, hat Ihre Datei Vorrang.

Dieselben Dateien dienen allen Sprachen. Eine Datei mit falschem Namen oder ungültigem JSON wird mit einer Warnung übersprungen.

Mordoc erzeugt außerdem ein cURL-Beispiel für jedes Anfragebeispiel. Diese schreiben Sie nicht selbst.

{% callout type="tip" title="Live ansehen" %}
Die Seite [Light a beacon](https://www.api-demo.mordoc.dev/api/watch/light-beacon) zeigt Beispiele aus der Spezifikation neben selbst verfassten.
{% /callout %}

## Was, wenn ein Ziel falsch ist?

Ein fehlendes Dateiziel oder ein unbekanntes Feld lässt den Build nie scheitern. Mordoc überspringt diesen Eintrag und gibt eine Warnung aus. Siehe [Warnungen und Fehler](/de/api-reference/warnings-and-errors).

## Patches kurzlebig halten

Wenn Sie eine Beschreibung patchen, teilen Sie dem API-Team mit, was Sie geändert haben, damit es das in der Spezifikation beheben kann. Sobald die neue Spezifikation erscheint, löschen Sie den Eintrag. Behalten Sie nur Badges, Callouts und anderen Inhalt, den die Spezifikation nicht aufnehmen kann.

## Nächster Schritt

[Felder mit Badges kennzeichnen](/de/api-reference/badges).
