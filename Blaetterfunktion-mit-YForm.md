---
tags: YForm, Blätterfunktion
---

27.02.2023

# Wie kann vorwärts / rückwärts mit YForm / YOrm und Url gemacht werden?


## Frage

Wie mache ich denn vorwärts / rückwärts mit YForm / YOrm und Url ? Also next topic , previous Topic?

## Antwort

Falls es darum geht, die ID bzw. den Datensatz des vorherigen/folgenden Datensatzes herauszufinden:

```php
$currentDataset = rex_yform_manager_dataset::get(CURRENT_ID);
$prevDataset = rex_yform_manager_dataset::query()
    ->where('prio < ?', [$currentDataset->getValue('prio')])
    ->orderBy('prio', 'desc')
    ->limit(1)
    ->findOne();
$nextDataset = rex_yform_manager_dataset::query()
    ->where('prio > ?', [$currentDataset->getValue('prio')])
    ->orderBy('prio', 'asc')
    ->limit(1)
    ->findOne();
```
    
Das geht natürlich auch mit Datum-Spalten. Da muss dann ggf. noch ein id != CURRENT_ID rein.

Prinziell musst du einfach nach Sortierungsattribute(n) mit > oder < filtern und auch danach sortieren.
