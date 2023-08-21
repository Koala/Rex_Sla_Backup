---
tags: rex_formatter, intlDate
---

05.06.2023

# Inputfeld Ausgabe als Datum und Zeit formatieren


## Frage

Ich habe ein Input Feld

```html
<input class="form-control" id="" type="datetime-local" name="REX_INPUT_VALUE[2]" value="REX_VALUE[2]" />
```

nur wie muß ich die Ausgabe machen damit ich das Datum und die Uhrzeit bekomme?

## Antwort

Siehe Doku [Formatierungen](https://redaxo.org/doku/main/formatierungen)

Fürs Datum:
```php
echo rex_formatter::intlDate(REX_VALUE[2], IntlDateFormatter::LONG);
```


