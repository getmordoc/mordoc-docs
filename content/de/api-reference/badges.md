---
title: Badges
description: Kennzeichnen Sie API-Felder als bedingt, schreibgeschützt, Beta oder mit allem anderen, was Leser bemerken sollen.
---

Ein Badge ist ein kleines Label neben einem Feldnamen. Verwenden Sie es für einen schnellen Hinweis, der nicht in einen ganzen Satz gehört.

OpenAPI kann weder ein bedingtes Feld noch ein eigenes Label ausdrücken, daher liegen Badges in Enrichment-Dateien. Anders als Beschreibungs-Patches sind sie **langfristig**: Behalten Sie sie, solange das Feld sie braucht.

## Ein Badge hinzufügen

Schreiben Sie das Badge in die `###`-Überschrift des Feldes in einer Enrichment-Datei:

```markdown {% process=false %}
{% params %}
### dark_lord_approval {% badge="conditional" %}
Required only when `kind` is `one`.
{% /params %}
```

Regeln:

* Ein Badge pro Feld.
* Der Wert muss ein Text in Anführungszeichen sein.

## Conditional

`conditional` ist ein reserviertes Wort für ein Feld, das nur in manchen Situationen gilt:

```markdown {% process=false %}
### dark_lord_approval {% badge="conditional" %}
Required only when `kind` is `one`.
```

Es wird als bernsteinfarbenes Label angezeigt. Ein bloßes Label sagt den Lesern nicht, wie die Bedingung lautet, erklären Sie sie deshalb immer in der Beschreibung des Feldes. Andernfalls warnt Sie der Build.

{% callout type="tip" title="Live ansehen" %}
Auf der Seite [Forge a ring](https://www.api-demo.mordoc.dev/api/rings/forge-ring) ist das Feld `dark_lord_approval` bedingt.
{% /callout %}

## Eigene Badges

Jeder andere Text wird genau so zum Badge, wie Sie ihn schreiben:

```markdown {% process=false %}
### corruption_level {% badge="Read-only" %}
A value from 0 to 100 that grows each day a ring is worn.
```

Alle diese Badges teilen sich einen Stil. Wählen Sie kurze Wörter, etwa `Read-only` oder `Beta`.

{% callout type="tip" title="Live ansehen" %}
Die Seite [Retrieve a ring](https://www.api-demo.mordoc.dev/api/rings/get-ring) zeigt die Badges `Read-only` und `Beta`.
{% /callout %}

## Deprecated ist separat

Ein `Deprecated`-Badge schreiben Sie nicht selbst. Es stammt aus `deprecated: true` in der Spezifikation. Siehe [Ihre Spezifikation vorbereiten](/de/api-reference/prepare-your-spec).

## Wenn ein Badge falsch ist

Ein leeres Badge wird ignoriert. Ein Badge, das kein Text in Anführungszeichen ist, wird verworfen, und der Build gibt eine Warnung aus.

## Nächster Schritt

[Warnungen und Fehler beheben](/de/api-reference/warnings-and-errors).
