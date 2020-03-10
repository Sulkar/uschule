---
title: 'Grav CMS'
taxonomy:
    category:
        - docs
---

Diese Seite wurde mit dem "flat Content Management System GRAV" erstellt. Hier werde ich einige interessante Sachen posten, die damit zu tun haben.

[official Grav Forums](https://discourse.getgrav.org/)

### Markdown Infos

Die seiten werden mit der Markdown Sprache verfasst. Hier findet man Grav typische Befehle:
[Markdown Info](./01markdown_info)

### Git Integration

Die Seite nutzt das Theme "Learn 2 with Git Sync". Damit kann man den Inhalt der Website mit Hilfe eines Git Repositories verwalten. Dies funktioniert in zwei Richtungen.

1. vom Git Repository zur Website: Wenn sich das Repository ändert, wird auch die Seite verändert.
2. von der Website zum Git Repository: Wenn man im Admin Bereich der Website etwas ändert, wird auch das Repository verändert.

### Style ändern

Das hier genutzte Theme ist "Learn2" mit "Learn 2 with Git Sync".

Wenn man nun diese Themes anpassen will, muss man im eigenen Theme z.B.: "myTheme" Anpassungen vornehmen. Um das Aussehen zu verändern ändert man die "custom.css" Datei in folgendem Order auf dem Server:
`/user/themes/mytheme/css/custom.css`

Diese CSS Datei überschreibt alle in den Themes vorhandenen Einstellungen.

### Teile der Website ändern

Um Teile der Seite zu ändern nutzt man auch die Dateien im Ordner: `/user/themes/mytheme/`.

Die Suche der Seite wird mit einem Platzhalter ausgefüllt, der "Search Documentation" anzeigt. Hier sollte aber besser "Suchen..." stehen. Dies kann man bewerkstelligen, indem man in `/user/themes/mytheme/templates/partials/` die Datei `search.html.twig` einfügt. Die Vorlage der Datei bekommt man aus dem "Learn2" Theme `/user/themes/learn2/templates/partials`.

### Grav Login Plugin

Dieses Plugin ermöglicht das Einloggen auf der Website. Man kann dann z.B. eine Seite nur für registrierte Nutzer einsehbar machen. Dazu muss man im "Frontmatter" folgenden Code eingeben:

```json
access:
    site.login: true
    admin.login: true
```
