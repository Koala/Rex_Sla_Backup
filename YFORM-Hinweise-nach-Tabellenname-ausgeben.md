---
tags: YFORM, EP, ExtensionPoint, YFORM_DATA_LIST, YFORM_DATA_LIST_QUERY
---

29.08.2023

# YFORM Hinweise nach Tabellenname ausgeben


## Frage

Kriegt man dort über der YFM Table irgendwie n custom success/error/warning/info alert rein?

![[YFORM-Hinweise-nach-Tabellenname-ausgeben_20230829.png]]
## Antwort

```php
rex_extension::register('YFORM_DATA_LIST_QUERY', static function (rex_extension_point $ep)
    {
        if (....) {
            echo rex_view::warning('.....');
        }
    }
);
```
Würde wohl auch im EP YFORM_DATA_LIST funktionieren.
