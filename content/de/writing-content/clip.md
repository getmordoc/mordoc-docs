---
title: Clips
description: Fügen Sie kurze, selbst gehostete Demo-Clips mit einem Klick-zum-Abspielen-Umschalter hinzu.
---

Ein Clip ist ein kurzes, stummgeschaltetes, in Schleife laufendes Demo-Video. Mordoc empfiehlt diesen Weg, um eine UI-Interaktion zu zeigen, statt eines animierten GIFs.

Ein GIF spielt automatisch ab, ohne Möglichkeit, es zu pausieren, was sowohl ablenkend als auch ein Barrierefreiheitsproblem ist. Ein Clip wird pausiert mit seinem Vorschaubild dargestellt und spielt erst ab, sobald ein Leser darauf klickt, sodass er unter der Kontrolle des Lesers bleibt.

## Einen Clip hinzufügen

```markdown {% process=false %}
{% clip 
  src="/clips/animated-dinosaur.mp4" 
  title="Animated Dinosaur" 
  alt="Animated Dinosaur" 
/%}
```

**So sieht das aus**

{% clip 
  src="/clips/animated-dinosaur.mp4" 
  title="Animierter Dinosaurier" 
  alt="Animierter Dinosaurier"
/%}


Legen Sie die Videodatei in `public/` ab und referenzieren Sie dann ihren Pfad auf die gleiche Weise wie bei einem Bild. Siehe [Bilder und Dateien](/de/getting-started/images-and-files), falls Sie noch nie ein Asset hinzugefügt haben.

## Clip-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `src`
* Die Videodatei selbst
* Videopfad
* Erforderlich
---
* `thumbnail`
* Wird pausiert angezeigt, bevor der Leser auf Play klickt
* Bildpfad
* Optional
---
* `title`
* Eine Bildunterschrift, die unter dem Clip angezeigt wird
* Beliebiger Text
* Optional
---
* `alt`
* Zugängliches Label für die Play/Pause-Schaltfläche
* Beliebiger Text
* Optional
{% /table %}

## Clips kurz und stumm halten

Clips sind für kurze, dekorative Demo-Schleifen gedacht, nicht für eine erzählte Anleitung. Mordoc schaltet sie immer stumm.

Verwenden Sie für ein längeres, hörbares Video, etwa einen aufgezeichneten Vortrag oder eine erzählte Anleitung, stattdessen eine [Video-Einbettung](/de/writing-content/video-embed), die auf ein bereits auf YouTube, Vimeo oder Loom gehostetes Video verweist, anstatt eine Datei, die Sie selbst hosten.

## Nächster Schritt

- [Ein gehostetes Video einbetten](/de/writing-content/video-embed).
