---
title: Video-Einbettungen
description: Betten Sie ein Video ein, das bereits auf YouTube, Vimeo oder Loom gehostet wird.
---

Verwenden Sie eine Video-Einbettung, wenn das Video bereits an anderer Stelle gehostet wird. Für eine kurze, stumme Demo-Schleife, die Sie selbst hosten, verwenden Sie stattdessen einen [Clip](/de/writing-content/clip).

Mordoc unterstützt einen nativen Video-Einbettungsplayer für YouTube, Vimeo und Loom.

## Eine Video-Einbettung hinzufügen

```markdown {% process=false %}
{% videoEmbed 
  src="https://www.youtube.com/watch?v=AF8d72mA41M" 
  title="Why it was almost impossible to make the blue LED" 
/%}
```

**So sieht das aus**

{% videoEmbed 
  src="https://www.youtube.com/watch?v=AF8d72mA41M" 
  title="Warum es fast unmöglich war, die blaue LED zu entwickeln" 
/%}


## Nicht erkannte Anbieter

Wenn `src` keiner der oben genannten Anbieter ist, versucht Mordoc nicht, eine defekte Einbettung darzustellen. Stattdessen zeigt es eine Link-Karte an, unter Verwendung von `thumbnail`, falls Sie eines gesetzt haben:

```markdown {% process=false %}
{% videoEmbed src="https://example.com/watch/123" thumbnail="/images/demo-thumb.jpg" title="Demo video" /%}
```

`thumbnail` wird bei einem erkannten Anbieter ignoriert: YouTube, Vimeo und Loom zeigen bereits in dem Moment, in dem die Einbettung lädt, ihr eigenes echtes Vorschaubild.

## Attribute der Video-Einbettung

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `src`
* Die öffentliche Seiten-URL des Videos
* URL
* Erforderlich
---
* `title`
* Eine Bildunterschrift, die unter der Einbettung angezeigt wird
* Beliebiger Text
* Optional
---
* `alt`
* Überschreibt das zugängliche Label. Andernfalls wird der Anbietername oder `title` verwendet
* Beliebiger Text
* Optional
---
* `thumbnail`
* Wird nur bei der Fallback-Link-Karte verwendet, für ein `src` mit nicht erkanntem Anbieter
* Bildpfad
* Optional
---
* `aspectRatio`
* Überschreibt die standardmäßige 16:9-Box
* CSS-Verhältnis, z. B. `"4 / 3"`, `"9 / 16"`
* Optional
{% /table %}

## Nächster Schritt

- [Nachrichten mit Callouts hervorheben](/de/writing-content/callouts).
