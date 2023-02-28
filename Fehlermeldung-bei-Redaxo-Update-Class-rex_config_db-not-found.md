---
tags: rex_config_db
---

22.02.2023

# Fehlermeldung bei Redaxo Update: Class 'rex_config_db' not found


## Frage

Betrifft Update auf Redaxo-Version 5.12.1 

ich versuche gerade eine Seite nach langer Zeit upzudaten und bin nun bei der Version 5.12.1 in einen 500er reingelaufen. Die Meldung besagt: 
```php
Error | Class 'rex_config_db' not found | redaxo/src/core/lib/rex.php | 352
```  

Kann jemand etwas damit anfangen und mir einen Tipp geben, ob und wie ich das wieder fixen kann?

## Antwort

- ```redaxo/cache/core/autoload.cache``` löschen
- das Problem ist in neueren Versionen behoben

