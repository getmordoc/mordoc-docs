---
title: App Layout
description: Gestalten Sie die Boxen für Header, Seitennavigation und Inhaltsbereich, aus denen jede Mordoc-Seite besteht.
---

Jede Seite einer Mordoc-Website ist aus denselben drei Boxen aufgebaut. `config/styles/app.css` gestaltet die Platzierung, den Hintergrund und den Rand dieser Boxen, ohne deren Inhalt anzufassen.

```text
┌────────────────────────────────────────────────┐
│                  Header Area                   │
├────────────────┬───────────────────────────────┤
│                │                               │
│  Sidenav Area  │        Content Area           │
│                │                               │
│                │                               │
└────────────────┴───────────────────────────────┘
```

* **Header Area**: bleibt oben auf jeder Seite fixiert.
* **Sidenav Area**: die Seitennavigation, links vom Inhalt auf dem Desktop, außerhalb des sichtbaren Bereichs auf Mobilgeräten.
* **Content Area**: alles Übrige, der Artikel, sein Inhaltsverzeichnis und die Fußzeile.

Was innerhalb jeder Box steht, ist Aufgabe der jeweiligen Komponente. Diese Seite behandelt nur die Box selbst. Siehe [Header](/de/customization/advanced/header), [Seitennavigation](/de/customization/advanced/side-navigation) und [Inhalts-Layout](/de/customization/advanced/content-layout) für das, was innerhalb jeder Box gezeichnet wird.

## Die Override-Datei öffnen

```text
config/styles/app.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--header-area-bg`
* Hintergrund der Header-Area-Box. Standardmäßig hellgrau: `#fafafa`, im Dunkelmodus `#272727`.
---
* `--sidenav-area-bg`
* Hintergrund der Sidenav-Area-Box.
---
* `--sidenav-area-width`
* Breite der Sidenav-Area-Box auf dem Desktop. Standardmäßig `16rem`.
{% /table %}


## Beispiel app.css

Eine `config/styles/app.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --header-area-bg: #ffffff;
  --sidenav-area-bg: #ffffff;
  --sidenav-area-width: 18rem;
}

.dark {
  --header-area-bg: #0d0d0d;
  --sidenav-area-bg: #0d0d0d;
}
```

## Nächster Schritt

- [Den Header gestalten](/de/customization/advanced/header).
