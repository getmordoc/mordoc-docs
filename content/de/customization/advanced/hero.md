---
title: Hero
description: Gestalten Sie den Standard-Hintergrund und die Textfarben des Hero-Banners auf Landing-Pages.
---

Hero wird oben auf einer Landing-Page gerendert. Siehe [Landing-Pages](/de/writing-content/landing-pages) für die Markdown-Syntax. Jede von ihm verwendete Farbe ist eine website-weite Design-Entscheidung, die hier in CSS festgelegt wird; der `{% hero %}`-Tag selbst hat keine eigenen Farbattribute.

## Die Override-Datei öffnen

```text
config/styles/hero.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--hero-bg`
* Einfarbiger Hintergrund, verwendet, wenn ein Hero kein `background`-Bild hat. Standardmäßig `#f5f5f5`, im Dunkelmodus `#1e1e1e`: etwas dunkler als der Header.
---
* `--hero-title-color`
* Titel-Textfarbe. Standardmäßig `--color-fg`.
---
* `--hero-title-accent-color`
* Farbe der Akzentzeile des Titels (`titleAccent` in Markdown).
---
* `--hero-desc-color`
* Beschreibungs-Textfarbe. Standardmäßig `#616161` im Hellmodus, damit sie auf dem Hero-Hintergrund gut lesbar bleibt, und `--color-fg-muted` im Dunkelmodus.
---
* `--hero-image-radius`
* Eckenradius des Vordergrundbilds eines Heros, falls vorhanden.
---
* `--hero-image-shadow`
* Schlagschatten unter diesem Vordergrundbild.
{% /table %}

## Beispiel hero.css

Eine `config/styles/hero.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --hero-bg: #f8fafc;
  --hero-title-color: #1c1c1c;
  --hero-title-accent-color: #0f766e;
  --hero-desc-color: #6b7280;
  --hero-image-radius: 10px;
  --hero-image-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
}

.dark {
  --hero-bg: #0f172a;
  --hero-title-color: #ebebeb;
  --hero-title-accent-color: #2dd4bf;
  --hero-desc-color: #9ca3af;
}
```

## Nächster Schritt

- [Abschnitte gestalten](/de/customization/advanced/sections).
