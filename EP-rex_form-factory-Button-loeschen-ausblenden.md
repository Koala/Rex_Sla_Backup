---
tags: EP, ExtensionPoint, rex_form, REX_FORM_CONTROL_FIELDS
---

28.02.2023

# rex_form::factory Button "löschen" ausblenden


## Frage

Hallo ,  im
```rex_form::factory```
bekomme ich ein Formular im AddOn angezeigt mit speichern und löschen des Datensatzes. Wie kann ich den Button löschen ausblenden?

## Antwort

Über den EP: 
`REX_FORM_CONTROL_FIELDS`

Praxistipp: erste Zeile `dump($ep)`  damit man sieht, was da alles ankommt.
Subject enthält das Array `$controlFields` . 

```php
$controlFields = $ep->getSubject();
$controlFields['delete'] = '';
$ep->setSubject($controlFields);
```
