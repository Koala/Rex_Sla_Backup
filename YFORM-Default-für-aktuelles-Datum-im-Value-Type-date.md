---
tags: 
---

18.05.2023

# YFORM Default für aktuelles Datum im Value Type date


## Frage

Wie konfigurier ich denn ein Value Type `date` so, dass im value Attribut stadadmäßig **nicht** 0000-00-00 steht?  Welcher Param ist denn fürs aktuelle Datum?

```php
$yform->setValueField('date', ['until', 'bis','2018','2038','d.m.Y','0','0','input:date']);
```

Output:  

```Html
<input class="form-control" name="until" type="date" id="yform-..." value="0000-00-00" />
```

## Antwort

```php
$yform->setValueField('date', ['until', 'bis','2018','2038','d.m.Y','1','0','input:date']);
```
