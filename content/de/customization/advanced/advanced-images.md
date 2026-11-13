---
title: Erweiterte Bilder
description: Gestalten Sie die Bildunterschrift und die vergrößerte Ansicht erweiterter Bilder.
---

Ein erweitertes Bild zeigt eine Bildunterschrift und öffnet sich per Klick vergrößert. Siehe [Erweiterte Bilder](/de/writing-content/advanced-images) für die Markdown-Syntax. Diese Seite behandelt sein Erscheinungsbild.

## Die Override-Datei öffnen

```text
config/styles/image.css
```

Erweiterte Bilder und [Bilder](/de/customization/advanced/images) werden in derselben Datei gestaltet und teilen sich `--image-radius` und `--image-shadow`.

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--image-radius`
* Eckenradius, gemeinsam für das Bild und seine vergrößerte Ansicht.
---
* `--image-shadow`
* Schatten um das Bild.
---
* `--image-caption-color`
* Textfarbe der Bildunterschrift. Standardmäßig `--color-fg-muted`.
---
* `--image-overlay-bg`
* Hintergrund hinter der vergrößerten Ansicht.
---
* `--image-close-button-radius`
* Eckenradius des Schließen-Buttons der vergrößerten Ansicht.
{% /table %}

## Beispiel image.css

Eine `config/styles/image.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --image-radius: 4px;
  --image-shadow: none;
  --image-caption-color: #6b7280;
  --image-overlay-bg: rgba(0, 0, 0, 0.82);
  --image-close-button-radius: 6px;
}

.dark {
  --image-caption-color: #9ca3af;
}
```

## Nächster Schritt

- [Den Hero gestalten](/de/customization/advanced/hero).
