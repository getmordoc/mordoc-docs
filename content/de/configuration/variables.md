---
title: Variablen
description: Definieren Sie wiederverwendbare Textwerte für Ihre Mordoc-Inhalte.
---

Variablen ermöglichen es Ihnen, einen Wert einmal zu schreiben und auf vielen Seiten wiederzuverwenden.

Sie sind nützlich für Namen, Versionen, URLs, Support-Adressen oder andere kleine Textstücke, die sich später ändern können.

## Die Variablendatei erstellen

Variablen befinden sich in dieser optionalen Datei:

```text
config/variables.yaml
```

Erstellen Sie sie nur, wenn Sie Werte haben, die Sie wiederverwenden möchten.

## Eine Variable hinzufügen

Beginnen Sie mit einem einfachen Namen und Wert:

```yaml
productName: Acme
supportEmail: support@example.com
currentVersion: "1.0"
```

Verwenden Sie Namen, die beschreiben, was der Wert bedeutet.

Einfache Werte wie Namen, E-Mail-Adressen und einfache URLs benötigen in der Regel keine Anführungszeichen.

Verwenden Sie Anführungszeichen, wenn ein Wert als Text behandelt werden soll, aber wie eine Zahl aussieht, oder wenn er Zeichen enthält, die YAML möglicherweise besonders behandelt.

## Eine Variable im Inhalt verwenden

Sobald eine Variable definiert ist, können Sie sie in Markdown-Inhalten verwenden:

```markdown {% process=false %}
Willkommen bei {% $productName %}.
```

Mordoc ersetzt die Variable durch den Wert aus `config/variables.yaml`.

Mit dieser Variable:

```yaml
productName: Acme
```

Sehen Leser:

```text
Willkommen bei Acme.
```

## Variablen für wiederholte Werte verwenden

Variablen sind am hilfreichsten, wenn derselbe Wert an mehreren Stellen erscheint.

Zum Beispiel:

```yaml
supportEmail: support@example.com
```

Verwenden Sie es dann überall, wo Leser die Support-Adresse benötigen:

```markdown {% process=false %}
Senden Sie eine E-Mail an {% $supportEmail %}, wenn Sie Hilfe benötigen.
```

Wenn sich die Adresse später ändert, müssen Sie nur `config/variables.yaml` aktualisieren.

## Variablen in Links und Bildern verwenden

`{% $variableName %}` funktioniert nur im laufenden Text. Das Ziel eines Links oder Bildes wird als reiner Text analysiert, bevor Mordoc es überhaupt sieht, sodass eine Variable, die direkt in die Klammern geschrieben wird, nie aufgelöst wird:

```markdown
[Support kontaktieren]($SUPPORT_PORTAL_URL)
```

Dies zeigt den literalen Text `$SUPPORT_PORTAL_URL` als Adresse an, nicht den Wert aus `config/variables.yaml`.

Verwenden Sie für einen Link oder ein Bild, das eine Variable benötigt, stattdessen den `link`- oder `image`-Tag:

```markdown {% process=false %}
{% link path=$SUPPORT_PORTAL_URL %}Support kontaktieren{% /link %}
```

```markdown {% process=false %}
{% image src=$IMAGE_LINK alt="Grafik" /%}
```

Die Variable muss weiterhin in `config/variables.yaml` definiert werden:

```yaml
SUPPORT_PORTAL_URL: https://support.example.com
```

## Variablen einfach halten

Variablen funktionieren am besten für kurze Textwerte.

Gute Beispiele:

* Produktnamen
* Versionsnummern
* Support-E-Mail-Adressen
* Häufig verwendete Website-URLs

Vermeiden Sie die Verwendung von Variablen für lange Absätze. Langer Inhalt ist in der Regel klarer, wenn er direkt auf der Seite bleibt.

## Nächster Schritt

[Assets und Branding konfigurieren](/de/configuration/assets-and-branding).
