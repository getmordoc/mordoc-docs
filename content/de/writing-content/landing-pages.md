---
title: Landing-Pages
description: Erstellen Sie vollbreite Seiten für Startseiten und Übersichtsseiten.
---

Die meisten Mordoc-Seiten verwenden das normale Dokumentations-Layout: Seitenleiste links, Seiteninhalt in der Mitte und ein Inhaltsverzeichnis rechts.

Manchmal benötigen Sie eine andere Art von Seite. Eine Startseite oder Produktübersicht funktioniert oft besser als Landing-Page.

## Was eine Landing-Page verändert

Eine Landing-Page ist vollbreit.

Sie zeigt nicht:

* Die Seitennavigation
* Das rechte Inhaltsverzeichnis
* Den normalen Artikel-Header

Das macht sie nützlich für Seiten, die die Website vorstellen, Karten zeigen oder Leser in die Hauptdokumentation führen.

## Eine Seite in eine Landing-Page umwandeln

Fügen Sie `layout: landing` zum Seiten-Frontmatter hinzu:

```markdown
---
title: Startseite
description: Willkommen bei meiner Dokumentation.
layout: landing
---
```

Verwenden Sie Landing-Pages sparsam. Die meisten Dokumentationsseiten sollten das normale Layout verwenden.

## Einen Hero hinzufügen

Ein Hero ist ein großer Eröffnungsbereich, der in der Regel oben auf einer Landing-Page verwendet wird.

Sie können Ihrer Landing-Page mit dem `{% hero %}`-Tag einen Hero-Bereich hinzufügen.

```markdown {% process=false %}
{% hero
  title="Meine Produkt-Dokumentation"
  titleAccent="leicht gemacht"
  description="Finden Sie Anleitungen, Referenzmaterial und praktische Beispiele."
  background="/images/hero-bg.png"
%}
{% button path="/getting-started/create-project" %}
Jetzt starten
{% /button %}
{% /hero %}
```

## Hero-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `title`
* Der Haupttitel-Text
* Beliebiger Text
* Erforderlich
---
* `titleAccent`
* Hervorgehobener Text, der in einer neuen Zeile unter dem Titel angezeigt wird
* Beliebiger Text
* Optional
---
* `description`
* Unterstützender Text, der unter dem Titel angezeigt wird
* Beliebiger Text
* Optional
---
* `image`
* Ein unterstützendes Bild, wie zum Beispiel ein Produkt-Screenshot, das unter den Schaltflächen angezeigt wird
* Bildpfad
* Optional
---
* `background`
* Ein Hintergrundbild hinter dem gesamten Hero
* Bildpfad
* Optional
{% /table %}

Verwenden Sie `background` für ein randloses Hintergrundbild hinter dem gesamten Hero. Verwenden Sie `image` für ein separates unterstützendes Bild, wie zum Beispiel einen Produkt-Screenshot, das unter den Schaltflächen angezeigt wird.

{% callout type="note" title="Farben sind keine Attribute" %}
Es gibt kein `titleColor`-, `titleAccentColor`- oder `descriptionColor`-Attribut, und `background` akzeptiert niemals eine reine Farbe, sondern nur einen Bildpfad. Die Farben eines Heros sind eine Design-Entscheidung, keine Inhaltsfrage, daher werden sie einmalig in CSS festgelegt. Siehe [Hero](/de/customization/advanced/hero) unter Erweiterte Anpassung.
{% /callout %}

## Größe eines Hintergrundbilds

Der Hero hat keine feste Höhe. Er wächst oder schrumpft mit dem Titel, `titleAccent`, der Beschreibung und den Schaltflächen, die Sie einfügen, sowie mit der Breite des Viewports. Ein Hintergrundbild wird so skaliert, dass es diesen Bereich abdeckt, und daher zugeschnitten, um die jeweilige Höhe des Heros vollständig auszufüllen.

Wählen Sie ein breites, kurzes Seitenverhältnis und halten Sie den wichtigen Bildbereich zentriert. Inhalte nahe dem oberen und unteren Rand werden zuerst zugeschnitten, wenn der Hero höher wird.

{% callout type="tip" title="Zuschneiden mit einem abstrakten Bild umgehen" %}
Ein Bild ohne festen Fokuspunkt, wie eine Textur, ein Farbverlauf oder ein Muster, wirkt unabhängig davon, wie sich der Hero in der Größe ändert. Zuschneiden verändert sein Aussehen kaum.
{% /callout %}

## Abschnitte hinzufügen

Ein Abschnitt gruppiert Inhalte auf einer Landing-Page, mit einem optionalen Titel und Hintergrund.

Sie können Ihrer Landing-Page mit dem `{% section %}`-Tag einen Abschnitt hinzufügen.

```markdown {% process=false %}
{% section title="Wählen Sie, wo Sie beginnen möchten" background="/images/section-bg.png" %}
Dieser Abschnitt stellt die Hauptwege durch die Dokumentation vor.
{% /section %}
```

## Abschnitts-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `title`
* Eine Überschrift, die über dem Abschnittsinhalt angezeigt wird
* Beliebiger Text
* Optional
---
* `background`
* Ein Hintergrundbild hinter dem Abschnitt
* Bildpfad
* Optional
{% /table %}

Wenn ein Abschnitt ein `background`-Bild hat, wechseln sein Titel und Text automatisch zu Weiß für bessere Lesbarkeit.

{% callout type="note" title="Farben sind keine Attribute" %}
`background` akzeptiert niemals eine reine Farbe, sondern nur einen Bildpfad. Die einfarbige Hintergrundfarbe eines Abschnitts ist eine Design-Entscheidung, keine Inhaltsfrage, daher wird sie einmalig in CSS festgelegt. Siehe [Abschnitte](/de/customization/advanced/sections) unter Erweiterte Anpassung.
{% /callout %}

## Karten zu einer Landing-Page hinzufügen

Landing-Pages verwenden häufig Karten innerhalb eines Abschnitts, um Leser dorthin zu führen, wo sie als Nächstes hinsollen:

```markdown {% process=false %}
{% section title="Die Dokumentation erkunden" %}
{% cardGrid cols="3" %}
{% card title="Erste Schritte" path="/getting-started/create-project" tag="Hier starten" %}
Erstellen und starten Sie Ihr erstes Projekt.
{% /card %}
{% /cardGrid %}
{% /section %}
```

Die vollständige Karten- und Karten-Raster-Syntax finden Sie unter [Karten und Karten-Raster](/de/writing-content/cards-and-card-grids).

## Schaltflächen hinzufügen

Eine Schaltfläche ist eine gestaltete Handlungsaufforderung, die normalerweise zu einer anderen Seite verlinkt.

Sie können mit dem `{% button %}`-Tag eine Schaltfläche hinzufügen.

```markdown {% process=false %}
{% button path="/getting-started/create-project" %}
Ein Projekt erstellen
{% /button %}
```

Verwenden Sie `variant="secondary"` für eine dezentere Schaltfläche:

```markdown {% process=false %}
{% button path="/writing-content/markdown-basics" variant="secondary" %}
Markdown lernen
{% /button %}
```

## Schaltflächen-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `path`
* Die Seite oder URL, zu der die Schaltfläche verlinkt
* Ein Pfad oder eine URL
* Erforderlich
---
* `variant`
* Steuert den visuellen Stil der Schaltfläche
* `primary`, `secondary` (Standard `primary`)
* Optional
{% /table %}

## Wann eine Landing-Page verwenden

Verwenden Sie eine Landing-Page für:

* Die Startseite
* Eine Produktübersicht
* Eine Übersicht eines Hauptabschnitts

## Nächster Schritt

* [Diagramme erstellen](/de/creating-diagrams/overview).