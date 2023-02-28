---
tags: CKEditor, CK-5, CK5, rex_form
---

27.02.2023

# CKEditor Textarea Größe mit rex_form festlegen


## Frage

Weitere Frage zu rex_form, die TEXTAREA hat bereits den CK-5 Editor eingebunden, nun soll das Eingabefeld aber eine bestimmte Größe in rows / cols festgelegt werden, wie bewerkstellige ich dies?

```php
$attributes = array(
    'class' => 'form-control cke5-editor',
    'data-profile' => 'nice',
    'rows'  => 10,
    'cols' => 15
);
$field = $form->addTextAreaField('project_text', $value = null, $attributes);
```

## Antwort

- Das machst du in den Profileinstellungen vom CKEditor...

![[CKEditor-Textarea-Groesse-festlegen_20230227.png]]

- Und es geht auch mit den folgenden Attributen:  

```php
$attributes = array(
        ‘class’ => ‘form-control cke5-editor’,
        ‘data-profile’ => ‘nice’,
        ‘data-max-height’ => 400,
        ‘data-min-height’ => 200
    );
```

Danke für den Hinweis hat geholfen.