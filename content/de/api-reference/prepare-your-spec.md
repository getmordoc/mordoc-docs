---
title: Ihre Spezifikation vorbereiten
description: Was das API-Team bereitstellen muss, damit Mordoc eine gute API-Referenz erzeugen kann.
---

Diese Seite richtet sich an das Team, das die API verantwortet. Redakteure können sie unverändert weitergeben.

Mordoc liest eine Standard-OpenAPI-Datei. Wenn die Datei gültig ist und jede Operation eine `operationId` hat, erhalten Sie eine funktionierende Referenz.

## Wo die Spezifikation liegt

Legen Sie die Spezifikation im Ordner `api/specs/` ab:

```text
api/specs/rings.yaml
```

Erzeugen Sie diese Datei aus Ihrem API-Code oder Ihren Tools. Bearbeiten Sie sie im Dokumentationsprojekt nicht von Hand, da der nächste Export Ihre Änderungen überschreiben würde.

## Die Spezifikation als maßgebliche Quelle behalten

Entwickler entwickeln direkt gegen diese Spezifikation, daher hilft jede Verbesserung hier ihnen ebenso wie der Dokumentation. Beheben Sie falschen oder fehlenden Text in der Spezifikation, an der Quelle.

Wenn eine Korrektur nicht bis zum nächsten Release warten kann, können Redakteure den Text als kurzfristige Maßnahme mit [Enrichment](/de/api-reference/enrich-descriptions) patchen. Diese Patches sollten entfernt werden, sobald die Spezifikation nachgezogen hat.

## Was erforderlich ist

* **Eine gültige OpenAPI-Datei.** Nur Fehler lassen den Build scheitern. Stilwarnungen des Linters werden ignoriert.
* **Eine `operationId` für jede Operation.** Sie muss in der gesamten Spezifikation eindeutig sein.

Die `operationId` wird zur URL der Seite und zum Namen ihrer Enrichment-Datei, wählen Sie sie also sorgfältig:

```yaml
paths:
  /rings:
    post:
      operationId: forgeRing
      summary: Forge a ring
```

Diese Operation erhält die URL `/api/rings/forge-ring`. Wenn Sie die `operationId` später umbenennen, wandert die Seite zu einer neuen URL.

Die `summary` wird zum Seitentitel und zum Standard-Label in der Seitenleiste. Halten Sie sie kurz.

## Was die Dokumentation ohne Mehraufwand verbessert

Nichts davon ist erforderlich, aber jeder Punkt macht die erzeugte Seite besser:

* **Echte `description`-Texte** für Operationen, Parameter und Felder.
* **Benannte `examples`** für Anfrage- und Antwort-Bodys.
* **`servers`.** Die URL des ersten Servers wird als Host in cURL-Beispielen verwendet. Ohne Server verwendet Mordoc `https://api.example.com`.
* **`deprecated: true`** für Operationen, die auslaufen. Die Seite kennzeichnet sie als veraltet.

{% callout type="tip" title="Live ansehen" %}
Die Seite [Retrieve a member](https://www.api-demo.mordoc.dev/api/fellowship/get-member) verwendet ausschließlich die Spezifikation, ganz ohne Enrichment.
{% /callout %}

## Webhooks

Mordoc dokumentiert Webhooks aus der `webhooks`-Map auf oberster Ebene einer OpenAPI-3.1-Spezifikation. Die ältere Erweiterung `x-webhooks` aus OpenAPI 3.0 wird nicht gelesen.

```yaml
webhooks:
  beaconLit:
    post:
      operationId: beaconLit
      summary: Beacon lit
```

Ein Webhook funktioniert wie jede andere Operation:

* Er benötigt eine `operationId`, und dieser Name muss sowohl in `paths` als auch in `webhooks` eindeutig sein.
* Sie verlinken ihn in der Seitenleiste mit `operation:`.
* Sie können ihn auf dieselbe Weise anreichern.

Die Seite zeigt den Namen des Webhooks dort, wo eine normale Operation ihre URL zeigt, und sie hat kein cURL-Beispiel.

{% callout type="tip" title="Live ansehen" %}
Öffnen Sie die Webhook-Seite [Beacon lit](https://www.api-demo.mordoc.dev/api/watch/beacon-lit-event).
{% /callout %}

## Nächster Schritt

[Eine API-Referenz einrichten](/de/api-reference/set-up).
