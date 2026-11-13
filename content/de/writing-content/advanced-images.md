---
title: Erweiterte Bilder
description: Fügen Sie ein Bild mit Bildunterschrift hinzu, das Leser vergrößert öffnen können.
---

Ein erweitertes Bild zeigt eine Bildunterschrift unter dem Bild. Leser können das Bild anklicken oder auswählen und Enter drücken, um es vergrößert zu öffnen. Verwenden Sie es für Screenshots und Diagramme, die Leser genauer ansehen möchten. Für ein einfaches Bild siehe [Bilder](/de/writing-content/images).

## Ein erweitertes Bild hinzufügen

```markdown {% process=false %}
{% advancedImage src="/images/content-images/artwork.png" alt="Grafik" caption="Die Grafik, per Klick vergrößert." /%}
```

**So sieht das aus**

{% advancedImage src="/images/content-images/artwork.png" alt="Grafik" caption="Die Grafik, per Klick vergrößert." /%}

Ein erweitertes Bild steht in einer eigenen Zeile. Es kann nicht innerhalb eines Satzes oder eines Links stehen.

## Attribute

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
* `caption`
* Der Text unter dem Bild und unter der vergrößerten Ansicht.
{% /table %}

Um das vergrößerte Bild zu schließen, klicken Sie irgendwo hin, verwenden Sie den Schließen-Button oder drücken Sie Escape.

## Nächster Schritt

- [Clips hinzufügen](/de/writing-content/clip).
