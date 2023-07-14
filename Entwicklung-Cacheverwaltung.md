---
tags: Cache
---

14.07.2023

# Entwicklung: Cacheverwaltung


## Frage

Wann wird der Cache von Addons `(redaxo/cache/addons/<AddonName>)` gelöscht?


## Antwort

https://redaxo.org/doku/main/caching

Wird ein Addon deaktiviert, de-installiert oder gelöscht, wird das zum Addon gehörende Verzeichnis in `redaxo/cache/addons/` automatisch gelöscht.
Addons müssen selbstständig dafür sorgen, dass nach einer Aktivierung die Cachedateien wieder erstellt werden.
Beachte die Hinweise für Entwickler:
https://redaxo.org/doku/main/caching#hinweise
