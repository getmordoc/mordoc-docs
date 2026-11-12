---
title: Karten und Karten-Raster
description: Erstellen Sie visuelle Linkgruppen mit Karten und Karten-Rastern.
---

Karten sind nützlich, wenn Sie Leser zu einigen verwandten Seiten oder Optionen führen möchten.

Eine Karte ist ein kleiner Inhaltsblock. Ein Karten-Raster ordnet mehrere Karten zusammen an.

Verwenden Sie Karten, wenn ein Leser wählen muss, wohin er als nächstes gehen möchte. Eine Startseite könnte zum Beispiel zu den wichtigsten Abschnitten einer Website verlinken.

## Ein Karten-Raster hinzufügen

Beginnen Sie mit einem `cardGrid`:

```markdown {% process=false %}
{% cardGrid cols="3" %}
{% /cardGrid %}
```

Der `cols`-Wert steuert, wie viele Spalten das Raster auf breiten Bildschirmen anzeigen soll. Übliche Werte sind `2` und `3`. Mordoc passt das Layout auf kleineren Bildschirmen weiterhin an.

## Karten-Raster-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `cols`
* Bevorzugte Anzahl der Spalten auf breiten Bildschirmen
* `1`-`4` (Standard `3`)
* Optional
{% /table %}

## Karten innerhalb des Rasters hinzufügen

Jede Karte benötigt ein `title`-Attribut:

```markdown {% process=false %}
{% cardGrid cols="2" %}
{% card title="Installieren" path="/guides/install" %}
Installieren Sie das Produkt und prüfen Sie, ob es läuft.
{% /card %}
{% card title="Konfigurieren" path="/guides/configure" %}
Passen Sie die Einstellungen für Ihr Projekt an.
{% /card %}
{% /cardGrid %}
```

Das `title`-Feld ist erforderlich. Verwenden Sie `path`, wenn die Karte irgendwohin verlinken soll. Die anderen Karten-Felder sind optional.

## Eine Kartenart wählen

Mordoc unterstützt einige Kartenarten:

* Eine einfache Karte, nur mit Titel, Pfad und Textinhalt
* Eine Karte mit `tag`, für ein kurzes Abzeichen wie `Neu` oder `Hier starten`
* Eine Karte mit `icon`, für ein kleines Icon neben dem Titel
* Eine Karte mit `image`, für ein größeres Bild über dem Titel

## Einfache Karten

Verwenden Sie eine einfache Karte, wenn der Titel und ein kurzer Satz ausreichen, um dem Leser bei der Entscheidung zu helfen.

```markdown {% process=false %}
{% cardGrid cols="2" %}
{% card title="Bauen und Bereitstellen" path="/de/publishing/build-your-site" %}
Erzeugen Sie eine statische Website und stellen Sie sie in wenigen Minuten auf einer beliebigen Hosting-Plattform bereit.
{% /card %}
{% card title="Vorschau vor der Veröffentlichung" path="/de/publishing/preview-before-publishing" %}
Sehen Sie genau, wie Ihre Website aussieht, bevor sie live geht — keine Überraschungen.
{% /card %}
{% /cardGrid %}
```

**So sieht das aus**

{% cardGrid cols="2" %}
{% card title="Bauen und Bereitstellen" path="/de/publishing/build-your-site" %}
Erzeugen Sie eine statische Website und stellen Sie sie in wenigen Minuten auf einer beliebigen Hosting-Plattform bereit.
{% /card %}
{% card title="Vorschau vor der Veröffentlichung" path="/de/publishing/preview-before-publishing" %}
Sehen Sie genau, wie Ihre Website aussieht, bevor sie live geht — keine Überraschungen.
{% /card %}
{% /cardGrid %}

## Einfache Karten mit Abzeichen

Verwenden Sie `tag` für kurze Beschriftungen wie `Neu`, `Hier starten` oder `Empfohlen`. Verwenden Sie Tags sparsam. Wenn jede Karte ein Tag hat, verlieren die Tags ihre Wirkung.

```markdown {% process=false %}
{% cardGrid cols="2" %}
{% card title="Schnellstart" path="/de/getting-started/create-project" tag="Hier starten" %}
Beginnen Sie mit dem schnellsten Weg durch die Dokumentation.
{% /card %}
{% card title="Callouts" path="/de/writing-content/callouts" tag="Neu" %}
Heben Sie Hinweise, Tipps, Warnungen und wichtige Meldungen auf Mordoc-Seiten hervor.
{% /card %}
{% /cardGrid %}
```

**So sieht das aus**

{% cardGrid cols="2" %}
{% card title="Schnellstart" path="/de/getting-started/create-project" tag="Hier starten" %}
Beginnen Sie mit dem schnellsten Weg durch die Dokumentation.
{% /card %}
{% card title="Callouts" path="/de/writing-content/callouts" tag="Neu" %}
Heben Sie Hinweise, Tipps, Warnungen und wichtige Meldungen auf Mordoc-Seiten hervor.
{% /card %}
{% /cardGrid %}

## Karten mit Icon

Fügen Sie `icon` hinzu, um ein kleines Icon neben dem Titel anzuzeigen. `icon` wird in einer kleinen quadratischen Box ohne Zuschneiden dargestellt, daher passt ein quadratisches Icon, idealerweise ein SVG, am besten.

```markdown {% process=false %}
{% cardGrid cols="3" %}
{% card title="Erste Schritte" path="/de/getting-started/create-project" icon="/icons/card-icons/getting-started.svg" %}
Erstellen Sie Ihr erstes Projekt, führen Sie es lokal aus und lernen Sie von Grund auf, wie Mordoc funktioniert.
{% /card %}
{% card title="Inhalte schreiben" path="/de/writing-content/markdown-basics" icon="/icons/card-icons/writing.svg" %}
Markdown-Grundlagen, Callouts, Tabellen, Karten, Landing-Pages und alles dazwischen.
{% /card %}
{% card title="Konfiguration" path="/de/configuration/site-configuration" icon="/icons/card-icons/configuration.svg" %}
Passen Sie Ihre Website mit Navigation, Branding, Themes, Variablen und Mehrsprachigkeit an.
{% /card %}
{% /cardGrid %}
```

**So sieht das aus**

{% cardGrid cols="3" %}
{% card title="Erste Schritte" path="/de/getting-started/create-project" icon="/icons/card-icons/getting-started.svg" %}
Erstellen Sie Ihr erstes Projekt, führen Sie es lokal aus und lernen Sie von Grund auf, wie Mordoc funktioniert.
{% /card %}
{% card title="Inhalte schreiben" path="/de/writing-content/markdown-basics" icon="/icons/card-icons/writing.svg" %}
Markdown-Grundlagen, Callouts, Tabellen, Karten, Landing-Pages und alles dazwischen.
{% /card %}
{% card title="Konfiguration" path="/de/configuration/site-configuration" icon="/icons/card-icons/configuration.svg" %}
Passen Sie Ihre Website mit Navigation, Branding, Themes, Variablen und Mehrsprachigkeit an.
{% /card %}
{% /cardGrid %}

## Karten mit Bild

Fügen Sie `image` hinzu, um ein größeres Bild über dem Titel anzuzeigen.

```markdown {% process=false %}
{% cardGrid cols="3" %}
{% card title="Český Krumlov" image="/images/content-images/cesky-krumlov.jpg" %}
Eine märchenhafte Stadt in Südböhmen, eingefasst von einer Flussschleife der Moldau.
{% /card %}
{% card title="Island" image="/images/content-images/iceland.jpg" %}
Wasserfälle, Gletscher und schwarze Sandstrände hinter jeder Kurve.
{% /card %}
{% card title="Reine" image="/images/content-images/reine.jpg" %}
Ein Fischerdorf, eingebettet unter den Gipfeln der Lofoten.
{% /card %}
{% /cardGrid %}
```

**So sieht das aus**

{% cardGrid cols="3" %}
{% card title="Český Krumlov" image="/images/content-images/cesky-krumlov.jpg" %}
Eine märchenhafte Stadt in Südböhmen, eingefasst von einer Flussschleife der Moldau.
{% /card %}
{% card title="Island" image="/images/content-images/iceland.jpg" %}
Wasserfälle, Gletscher und schwarze Sandstrände hinter jeder Kurve.
{% /card %}
{% card title="Reine" image="/images/content-images/reine.jpg" %}
Ein Fischerdorf, eingebettet unter den Gipfeln der Lofoten.
{% /card %}
{% /cardGrid %}

{% callout type="tip" title="Das erwartete Seitenverhältnis beachten" %}
`image` wird in einer festen 16:9-Box dargestellt und zugeschnitten, um sie auszufüllen. Ein Quellbild im Format 16:9 (zum Beispiel 800x450 oder 1200x675) verhindert daher, dass Ränder verloren gehen.
{% /callout %}

## Kartentext kurz halten

Kartentext sollte Lesern bei der Wahl helfen. Ein kurzer Satz ist in der Regel ausreichend.

## Karten-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `title`
* Die Kartenüberschrift
* Beliebiger Text
* Erforderlich
---
* `path`
* Die Seite oder URL, zu der die gesamte Karte verlinkt
* Ein Pfad oder eine URL
* Optional
---
* `icon`
* Ein kleines Icon, das neben dem Titel angezeigt wird. Wird ignoriert, wenn `image` gesetzt ist
* Icon-Pfad
* Optional
---
* `image`
* Ein größeres Bild, das über dem Titel angezeigt wird
* Bildpfad
* Optional
---
* `tag`
* Ein kurzes Abzeichen, das über dem Titel angezeigt wird, z. B. `Neu` oder `Hier starten`
* Beliebiger Text
* Optional
{% /table %}

## Nächster Schritt

* [Spalten anordnen](/de/writing-content/columns).
