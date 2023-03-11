---
tags: YFORM, onChange
---

28.02.2023

# Kann in ein yForm Feld ein "onChange" eingebaut werden?


## Frage

Kann ich in ein yForm Feld ein "onChange" einbauen?

```php
$yform->setValueField(
            'email',
            ['email', '###business_email###', '#required:required', '#type:email', '#autocomplete:email', '#onChange:checkEmailDomain(this)']
        );
```

So geht's leider nicht.

## Antwort

```php
$yform->setValueField(
            'email',
            ['email', '###business_email###', '#required:required', '#type:email', '#autocomplete:email', '#attributes: {"onChange":"checkEmailDomain(this)"}']
        );
```

Welche du direkt via ```#``` ansprechen kannst, steht in den Definitionen
https://github.com/yakamara/redaxo_yform/blob/master/lib/yform/value/email.php#L52-L57
