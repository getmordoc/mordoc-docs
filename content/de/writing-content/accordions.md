---
title: Accordions
description: Fügen Sie einklappbare Abschnitte für Inhalte hinzu, die Leser nicht sofort sehen müssen.
---

Ein Accordion ist ein einklappbarer Abschnitt: ein klickbarer Titel und ein Body, der verborgen bleibt, bis der Leser ihn öffnet.

Verwenden Sie Accordions für Inhalte, die nützlich, aber nicht für jeden Leser wesentlich sind. Zum Beispiel, wenn Sie häufig gestellte Fragen (FAQ), optionale Details oder eine lange Liste von Sonderfällen schreiben möchten, die die Seite sonst überladen würden.

## Ein Accordion hinzufügen

```markdown {% process=false %}
{% accordion title="Who is the Ring-bearer?" %}
Frodo Baggins carries the One Ring from the Shire to Mount Doom, though Sam never leaves his side.
{% /accordion %}
```

**So sieht das aus**

{% accordion title="Wer ist der Ringträger?" %}
Frodo trägt den Einen Ring vom Auenland bis zum Schicksalsberg, wobei Sam nie von seiner Seite weicht.
{% /accordion %}

Ein Accordion akzeptiert den gleichen Inhalt wie ein normaler Seiten-Body, also Überschriften, Absätze, Listen, Code-Blöcke, Bilder, Callouts, sogar ein verschachteltes `clip`, ein weiteres Accordion usw.

## Standardmäßig geöffnet

Fügen Sie `defaultOpen=true` hinzu, wenn der Inhalt beim Laden der Seite bereits sichtbar sein soll, statt einen Klick zu erfordern:

```markdown {% process=false %}
{% accordion title="The Fellowship" defaultOpen=true %}
Frodo, Sam, Merry, Pippin, Gandalf, Aragorn, Legolas, Gimli, and Boromir.
{% /accordion %}
```

**So sieht das aus**

{% accordion title="Die Gemeinschaft des Rings" defaultOpen=true %}
Frodo, Sam, Merry, Pippin, Gandalf, Aragorn, Legolas, Gimli und Boromir.
{% /accordion %}

## Mehrere Accordions gruppieren

Fassen Sie mehrere Accordions in `accordions` zusammen, um sie zu einem visuell verbundenen Block zu gruppieren:

```markdown {% process=false %}
{% accordions %}
{% accordion title="What is the One Ring?" %}
Sauron forged it in the fires of Mount Doom, binding it to his own power so that whoever holds it can command the other Rings of Power.
{% /accordion %}
{% accordion title="Why can't the Ring simply be destroyed with a sword?" %}
It can only be unmade the same way it was made: cast back into the fires where it was forged.
{% /accordion %}
{% /accordions %}
```

**So sieht das aus**

{% accordions %}
{% accordion title="Was ist der Eine Ring?" %}
Sauron schmiedete ihn in den Feuern des Schicksalsbergs und band ihn an seine eigene Macht, sodass jeder, der ihn hält, die anderen Ringe der Macht befehligen kann.
{% /accordion %}
{% accordion title="Warum kann der Ring nicht einfach mit einem Schwert zerstört werden?" %}
Er kann nur auf dieselbe Weise vernichtet werden, wie er geschaffen wurde: zurückgeworfen in die Feuer, in denen er geschmiedet wurde.
{% /accordion %}
{% /accordions %}

Eine Gruppe ist standardmäßig exklusiv: Das Öffnen eines Elements schließt jedes andere offene Element in der Gruppe, genau wie bei einer typischen FAQ-Liste.

## Accordion-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `title`
* Der klickbare Header-Text
* Beliebiger Text
* Erforderlich
---
* `defaultOpen`
* Ob der Abschnitt geöffnet startet
* `true`/`false` (Standard `false`)
* Optional
{% /table %}

## Nächster Schritt

- [Landing-Pages erstellen](/de/writing-content/landing-pages).
