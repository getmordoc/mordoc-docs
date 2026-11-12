---
title: Spalten
description: Ordnen Sie Inhalte mit der Columns-Komponente nebeneinander an.
---

Spalten ordnen Inhalte nebeneinander mit gleicher Breite an und stapeln sich auf schmalen Bildschirmen automatisch zu einer einzigen Spalte.

Verwenden Sie sie, um zwei kurze Inhalte zu vergleichen, oder um einen Demo-Clip neben die Schritte zu stellen, die ihn erzeugen.

## Spalten hinzufügen

Fassen Sie zwei oder mehr `column`-Tags in `columns` zusammen:

```markdown {% process=false %}
{% columns %}
{% column %}
{% image src="/images/content-images/cesky-krumlov.jpg" alt="Cesky Krumlov" /%}
{% /column %}
{% column %}
### Cesky Krumlov

A small town in South Bohemia, built around a sharp bend in the Vltava river. Its old town is packed onto the riverbank below a castle that has stood since the 13th century, and the whole center is a UNESCO World Heritage Site.

Visitors come for the narrow cobbled streets, the castle's painted tower, and the view from the bridge over the river. 
{% /column %}
{% /columns %}
```

**So sieht das aus**

{% columns %}
{% column %}
{% image src="/images/content-images/cesky-krumlov.jpg" alt="Český Krumlov" /%}
{% /column %}
{% column %}
### Český Krumlov

Eine kleine Stadt in Südböhmen, erbaut um eine scharfe Flussschleife der Moldau. Die Altstadt drängt sich am Flussufer unterhalb einer Burg, die seit dem 13. Jahrhundert steht, und das gesamte Zentrum ist UNESCO-Weltkulturerbe.

Besucher kommen wegen der engen Kopfsteinpflasterstraßen, des bemalten Burgturms und der Aussicht von der Brücke über den Fluss.
{% /column %}
{% /columns %}

{%callout type="note" %}
Eine Spalte akzeptiert den gleichen Inhalt wie ein normaler Seiten-Body: Überschriften, Absätze, Listen, Code-Blöcke, Bilder, Callouts, sogar ein verschachteltes `clip` oder `accordion`.
{% /callout %}

Die Anzahl der Spalten richtet sich danach, wie viele `column`-Tags Sie verschachteln.

## Einen Trenner hinzufügen

Setzen Sie `divider=true` auf `columns`, um eine vertikale Trennlinie zwischen den Spalten zu ziehen:

```markdown {% process=false %}
{% columns divider=true %}
{% column %}
{% image src="/images/content-images/iceland.jpg" alt="Iceland" /%}
{% /column %}
{% column %}
### Iceland

A Nordic island nation shaped by volcanoes, glaciers, and the rift where the North American and Eurasian plates pull apart. Waterfalls, hot springs, and black sand beaches sit within a short drive of one another along the Ring Road.

Visitors come for the Northern Lights in winter, the midnight sun in summer, and the glacial lagoons in between.
{% /column %}
{% /columns %}
```

**So sieht das aus**

{% columns divider=true %}
{% column %}
{% image src="/images/content-images/iceland.jpg" alt="Island" /%}
{% /column %}
{% column %}
### Island

Ein nordischer Inselstaat, geformt von Vulkanen, Gletschern und dem Grabenbruch, an dem sich die nordamerikanische und die eurasische Platte auseinanderziehen. Wasserfälle, heiße Quellen und schwarze Sandstrände liegen entlang der Ringstraße nur eine kurze Fahrt voneinander entfernt.

Besucher kommen wegen der Nordlichter im Winter, der Mitternachtssonne im Sommer und der Gletscherlagunen dazwischen.
{% /column %}
{% /columns %}

## Spalten-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `divider`
* Zieht eine vertikale Trennlinie zwischen den Spalten
* `true`/`false` (Standard `false`)
* Optional
{% /table %}

`column` selbst hat keine Attribute.

## Spalten kurz halten

Spalten eignen sich am besten für Inhalte, die wirklich nebeneinander stehen sollen. Zum Beispiel: ein kurzer Vergleich, oder ein Clip zusammen mit den Schritten drumherum. Für alles Längere sind einfach gestapelte Abschnitte in der Regel leichter zu lesen.

## Nächster Schritt

- [Inhalte mit Accordions gruppieren](/de/writing-content/accordions).
