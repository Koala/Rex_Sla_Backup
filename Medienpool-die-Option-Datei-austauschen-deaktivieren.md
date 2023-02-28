---
tags: Medienpool, rex_url, rex_i18n
---

06.01.2022

# Medienpool die Option "Datei austauschen" deaktivieren


## Frage
Wie kann ich im Medienpool die Option "Datei austauschen" deaktivieren? Ich will vermeiden, dass viel zu große Abbildungen im Medienpool landen.


## Antwort
das form (core/form/form.php) fragment in das project addon kopieren und dort checken wo man ist und das element entfernen

dort dann im oberen teil, vor dem output:

```php
$el = null;
if(rex_url::currentBackendPage() === 'index.php?page=mediapool/media') {
 $exchangeTitle = rex_i18n::msg('pool_file_exchange');
 $el = array_filter($this->elements, function ($element) use ($exchangeTitle) {
 return $element['label'] === '<label>'.$exchangeTitle.'</label>';
 });

 if($el) {
 $el = array_values($el);
 }
}
```

und im loop:

```php
if($el && $element == $el[0]) {
 continue;
}
```

nicht schön, sollte aber funktionieren


habe die Datei form.php hier hin kopiert redaxo/src/addons/project

```php
if(rex_url::currentBackendPage() === 'index.php?page=mediapool/media') {
 $exchangeTitle = rex_i18n::msg('pool_file_exchange');
 $el = array_filter($this->elements, function ($element) use ($exchangeTitle) {
 return $element['label'] === '<label>'.$exchangeTitle.'</label>';
 });

 if($el) {
 $el = array_values($el);
 }
}


$out = '';


foreach ($this->elements as $element) {
    $id = isset($element['id']) && '' != $element['id'] ? ' id="' . $element['id'] . '"' : '';
    $label = isset($element['label']) && '' != $element['label'] ? '<dt>' . $element['label'] . '</dt>' : '';
    $field = isset($element['field']) && '' != $element['field'] ? $element['field'] : '';

    $before = $element['before'] ?? '';
    $after = $element['after'] ?? '';

    $header = $element['header'] ?? '';
    $footer = $element['footer'] ?? '';

    $note = isset($element['note']) && '' != $element['note'] ? '<p class="help-block rex-note">' . $element['note'] . '</p>' : '';

    $classes = '';

    $error = '';
    if (isset($element['error']) && '' != $element['error']) {
        $classes .= ' has-error';
        $error = '<p class="rex-form-error">' . $element['error'] . '</p>';
    }
    if (isset($element['required']) && $element['required']) {
        $classes .= ' rex-is-required';
    }
    if (isset($element['class']) && '' != $element['class']) {
        $classes .= ' ' . $element['class'];
    }
	
	if($el && $element == $el[0]) {
 continue;
}

    $out .= $header;
    $out .= '<dl class="rex-form-group form-group' . $classes . '"' . $id . '>';
    $out .= $label;
    $out .= '<dd>' . $before . $field . $after . $note . $error . '</dd>';
    $out .= '</dl>';
    $out .= $footer;
}

echo $out;
```


die `form.php` muss im gleichen ordner liegen wie im core
`redaxo/src/addons/project/fragments/core/form/form.php`

