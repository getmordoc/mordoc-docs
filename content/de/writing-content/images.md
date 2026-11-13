---
title: Bilder
description: Fügen Sie Bilder und Icons hinzu, einschließlich solcher mit einer variablenbasierten Quelle.
---

Legen Sie Inhaltsbilder in `public/` ab und referenzieren Sie sie dann mit einem Pfad, der mit `/` beginnt.

## Grundlegende Bilder

```markdown
![Grafik](/images/content-images/artwork.png)
```

Der Text in eckigen Klammern ist der `alt`-Text des Bildes. Halten Sie ihn beschreibend, da Bildschirmlesegeräte ihn vorlesen und er angezeigt wird, falls das Bild nicht geladen werden kann.

**So sieht das aus**

![Grafik](/images/content-images/artwork.png)

Die Seite [Bilder und Dateien](/de/getting-started/images-and-files) führt Sie Schritt für Schritt durch das Hinzufügen eines Bildes.

## Der image-Tag

Sie können ein Bild auch als Tag schreiben. Er stellt dasselbe einfache Bild dar, und sein `src` kann eine [Variable](/de/configuration/variables) sein.

```markdown {% process=false %}
{% image src="/images/content-images/artwork.png" alt="Grafik" title="Wird beim Darüberfahren angezeigt" /%}
```

**So sieht das aus**

{% image src="/images/content-images/artwork.png" alt="Grafik" title="Wird beim Darüberfahren angezeigt" /%}

{% table %}
* Attribut
* Was es bewirkt
---
* `src`
* Der Pfad zum Bild, beginnend mit `/`. Erforderlich.
---
* `alt`
* Der Text, den Bildschirmlesegeräte vorlesen und der angezeigt wird, falls das Bild nicht geladen werden kann.
---
* `title`
* Der Text, der angezeigt wird, wenn Leser mit der Maus über das Bild fahren.
{% /table %}

Für eine Bildunterschrift unter dem Bild und Vergrößern per Klick verwenden Sie ein [erweitertes Bild](/de/writing-content/advanced-images).

## Icons

Icons funktionieren genauso wie jedes andere Bild: Legen Sie die Datei in `public/` ab und referenzieren Sie dann ihren Pfad.

```text
public/icons/shield.svg
```

Kleine SVGs sind die häufigste Wahl, da sie in jeder Größe scharf bleiben.

Sie fügen ein Icon nicht direkt in den Seitentext ein. Stattdessen nehmen bestimmte Komponenten eine Icon-Datei über ein Attribut entgegen, wie zum Beispiel `icon` bei einer [Karte](/de/writing-content/cards-and-card-grids) oder das Icon eines Akteurs in einem [Sequenzdiagramm](/de/creating-diagrams/sequence-diagrams).

## Bilder mit Variablen

Manchmal sollte die Quelle eines Bildes aus einem wiederverwendbaren Wert stammen, anstatt direkt geschrieben zu werden, zum Beispiel eine Logo-URL, die sich später ändern könnte. Siehe [Variablen](/de/configuration/variables), um zu erfahren, wie Sie eine Variable definieren und in einem Bild verwenden.

## Nächster Schritt

- [Erweiterte Bilder hinzufügen](/de/writing-content/advanced-images).
