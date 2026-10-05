# personal-website

Bewerbungswebsite mit Blog von Tom-Niklas Müller. GitHub Pages baut die Seite bei jedem Push auf `main` automatisch mit Jekyll; ein eigener Build-Schritt ist nicht nötig.

Live: https://tomu1996.github.io/personal-website/

## Aufbau

- `index.html` – Startseite (Profil, Schwerpunkte, Erfahrung, Kenntnisse, Studium, Kontakt)
- `blog/index.html` – Übersicht aller Artikel
- `_posts/` – die Artikel als Markdown-Dateien
- `_drafts/vorlage.md` – Vorlage für neue Artikel (wird nicht veröffentlicht)
- `_layouts/` – gemeinsamer Seitenrahmen (`default.html`) und Artikelansicht (`post.html`)
- `_includes/post-row.html` – eine Zeile der Artikelliste
- `_config.yml` – Einstellungen für Jekyll
- `assets/style.css` – Gestaltung, inklusive Dunkelmodus und mobiler Ansicht
- `assets/fonts/` – lokal ausgelieferte Schriften (Lizenzen in `LICENSES.txt`)
- `assets/blog/` – Bilder für Artikel

## Einen Artikel schreiben

1. In `_posts/` eine Datei nach dem Muster `JJJJ-MM-TT-kurzer-titel.md` anlegen, zum Beispiel `2026-10-12-rechnungseingang-automatisieren.md`. Das Datum im Dateinamen ist das Veröffentlichungsdatum, der Rest wird zur Adresse: `/blog/rechnungseingang-automatisieren/`.
2. Die Datei beginnt mit diesem Kopf, danach folgt der Text in Markdown:

   ```markdown
   ---
   title: Rechnungseingang automatisieren
   description: Ein bis zwei Sätze für die Übersicht und unter dem Titel.
   ---

   Hier beginnt der Artikel.
   ```

3. Committen und pushen. Nach ein bis zwei Minuten steht der Artikel im Blog, auf der Startseite (die neuesten drei) und im Feed unter `/feed.xml`.

Das geht auch ohne lokale Umgebung direkt auf GitHub: Ordner `_posts` öffnen, **Add file → Create new file**, Inhalt einfügen, **Commit changes**.

`_drafts/vorlage.md` zeigt Überschriften, Listen, Codeblöcke und Zitate. Ein Artikel mit einem Datum in der Zukunft erscheint erst, wenn die Seite nach diesem Datum neu gebaut wird.

### Bilder

Bild in `assets/blog/` ablegen und im Artikel so einbinden:

```markdown
![Beschreibung des Bildes]({{ '/assets/blog/dateiname.png' | relative_url }})
```

### Code mit doppelten geschweiften Klammern

Jekyll wertet `{{ … }}` und `{% … %}` als Vorlagen-Syntax aus. Pipeline-Beispiele aus Azure DevOps oder GitHub Actions enthalten genau solche Ausdrücke. Damit sie unverändert im Artikel erscheinen, den Codeblock in `raw` einschließen:

````markdown
{% raw %}
```yaml
steps:
  - script: echo ${{ parameters.version }}
```
{% endraw %}
````

### Entwürfe

Dateien in `_drafts/` werden nicht veröffentlicht. Zum Veröffentlichen die Datei nach `_posts/` verschieben und das Datum vor den Dateinamen setzen.

## Lokale Vorschau

Mit installiertem Ruby und Bundler:

```
bundle install
bundle exec jekyll serve --drafts
```

Die Seite läuft dann unter http://localhost:4000/personal-website/ und zeigt auch die Entwürfe.

## Veröffentlichung

Unter **Settings → Pages** ist „Deploy from a branch“ mit Branch `main` und Ordner `/ (root)` eingestellt. Schlägt ein Build fehl, bleibt die zuletzt veröffentlichte Version online; die Fehlermeldung steht im Repository unter **Actions**.
