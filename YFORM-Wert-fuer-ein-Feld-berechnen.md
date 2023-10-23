---
tags:
  - YForm
---

23.10.2023

# YFORM Wert für ein Feld berechnen vor dem speichern



## Frage

wie kann ich beim Speichern eines Formulares den Wert für ein Feld berechnen und setzen, so dass es in die Datenbank gespeichert wird?

## Antwort

```php
$yform->setActionField('callback', [
    function (rex_yform_base_abstract $form) {
        $form->params['value_pool']['sql']['field_c'] = $form->params['value_pool']['sql']['field_a'] + $form->params['value_pool']['sql']['field_b'];
    }
]);
```
