# personal-website

Bewerbungswebsite von Tom-Niklas Müller: eine statische Seite aus HTML und CSS, ohne Build-Schritt und ohne JavaScript.

## Aufbau

- `index.html` – alle Inhalte (Profil, Schwerpunkte, Erfahrung, Kenntnisse, Studium, Kontakt)
- `assets/style.css` – Gestaltung, inklusive Dunkelmodus und mobiler Ansicht
- `assets/fonts/` – lokal ausgelieferte Schriften (Lizenzen in `LICENSES.txt`)
- `assets/tom-niklas-mueller.jpg` – Porträt
- `assets/favicon.svg` – Icon für den Browser-Tab

## Lokal ansehen

`index.html` im Browser öffnen, oder im Projektordner einen kleinen Server starten:

```
python3 -m http.server 8000
```

Danach ist die Seite unter http://localhost:8000 erreichbar.

## Veröffentlichen mit GitHub Pages

1. Im Repository **Settings → Pages** öffnen.
2. Unter „Build and deployment“ als Quelle **Deploy from a branch** wählen.
3. Branch `main` und Ordner `/ (root)` auswählen und speichern.

Nach ein bis zwei Minuten ist die Seite unter `https://tomu1996.github.io/personal-website/` erreichbar. Jeder weitere Push auf `main` aktualisiert sie automatisch.

## Inhalte ändern

Alle Texte stehen direkt in `index.html`. Eine neue berufliche Station ist ein weiterer `<li class="stage">`-Block in der Liste `pipeline`; die jeweils aktuelle Station trägt zusätzlich die Klasse `stage-running`.
