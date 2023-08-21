---
tags: SSL
---

07.08.2023

# Fehlermeldung: ERR_CONNECTION_REFUSED


## Frage

Auf meinem lokalen Entwicklungsserver habe ich ein Problem. Der Server funktioniert und PHP Dateien können  abgerufen werden. Aber sobald ich versuche ein Redaxo aufzurufen - und wenn es nur die Redaxo Installationsroutine ist - erhalte ich im Browser einen ERR_CONNECTION_REFUSED. Wo kann ich ansetzen um das Problem zu lösen?

## Antwort

*Anmerkung vorweg: auf dem lokalen Entwicklungsserver ist kein SSL eingerichtet*

Prüfe ob in der `redaxo/data/core/config.yml` einer der Werte (oder beide) auf `true` gesetzt sind:
`use_https` und `use_hsts`
Falls ja, setzte sie auf `false` und versuche den Seitenaufruf erneut.
