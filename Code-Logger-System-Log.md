---
tags: System-Log, Fehlermeldung, Logger, REX-Log
---

14.07.2023

# Code - Logger - System-Log


## Frage

Wie können Meldungen (Fehlermeldung, Error, Warning) in die Logdatei (Systemlog) geschrieben werden?  
Gibts in einer Doku etwas dazu?

Gabs da nicht eine Möglichkeit einen Eintrag ins REX-Log zu schreiben?

## Antwort

### Möglichkeit 1

- Hinweistextfarbe **rot**:
```php
rex_logger::factory()->emergency('Emergencymeldung');
rex_logger::factory()->alert('Alertmeldung');
rex_logger::factory()->critical('Criticalmeldung');
rex_logger::factory()->error('Errormeldung');
```

- Hinweistextfarbe **ocker**:
```php
rex_logger::factory()->warning('Warnungsmeldung');
```

- Hinweistextfarbe **blau**:
```php
rex_logger::factory()->notice('Noticemeldung');
rex_logger::factory()->info('Infomeldung');
```

- Hinweistextfarbe **schwarz**:
```php
rex_logger::factory()->debug('Debugmeldung');
```

Die Bezeichnungen der Loglevel sind definiert in der Datei *redaxo/src/core/vendor/psr/log/Psr/Log/AbstractLogger.php*

### Möglichkeit 2

[https://friendsofredaxo.github.io/phpdoc/classes/rex-logger.html](https://friendsofredaxo.github.io/phpdoc/classes/rex-logger.html)

Das kann dann so aussehen:  
```php
rex_logger::factory()->log('logevent', 'Mein Text zum Event');
```

Zum Logger gibts keinen Eintrag in der Doku, nur hier:  
[https://redaxo.org/doku/main/addon-phpmailer#errormail](https://redaxo.org/doku/main/addon-phpmailer#errormail)

Übersicht der von Redaxo verwendeten Schlüsselworte:
```php
E_USER_ERROR, E_ERROR, E_COMPILE_ERROR, E_RECOVERABLE_ERROR => 'Fatal error',
E_PARSE => 'Parse error',
E_USER_WARNING, E_WARNING, E_COMPILE_WARNING => 'Warning',
E_USER_NOTICE, E_NOTICE => 'Notice',
E_USER_DEPRECATED, E_DEPRECATED => 'Deprecated',
E_STRICT => 'Strict',
```

- Hinweistextfarbe **rot**:
```php
rex_logger::factory()->log('Fatal error', 'Mein Text zum Event');
rex_logger::factory()->log('Parse error', 'Mein Text zum Event');
rex_logger::factory()->log('Strict', 'Mein Text zum Event');
```
Jedes andere frei wählbare Schlüsselwort (Anstelle von 'logevent') wird ebenfalls **rot** dargestellt.


- Hinweistextfarbe **ocker**:
```php
rex_logger::factory()->log('Warning', 'Mein Text zum Event');
```

- Hinweistextfarbe **blau**:
```php
rex_logger::factory()->log('Notice', 'Mein Text zum Event');
rex_logger::factory()->log('Deprecated', 'Mein Text zum Event');
```

*Anmerkung: die Farben können je nach Backend auch anders sein*


