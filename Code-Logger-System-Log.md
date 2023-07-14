---
tags: System-Log, Fehlermeldung, Logger
---

14.07.2023

# Code - Logger - System-Log


## Frage

Wie können Meldungen (Fehlermeldung, Error, Warning) in die Logdatei (Systemlog) geschrieben werden?  
Gibts in einer Doku etwas dazu?


## Antwort

[https://friendsofredaxo.github.io/phpdoc/classes/rex-logger.html](https://friendsofredaxo.github.io/phpdoc/classes/rex-logger.html)

Das kann dann so aussehen:  
```php
rex_logger::factory()->log('logevent', 'Mein Text zum Event');
```

Zum Logger gibts keinen Eintrag in der Doku, nur hier:  
[https://redaxo.org/doku/main/addon-phpmailer#errormail](https://redaxo.org/doku/main/addon-phpmailer#errormail)



