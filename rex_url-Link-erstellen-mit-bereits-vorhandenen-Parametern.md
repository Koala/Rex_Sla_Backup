---
tags: 
---

02.06.2023

# rex_url: Link erstellen mit bereits vorhandenen Parametern

## Frage

Wie kann ich einen Link mit rex_url::currentbackendpage() erstellen, und alle bereits vorhandenen url Parameter mit übernehmen?


## Antwort

[rex_context](https://friendsofredaxo.github.io/phpdoc/classes/rex-context.html) hilft da weiter:

```php
$con = rex_context::fromGet();
$con->getUrl(["asdf" => true]);
```
