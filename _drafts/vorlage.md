---
title: Titel des Artikels
description: Ein bis zwei Sätze, die in der Übersicht und unter dem Titel erscheinen.
---

Der erste Absatz führt ins Thema ein: Worum ging es in dem Projekt, und für wen ist der Artikel interessant?

## Ausgangslage

Fließtext schreibst du einfach als Absätze. **Fett** und *kursiv* funktionieren wie gewohnt, Links so: [Business Central](https://learn.microsoft.com/dynamics365/business-central/).

## Umsetzung

Aufzählungen:

- erster Punkt
- zweiter Punkt

Code steht in einem Block mit Sprachangabe:

```powershell
Get-BcContainerAppInfo -containerName "bcserver" -tenantSpecificProperties
```

Enthält der Code doppelte geschweifte Klammern, etwa in einer Pipeline, schließt du den Block in `raw` ein. Sonst versucht Jekyll, die Ausdrücke auszuwerten:

{% raw %}
```yaml
steps:
  - script: echo ${{ parameters.version }}
```
{% endraw %}

Einzelne Begriffe wie `app.json` setzt du in Backticks.

> Ein Zitat oder ein Merksatz steht in einer eingerückten Zeile.

## Ergebnis

Was hat es gebracht, und was würdest du beim nächsten Mal anders machen?
