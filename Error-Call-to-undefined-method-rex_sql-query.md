---
tags: rex_sql
---

17.05.2023

# Error “Call to undefined method rex_sql::query()"


## Frage

Habe einen Cronjob angelegt zum löschen von Datensätzen nach X tagen. wenn ich den manuell ausführe, bekomme ich den Error “Call to undefined method rex_sql::query()” - das klingt irgendwie kaputt, oder? Die Methode gibts doch, oder?

## Antwort

Müsste es nicht `rex_sql::factory()->setQuery(...)` lauten?
