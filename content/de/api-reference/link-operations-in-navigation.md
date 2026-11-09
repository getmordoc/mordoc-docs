---
title: Operationen in der Navigation verlinken
description: Fügen Sie erzeugte API-Seiten zu Ihrer Seitenleiste hinzu und mischen Sie sie mit gewöhnlichen Leitfadenseiten.
---

Erzeugte API-Seiten erscheinen nicht von selbst in der Seitenleiste. Sie fügen sie in der Navigationsdatei hinzu, genauso wie jede andere Seite.

## Eine Operation verlinken

Verwenden Sie `operation:` mit der `operationId` der Spezifikation anstelle von `path:`:

```yaml
- label: Rings API
  expanded: true
  children:
    - operation: forgeRing
    - operation: getRing
```

Mordoc findet die Seite und ergänzt den Link für Sie. Wenn Sie die `operationId` umbenennen, meldet Ihnen der Build das, anstatt einen defekten Link zu hinterlassen.

## Ein Label wählen

Das `label` ist optional. Ohne Label verwendet die Seitenleiste die `summary` der Operation aus der Spezifikation:

```yaml
- operation: forgeRing
```

Um ein kürzeres Label zu verwenden, fügen Sie eines hinzu:

```yaml
- label: Forge
  operation: forgeRing
```

Kurze Labels funktionieren gut unter einem klaren Gruppennamen, zum Beispiel `Forge` und `Retrieve` unter `Rings API`.

## Eine Gruppenseite hinzufügen

Eine Gruppe kann wie jede andere Gruppe auf eine eigene Seite verlinken. Kombinieren Sie `path` mit `children`:

```yaml
- label: Rings API
  path: /api/rings
  children:
    - operation: forgeRing
```

Hier muss `/api/rings` eine echte Seite sein. Schreiben Sie also eine in `content/en/api/rings/index.md`. Ein Pfad unter dem URL-Präfix einer API, der keine Seite ist, lässt den Build scheitern. Siehe [Seitennavigation](/de/configuration/side-navigation).

{% callout type="tip" title="Live ansehen" %}
Die Gruppe [Rings of Power API](https://www.api-demo.mordoc.dev/api/rings) in der Seitenleiste der Demo hat eine eigene Seite und eine Liste von Operationen.
{% /callout %}

## Leitfadenseiten einbinden

Seiten wie Authentifizierung, Fehler und Paginierung sind gewöhnliche Markdown-Seiten. Verlinken Sie sie mit `path:` neben Ihren Operationen:

```yaml
- label: Guides
  children:
    - label: Authentication
      path: /guides/authentication
```

Schreiben Sie sie wie jede andere Seite. Siehe [Seiten schreiben](/de/getting-started/write-pages).

{% callout type="tip" title="Live ansehen" %}
Der Leitfaden [Authentication](https://www.api-demo.mordoc.dev/guides/authentication) der Demo steht in der Seitenleiste neben den API-Gruppen.
{% /callout %}

## Was passiert, wenn eine Operation nicht verlinkt ist?

Die Seite wird trotzdem gebaut und ist weiterhin durchsuchbar. Jeder, der die URL kennt, kann sie öffnen. Der Build gibt eine Warnung aus, die die Operationen auflistet, die nicht in der Seitenleiste stehen.

## Funktioniert mit der oberen Navigation

`operation:` funktioniert in `sidenav.yaml` und in den Sidenav-Dateien der einzelnen Bereiche, die mit der oberen Navigation verwendet werden. Siehe [Obere Navigation](/de/configuration/top-navigation).

## Nächster Schritt

[Beschreibungen anreichern](/de/api-reference/enrich-descriptions).
