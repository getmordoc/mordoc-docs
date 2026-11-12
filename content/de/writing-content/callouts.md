---
title: Callouts
description: Heben Sie Hinweise, Tipps, Warnungen und wichtige Meldungen auf Mordoc-Seiten hervor.
---

Callouts helfen dabei, wichtige Informationen vom Rest der Seite abzuheben.

Verwenden Sie sie, wenn ein Leser innehalten, etwas bemerken oder vorsichtig sein sollte, bevor er weiterliest. Verwenden Sie keinen Callout für jeden wichtigen Satz. Zu viele Callouts machen eine Seite schwerer zu überfliegen.

## Einen einfachen Callout hinzufügen

Ein Callout beginnt mit `{% callout %}` und endet mit `{% /callout %}`.

```markdown {% process=false %}
{% callout type="note" title="Gut zu wissen" %}
Die Gemeinschaft des Rings brach mit neun Gefährten von Bruchtal auf.
{% /callout %}
```

Der Text zwischen den öffnenden und schließenden Tags ist der Callout-Inhalt.

## Einen Typ wählen

Mordoc unterstützt vier Callout-Typen:

* `note` für nützlichen zusätzlichen Kontext
* `tip` für hilfreiche Vorschläge
* `warning` für Dinge, bei denen Leser vorsichtig sein sollten
* `danger` für ernste oder riskante Situationen

Der `type`-Wert ist optional. Wenn Sie ihn weglassen, verwendet Mordoc `note`.

Der `title`-Wert ist ebenfalls optional. Fügen Sie ihn hinzu, wenn er Lesern hilft, den Callout schnell zu verstehen.

## Note

Verwenden Sie `note` für hilfreiche Informationen, die den Haupttext unterstützen.

```markdown {% process=false %}
{% callout type="note" title="Gut zu wissen" %}
Das Auenland liegt westlich von Bree, jenseits des Flusses Brandywein.
{% /callout %}
```

**So sieht das aus**

{% callout type="note" title="Gut zu wissen" %}
Das Auenland liegt westlich von Bree, jenseits des Flusses Brandywein.
{% /callout %}

## Tip

Verwenden Sie `tip` für Ratschläge, die eine Aufgabe einfacher machen.

```markdown {% process=false %}
{% callout type="tip" title="Sprich, Freund, und tritt ein" %}
Sagen Sie an den Toren von Moria „Mellon".
{% /callout %}
```

**So sieht das aus**

{% callout type="tip" title="Sprich, Freund, und tritt ein" %}
Sagen Sie an den Toren von Moria „Mellon".
{% /callout %}

## Warning

Verwenden Sie `warning`, wenn Leser etwas verlangsamen oder überprüfen sollten, bevor sie fortfahren.

```markdown {% process=false %}
{% callout type="warning" title="Vorsicht vor dem Wasser" %}
Verweilen Sie nicht am See vor den Toren von Durin. Etwas regt sich unter seiner Oberfläche.
{% /callout %}
```

**So sieht das aus**

{% callout type="warning" title="Vorsicht vor dem Wasser" %}
Verweilen Sie nicht am See vor den Toren von Durin. Etwas regt sich unter seiner Oberfläche.
{% /callout %}

## Danger

Verwenden Sie `danger` nur für ernste Situationen.

```markdown {% process=false %}
{% callout type="danger" title="Den Ring niemals aufsetzen" %}
Setzen Sie niemals den Einen Ring auf. In dem Moment, in dem Sie ihn tragen, ziehen Sie das Auge Saurons auf sich.
{% /callout %}
```

**So sieht das aus**

{% callout type="danger" title="Den Ring niemals aufsetzen" %}
Setzen Sie niemals den Einen Ring auf. In dem Moment, in dem Sie ihn tragen, ziehen Sie das Auge Saurons auf sich.
{% /callout %}

## Callouts kurz halten

Ein guter Callout ist in der Regel ein kurzer Absatz oder eine kleine Liste. Wenn der Callout zu lang wird, muss er möglicherweise ein normaler Abschnitt werden.

## Callout-Attribute

{% table %}
* Attribut
* Beschreibung
* Werte
* Erforderlich
---
* `type`
* Der Callout-Stil
* `note`, `tip`, `warning`, `danger` (Standard `note`)
* Optional
---
* `title`
* Eine kurze Überschrift, die über dem Callout-Inhalt angezeigt wird
* Beliebiger Text
* Optional
---
{% /table %}

## Nächster Schritt

* [Tabellen erstellen](/de/writing-content/tables).
