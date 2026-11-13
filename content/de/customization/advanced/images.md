---
title: Bilder
description: Gestalten Sie einfache Bilder, die in Markdown-Inhalten platziert werden.
---

Ein Bild ist ein Standard-Markdown-`![]()`-Bild. Siehe [Bilder](/de/writing-content/images) für die Markdown-Syntax. Diese Seite behandelt sein Erscheinungsbild.

## Die Override-Datei öffnen

```text
config/styles/image.css
```

Bilder und [erweiterte Bilder](/de/customization/advanced/advanced-images) werden in derselben Datei gestaltet und teilen sich `--image-radius` und `--image-shadow`.

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--image-radius`
* Eckenradius des Bildes.
---
* `--image-shadow`
* Schatten um das Bild.
{% /table %}

## Beispiel image.css

Eine `config/styles/image.css`, die jeden Token auf dieser Seite festlegt:

```css
:root {
  --image-radius: 4px;
  --image-shadow: none;
}
```

## Nächster Schritt

- [Erweiterte Bilder gestalten](/de/customization/advanced/advanced-images).
