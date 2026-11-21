---
title: Suche
description: Gestalten Sie die Suchleiste im Header und das Vollbild-Suchmodal, das sie öffnet.
---

Suche ist eine Funktion, aufgeteilt auf zwei Dateien, weil sie aus zwei unterschiedlichen Oberflächenelementen besteht: der Leiste im Header und dem Vollbild-Modal, das sie öffnet.

```text
┌───────────────────┐        ┌─────────────────────────────┐
│ 🔍 Search..   ⌘K │  --->  │ 🔍 [type to search...]  ✕  │
└───────────────────┘        ├─────────────────────────────┤
     Search Bar              │  Result title               │
                             │  matching excerpt…          │
                             │  Result title               │
                             │  matching excerpt…          │
                             └─────────────────────────────┘
                                     Search Modal
```

## Suchleiste

```text
config/styles/search-bar.css
```

{% table %}
* Token
* Was es steuert
---
* `--search-bar-width`
* Breite der Leiste auf dem Desktop. Standardmäßig schmaler beim `768px`-Breakpoint als bei `1024px` und darüber.
---
* `--search-bar-height`
* Höhe der Leiste.
---
* `--search-bar-radius`
* Eckenradius der Leiste.
---
* `--search-bar-padding`
* Horizontaler Abstand innerhalb der Leiste.
---
* `--search-bar-gap`
* Abstand zwischen dem Icon, dem Platzhaltertext und dem Tastenkürzel-Hinweis.
---
* `--search-bar-font-size`
* Schriftgröße des Platzhaltertexts.
---
* `--search-bar-icon-size`
* Größe des Such-Icons.
---
* `--search-bar-bg`
* Hintergrund der Leiste.
---
* `--search-bar-bg-hover`
* Hintergrund der Leiste bei Hover.
---
* `--search-bar-border`
* Randfarbe der Leiste.
---
* `--search-bar-border-hover`
* Randfarbe der Leiste bei Hover. Standardmäßig ein durchscheinender Farbton von `--accent`.
---
* `--search-bar-fg`
* Farbe des Icons und des Platzhaltertexts.
---
* `--search-bar-kbd-height`
* Höhe des Tastenkürzel-Chips im `⌘K`-Stil.
---
* `--search-bar-kbd-padding`
* Horizontaler Abstand des Tastenkürzel-Chips.
---
* `--search-bar-kbd-font-size`
* Schriftgröße des Tastenkürzel-Chips.
---
* `--search-bar-kbd-radius`
* Eckenradius des Tastenkürzel-Chips.
---
* `--search-bar-kbd-bg`
* Hintergrund des Tastenkürzel-Chips.
{% /table %}

## Suchmodal

```text
config/styles/search-modal.css
```

{% table %}
* Token
* Was es steuert
---
* `--modal-max-width`
* Maximale Breite des Modal-Panels.
---
* `--modal-overlay-bg`
* Hintergrund hinter dem Modal.
---
* `--modal-bg`
* Hintergrund des Modal-Panels. Standardmäßig `--color-bg`.
---
* `--modal-border`
* Rand des Modal-Panels. Standardmäßig `--color-border`.
---
* `--modal-shadow`
* Schlagschatten unter dem Modal-Panel.
---
* `--modal-radius`
* Eckenradius des Modal-Panels.
---
* `--modal-input-size`
* Schriftgröße des Sucheingabefelds.
---
* `--modal-result-radius`
* Eckenradius jeder Ergebniszeile.
---
* `--modal-result-hover`
* Hintergrund einer Ergebniszeile bei Hover. Standardmäßig `--color-bg-hover`.
---
* `--modal-result-selected`
* Hintergrund der per Tastatur ausgewählten Ergebniszeile.
---
* `--modal-kbd-radius`
* Eckenradius der kleinen Inline-Chips für den `Esc`-Hinweis und übereinstimmende Schlüsselwörter.
{% /table %}

## Beispiel search-bar.css

Eine `config/styles/search-bar.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --search-bar-width: 256px;
  --search-bar-height: 36px;
  --search-bar-radius: 999px;
  --search-bar-padding: 12px;
  --search-bar-gap: 8px;
  --search-bar-font-size: 14px;
  --search-bar-icon-size: 16px;
  --search-bar-bg: #ffffff;
  --search-bar-bg-hover: #f5f5f5;
  --search-bar-border: #e0e0e0;
  --search-bar-border-hover: color-mix(in oklch, #0d9488 30%, transparent);
  --search-bar-fg: #616161;
  --search-bar-kbd-height: 20px;
  --search-bar-kbd-padding: 6px;
  --search-bar-kbd-font-size: 10px;
  --search-bar-kbd-radius: 4px;
  --search-bar-kbd-bg: #ffffff;
}

.dark {
  --search-bar-bg: #121212;
  --search-bar-bg-hover: #242424;
  --search-bar-border: #383838;
  --search-bar-fg: #9e9e9e;
  --search-bar-kbd-bg: #1e1e1e;
}
```

## Beispiel search-modal.css

Eine `config/styles/search-modal.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --modal-max-width: 640px;
  --modal-overlay-bg: rgba(0, 0, 0, 0.45);
  --modal-bg: #ffffff;
  --modal-border: #e5e5e5;
  --modal-shadow: 0 24px 64px rgba(0, 0, 0, 0.22);
  --modal-radius: 16px;
  --modal-input-size: 16px;
  --modal-result-radius: 8px;
  --modal-result-hover: #f3f4f6;
  --modal-result-selected: #f0fdfa;
  --modal-kbd-radius: 4px;
}

.dark {
  --modal-overlay-bg: rgba(0, 0, 0, 0.65);
  --modal-bg: #161616;
  --modal-border: #2e2e2e;
  --modal-result-hover: #242424;
  --modal-result-selected: #0f2e2b;
}
```

## Nächster Schritt

- [Die Seitennavigation gestalten](/de/customization/advanced/side-navigation).
