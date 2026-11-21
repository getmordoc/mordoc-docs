---
title: Code-Blöcke
description: Gestalten Sie die Farben, die Kopfzeile und den Kopier-Button eines umzäunten Code-Blocks.
---

Code Block umschließt jeden umzäunten Code-Block in Ihrem Markdown-Inhalt. Siehe [Markdown-Grundlagen](/de/writing-content/markdown-basics). Diese Seite behandelt seine Farben, die Kopfzeile, den Rand und den Kopier-Button.

## Die Override-Datei öffnen

```text
config/styles/code-block.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--cb-bg`
* Hintergrund der Kopfzeile, die den Sprachnamen anzeigt: ein dunkleres Grau als der Code.
---
* `--cb-code-bg`
* Hintergrund des Codes selbst: hell im Hellmodus, dunkel im Dunkelmodus.
---
* `--cb-fg`
* Farbe von Code, der nicht hervorgehoben ist.
---
* `--cb-fg-muted`
* Farbe des Sprachnamens und des Kopier-Buttons.
---
* `--cb-hover-bg`
* Hintergrund des Kopier-Buttons bei Hover.
---
* `--cb-border`
* Rand um den gesamten Block und unter der Kopfzeile. Standardmäßig `--color-border`.
---
* `--cb-token-comment`, `--cb-token-punctuation`, `--cb-token-constant`, `--cb-token-string`, `--cb-token-operator`, `--cb-token-keyword`, `--cb-token-function`, `--cb-token-variable`
* Hervorhebungsfarben für Kommentare, Satzzeichen, Konstanten und Zahlen, Zeichenketten, Operatoren, Schlüsselwörter, Funktionen und Variablen. Mordoc legt eine Gruppe für den Hellmodus und eine für den Dunkelmodus fest; wählen Sie Farben, die auf `--cb-code-bg` gut lesbar sind.
---
* `--cb-radius`
* Eckenradius des gesamten Blocks.
---
* `--cb-copy-button-radius`
* Eckenradius des Kopier-Buttons.
{% /table %}

## Beispiel code-block.css

Eine `config/styles/code-block.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --cb-bg: #eeeeee;
  --cb-code-bg: #fafafa;
  --cb-fg: #1f2328;
  --cb-fg-muted: #59636e;
  --cb-hover-bg: rgba(0, 0, 0, 0.06);
  --cb-border: #e5e5e5;
  --cb-radius: 6px;
  --cb-copy-button-radius: 4px;

  --cb-token-comment: #59636e;
  --cb-token-punctuation: #1f2328;
  --cb-token-constant: #0550ae;
  --cb-token-string: #0a3069;
  --cb-token-operator: #8250df;
  --cb-token-keyword: #c62828;
  --cb-token-function: #673ab7;
  --cb-token-variable: #953800;
}

.dark {
  --cb-bg: #121212;
  --cb-code-bg: #1e1e1e;
  --cb-fg: #eceff1;
  --cb-fg-muted: #a1a1aa;
  --cb-hover-bg: rgba(255, 255, 255, 0.08);
  --cb-border: #2e2e2e;

  --cb-token-comment: #8b949e;
  --cb-token-punctuation: #cdd9e5;
  --cb-token-constant: #79c0ff;
  --cb-token-string: #7ee787;
  --cb-token-operator: #d2a8ff;
  --cb-token-keyword: #ff7b72;
  --cb-token-function: #d29922;
  --cb-token-variable: #ffa657;
}
```

Sie müssen nicht jeden Token wie in diesem Beispiel festlegen. Fügen Sie nur die hinzu, die Sie tatsächlich ändern möchten; jeder ausgelassene Token behält Mordocs Standardwert.

## Nächster Schritt

- [Diagramme gestalten](/de/customization/advanced/diagrams).
