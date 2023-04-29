---
tags: 
---

29.04.2023

# Schreibrechte Dateien / Verzeichnisse


## Frage
Wie werden die richtigen Schreibrechte für Dateien / Verzeichnisse gesetzt, beim Erstellen der Dateien / Verzeichnisse.

## Antwort
Beispiel zum Schreiben im Verzeichnis ***redaxo/cache/addons/***
Dateien:
rex_file::put(rex_path::addonCache('dein Verzeichnisname/DerDateiname'),'');

Verzeichnisse:
rex_dir::create(rex_path::addonCache('dein Verzeichnisname'));

