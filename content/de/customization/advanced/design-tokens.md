---
title: Design Tokens
description: Überschreiben Sie die globalen Farb-Tokens, auf die jede Komponente zurückgreift, über die Akzentfarbe hinaus.
---

Die [Grundlegende Anpassung](/de/customization/basic/theme-css) behandelt `--accent`, die eine Farbe, die fast jede Website ändert. Dieselbe Datei, `config/styles/theme.css`, enthält auch eine kleine Reihe weiterer globaler Tokens: die Farben, auf die jede Komponente zurückgreift, sofern sie nicht ihre eigenen festlegt.


## Die Theme-Datei öffnen

```text
config/styles/theme.css
```

Fügen Sie nur die Tokens hinzu, die Sie ändern möchten, innerhalb von `:root`:

```css
:root {
  --color-bg: #fbfaf7;
  --color-border: #e8e3d8;
}
```

## Flächen und Text

{% table %}
* Token
* Was es steuert
---
* `--color-bg`
* Der Seitenhintergrund, hinter allem.
---
* `--color-surface`
* Ein leicht abweichender Hintergrund für erhöhte oder vertiefte Flächen: die Eingabezeile des Suchmodals, Tabellenüberschriften in Ihrem geschriebenen Inhalt und ähnliche Oberflächenelemente.
---
* `--color-border`
* Feine Trennlinien, die auf der gesamten Website verwendet werden: Flächenränder, Trennlinien, die Linie unter dem Header.
---
* `--color-fg`
* Primärer Text in der gesamten Oberfläche: Überschriften, Navigationslabels, Schaltflächen.
---
* `--color-content-fg`
* Speziell der Artikel-Fließtext: Markdown-Absätze und Listentext. Getrennt von `--color-fg` gehalten, damit Sie den Kontrast von Überschriften und Lesetext unabhängig voneinander abstimmen können.
---
* `--color-fg-muted`
* Sekundärer oder Meta-Text sowie gedämpfte Icons: Beschreibungen, Zeitstempel, Breadcrumbs, Platzhaltertext.
---
* `--color-bg-hover`
* Hintergrund, der bei Hover für interaktive Zeilen angezeigt wird: Dropdown-Elemente, Menü-Schaltflächen und ähnliche Steuerelemente, die keine Links oder Schaltflächen sind.
{% /table %}

## Dunkelmodus

Überschreiben Sie jeden dieser Werte erneut innerhalb von `.dark`, für einen Wert, der nur im Dunkelmodus gilt:

```css
:root {
  --color-bg: #fbfaf7;
}

.dark {
  --color-bg: #14120f;
}
```

## Beispiel theme.css

Ein Beispiel mit allen Tokens, die Sie in `theme.css` für den Hell- und den Dunkelmodus festlegen können:

```css
:root {
  --accent: #b45309;

  --color-bg: #fbfaf7;
  --color-surface: #f2ede4;
  --color-border: #e8e3d8;

  --color-fg: #211f1a;
  --color-content-fg: #3a362e;
  --color-fg-muted: #7a7266;

  --color-bg-hover: #efe9de;
}

.dark {
  --accent: #f0a659;

  --color-bg: #14120f;
  --color-surface: #1d1a15;
  --color-border: #2c281f;

  --color-fg: #f3efe6;
  --color-content-fg: #d8d2c4;
  --color-fg-muted: #948c7c;

  --color-bg-hover: #221f19;
}
```

## Nächster Schritt

- [Das App Layout anpassen](/de/customization/advanced/app-layout).
