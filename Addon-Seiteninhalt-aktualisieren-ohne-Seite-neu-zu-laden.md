---
tags: 
---

21.08.2023

# Addon Seiteninhalt aktualisieren ohne Seite neu zu laden


## Frage

ich habe in der boot.php eines addons eine funktion., die  per outputfiter ein tab ändert. auf der seite gibt es ein formular.

die werte ich dem tab schreibe ich in die rex_config.

klappt alles. ausser:

wenn ich das formular sende wird der tab inhalt nicht aktualisiert (obwohl die seite doch neu geladen - und die boot.php abgearbeitet wird - oder). erst wenn ich die seite von hand neu lade erscheinen die richtigen werte…

egal wo ich die funktion aufrufe. egal was ich mit pjax mache… verwirrt bin

ich nutze die factory

```php
$form = rex_config_form::factory('base_checklist'); 
```

## Antwort

in deinem form würde ich ` data-pjax="false"` als Attribute probieren

nicht bei jedem Feld … du setzt das direkt am `<form>` Tag

So würde ich es eher notieren

```php
$form = rex_config_form::factory('base_checklist');
$form->setFormAttribute('data-pjax', 'false');

$field = $form->addCheckboxField('be_noch_irgendetwas');
$field->addOption('Noch irgendetwas', 1);
```
