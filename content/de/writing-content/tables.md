---
title: Tabellen
description: Erstellen Sie strukturierte Tabellen mit der Mordoc-Tabellensyntax.
---

Tabellen sind nützlich, wenn Leser verwandte Informationen vergleichen müssen.

Mordoc verwendet eine Tabellensyntax, die einfachen Text und reichhaltigere Inhalte aufnehmen kann. Dies unterscheidet sich von der grundlegenden Markdown-Tabellensyntax.

## Eine einfache Tabelle erstellen

Eine Mordoc-Tabelle beginnt mit `{% table %}` und endet mit `{% /table %}`.

Verwenden Sie `*` für jede Zelle. Verwenden Sie `---`, um Kopfzeile und Zeilen zu trennen.

```markdown {% process=false %}
{% table %}
* Kopfzeile 1
* Kopfzeile 2
* Kopfzeile 3
---
* Zeile 1, Zelle 1
* Zeile 1, Zelle 2
* Zeile 1, Zelle 3
---
* Zeile 2, Zelle 1
* Zeile 2, Zelle 2
* Zeile 2, Zelle 3
---
{% /table %}
```

**So sieht das aus**

{% table %}
* Kopfzeile 1
* Kopfzeile 2
* Kopfzeile 3
---
* Zeile 1, Zelle 1
* Zeile 1, Zelle 2
* Zeile 1, Zelle 3
---
* Zeile 2, Zelle 1
* Zeile 2, Zelle 2
* Zeile 2, Zelle 3
---
{% /table %}

Jede Zeile sollte dieselbe Anzahl von Zellen wie die Kopfzeile haben.

## Weitere Spalten hinzufügen

Sie können weitere Spalten hinzufügen, indem Sie mehr Kopfzeilenzellen und entsprechende Zeilenzellen hinzufügen:

```markdown {% process=false %}
{% table %}
* Kopfzeile 1
* Kopfzeile 2
* Kopfzeile 3
* Kopfzeile 4
* Kopfzeile 5
* Kopfzeile 6
---
* Zeile 1, Zelle 1
* Zeile 1, Zelle 2
* Zeile 1, Zelle 3
* Zeile 1, Zelle 4
* Zeile 1, Zelle 5
* Zeile 1, Zelle 6
---
* Zeile 2, Zelle 1
* Zeile 2, Zelle 2
* Zeile 2, Zelle 3
* Zeile 2, Zelle 4
* Zeile 2, Zelle 5
* Zeile 2, Zelle 6
---
{% /table %}
```

Breite Tabellen können schwerer zu lesen sein, besonders auf kleinen Bildschirmen. Verwenden Sie nur so viele Spalten, wie der Leser benötigt.

## Reichhaltige Inhalte hinzufügen

Tabellenzellen können mehr als nur einfachen Text enthalten.

Eine Zelle kann zum Beispiel formatierten Text, Listen, Blockzitate, Code-Blöcke, Callouts und Bilder enthalten.

````markdown {% process=false %}
{% table %}
* Inhaltstyp
* Beispiel
---
* Typografie
* **Fett**, *kursiv*, `Inline-Code` und ein [Link](/getting-started/create-project).
---
* Ungeordnete Liste
*
  - Alpha
  - Beta
    - Gamma verschachtelt
---
* Geordnete Liste
*
  1. Schritt eins
  2. Schritt zwei
     1. Teilschritt a
     2. Teilschritt b
---
* Blockzitat
*
  > Zitierte Zeile eins.
  >
  > Zitierte Zeile zwei.
---
* Code-Block
*
  ```ts
  export function isReady(pageCount: number): boolean {
    return pageCount > 0;
  }
  ```
---
* Callout note
*
  {% callout type="note" title="In der Tabelle" %}
  Callout-Inhalt mit einer Liste:

  - In Callouts erlaubt
  - Zweites Element
  {% /callout %}
---
* Callout warning
*
  {% callout type="warning" title="Warnung" %}
  ```json
  { "pages": 3 }
  ```
  {% /callout %}
---
* Callout danger
*
  {% callout type="danger" title="Gefahr" %}
  Kritische Einschränkung in einer Tabellenzelle.
  {% /callout %}
---
* Callout tip
*
  {% callout type="tip" %}
  Tipp ohne Titel.
  {% /callout %}
---
* Bild
*
  ![Mordoc Hero-Bild](/images/hero-images/mordor.png)
---
* Gemischte Inline-Links
* Extern: [Beispiel](https://example.com), intern: [Projekt erstellen](/getting-started/create-project)
{% /table %}
````

**So sieht das aus**

{% table %}
* Inhaltstyp
* Beispiel
---
* Typografie
* **Fett**, *kursiv*, `Inline-Code` und ein [Link](/getting-started/create-project).
---
* Ungeordnete Liste
*
  - Alpha
  - Beta
    - Gamma verschachtelt
---
* Geordnete Liste
*
  1. Schritt eins
  2. Schritt zwei
     1. Teilschritt a
     2. Teilschritt b
---
* Blockzitat
*
  > Zitierte Zeile eins.
  >
  > Zitierte Zeile zwei.
---
* Code-Block
*
  ```ts
  export function isReady(pageCount: number): boolean {
    return pageCount > 0;
  }
  ```
---
* Callout note
*
  {% callout type="note" title="In der Tabelle" %}
  Callout-Inhalt mit einer Liste:

  - In Callouts erlaubt
  - Zweites Element
  {% /callout %}
---
* Callout warning
*
  {% callout type="warning" title="Warnung" %}
  ```json
  { "pages": 3 }
  ```
  {% /callout %}
---
* Callout danger
*
  {% callout type="danger" title="Gefahr" %}
  Kritische Einschränkung in einer Tabellenzelle.
  {% /callout %}
---
* Callout tip
*
  {% callout type="tip" %}
  Tipp ohne Titel.
  {% /callout %}
---
* Bild
*
  ![Mordoc Hero-Bild](/images/content-images/artwork.png)
---
* Gemischte Inline-Links
* Extern: [Beispiel](https://example.com), intern: [Projekt erstellen](/getting-started/create-project)
{% /table %}

## Nächster Schritt

- [Karten und Karten-Raster verwenden](/de/writing-content/cards-and-card-grids).
