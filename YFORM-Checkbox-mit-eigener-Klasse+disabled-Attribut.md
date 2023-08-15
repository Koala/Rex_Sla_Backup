---
tags: 
---

15.08.2023

# YFORM: Checkbox mit eigener Klasse und disabled Attribut


## Frage

Wie müsste denn die PHP-Notation einer YForm-Checkbox sein (choice-Feld), wenn ich dieser eine eigene Klasse und ein disabled-Attribut geben möchte?

## Antwort

Ich schreibe die Values gerne so:

```php
$yform->setValueField('choice', [
        'name' => 'status',
        'label' => '{{ label.status }}',
        'choices' => 'SELECT `name` AS label, `id` AS value FROM `rex_yf_status ORDER BY `label`',
        'expanded' => false,
        'multiple' => false,
        'attributes' => '{"required":"","placeholder":"{{ label.please_select }}"}'
    ]);
```

