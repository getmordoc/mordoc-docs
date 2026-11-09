---
title: Warnungen und Fehler
description: Verstehen Sie, was der Build der API-Referenz meldet, warum er es meldet und wie Sie es beheben.
---

Der Build der API-Referenz folgt einer Regel: **Probleme, die die Website falsch machen, lassen den Build scheitern, und Probleme, die sie weniger vollständig machen, warnen nur.**

Die Website wird immer veröffentlicht, und zwar als die Spezifikation plus alles an Enrichment, was angewendet werden konnte.

## Mehr Details sehen

Standardmäßig wird jede Warnung als einzelne Zeile ausgegeben. Fügen Sie `--verbose` hinzu, um mehr zu sehen, etwa die vollständige Liste der undokumentierten Felder:

```bash
npm run build -- --verbose
```

## Fehler, die den Build scheitern lassen

Beheben Sie diese, bevor die Website gebaut werden kann.

{% table %}
* Was Sie sehen
* Warum
* Lösung
---
* `Spec "<file>" is not valid OpenAPI:`
* Die Spezifikation enthält einen Fehler.
* Beheben Sie die Spezifikation an der Quelle und exportieren Sie sie erneut.
---
* `config/api.yaml: API "<id>" declares spec "<file>", but ... does not exist.`
* Die Registry verweist auf eine fehlende Datei.
* Legen Sie die Datei in `api/specs/` ab oder korrigieren Sie den Namen.
---
* `<id>: <method> <path> has no "operationId".`
* Eine Operation hat keine `operationId`.
* Fügen Sie eine eindeutige `operationId` hinzu.
---
* `operationId "<name>" is used by both ... Operation ids must be unique.`
* Zwei Operationen teilen sich einen Namen.
* Benennen Sie eine davon in der Spezifikation um.
---
* `Navigation references operation "<name>", which no registered spec declares.`
* Ein `operation:`-Eintrag in der Seitenleiste hat keine passende Operation.
* Prüfen Sie die Schreibweise oder entfernen Sie den Eintrag.
---
* `Navigation entry "<label>" points at "<path>", which is not a route.`
* Ein `path:` unter dem URL-Präfix einer API führt ins Leere.
* Verwenden Sie stattdessen `operation:` oder erstellen Sie die Seite.
---
* `Route collision at "<path>"`
* Zwei Seiten beanspruchen dieselbe URL.
* Benennen Sie die Seite um oder ändern Sie den `routePrefix`.
---
{% /table %}

## Warnungen

Diese stoppen den Build nicht. Der betroffene Eintrag wird übersprungen.

{% table %}
* Was Sie sehen
* Lösung
---
* `no operation with operationId "<name>" — file skipped.`
* Benennen Sie die Datei in `operations/` so um, dass sie zu einer `operationId` passt.
---
* `no component schema named "<name>" — file skipped.`
* Benennen Sie die Datei in `schemas/` so um, dass sie zu einem Schema in der Spezifikation passt.
---
* `"<field>" does not match any field in ... entry skipped. Valid fields: ...`
* Verwenden Sie einen Feldnamen aus der Liste in der Meldung.
---
* `"<field>" is ambiguous in ... Use the full dotted path.`
* Schreiben Sie den vollständigen Pfad, etwa `quest.destination`.
---
* `{% params in="response" %} requires a "status" attribute`
* Fügen Sie den Status hinzu, zum Beispiel `status="403"`.
---
* `declares no <status> response`
* Verwenden Sie einen Statuscode, den die Operation deklariert.
---
* `content before the first "###" entry inside a {% params %} block is ignored`
* Verschieben Sie diesen Text aus dem Block heraus.
---
* `has a non-text badge — badge dropped`
* Schreiben Sie das Badge als Text in Anführungszeichen.
---
* `is badged "conditional" but has no description`
* Erklären Sie die Bedingung in der Beschreibung des Feldes.
---
* `filename must be "request.<case>.json" or "response.<status>.json"`
* Benennen Sie die Beispieldatei um.
---
* `invalid JSON`
* Korrigieren Sie das JSON in der Beispieldatei.
---
* `<n> operation(s) reachable only by URL (no nav entry)`
* Fügen Sie die aufgeführten Operationen zur Seitenleiste hinzu, oder ignorieren Sie dies, wenn es beabsichtigt ist.
---
* `<id>: <n>% of fields documented`
* Nur zur Information. Führen Sie den Build mit `--verbose` aus, um die fehlenden Felder zu sehen.
---
{% /table %}

## Warnungen in Fehler umwandeln

Wenn Ihr Team möchte, dass jede Warnung den Build scheitern lässt, setzen Sie `strict: true` in `config/api.yaml`. Siehe [API-Registry](/de/configuration/api-registry).

## Nächster Schritt

[Die API-Registry konfigurieren](/de/configuration/api-registry).
