---
title: Grav CMS
taxonomy:
    category: docs
---

Diese Seite wurde mit dem "flat Content Management System GRAV" erstellt. Hier wrede ich einige interessante Sachen posten, die damit zu tun haben.

### Style ändern:
Das hier genutzte Theme ist "Learn2" mit "Learn 2 with Git Sync".

Wenn man nun diese Themes anpassen will, muss man im eigenen Theme z.B.: "myTheme" Anpassungen vornehmen. Um das Aussehen zu verändern ändert man die "custom.css" Datei in folgendem Order auf dem Server:
`/user/themes/mytheme/css/custom.css`

Diese CSS Datei überschreibt alle in den Themes vorhandenen Einstellungen.

### Teile der Website ändern:
Um Teile der Seite zu ändern nutzt man auch die Dateien im Ordner: `/user/themes/mytheme/`. 

Die Suche der Seite wird mit einem Platzhalter ausgefüllt, der "Search Documentation" anzeigt. Hier sollte aber besser "Suchen..." stehen. Dies kann man bewerkstelligen, indem man in `/user/themes/mytheme/templates/partials/` die Datei `search.html.twig` einfügt. Die Vorlage der Datei bekommt man aus dem "Learn2" Theme `/user/themes/learn2/templates/partials`.
