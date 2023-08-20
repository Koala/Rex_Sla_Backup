---
tags: Update, Addonänderungen, Ergänzung, Projekt-Addon
---

14.08.2023

# Updatesicher Addonänderungen anderer Addons speichern
## Frage

Wie lautet der Pfad im Project-Addon, Ergänzungen die ein anderes Addon beeinflussen, updatesicher gespeichert werden können.

## Antwort

Unter `project/pages` die Datei `anderesaddon.seitenname.php` anlegen. Und in der `project/package.yml` wie die Page in das andere Addon hängen:  

```php
pages:
    anderesaddon/seitenname:
        title: ...
```


