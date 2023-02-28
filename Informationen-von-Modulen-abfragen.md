---
tags: rex_module, rex_sql
---

08.02.2023

# Informationen von Modulen abfragen


## Frage

Gibt es etwas wie `rex_module::get($id)` um Infos über das Modul zu bekommen (nicht den Slice). Als z.B. Modulnamen, key oder updatedate…


## Antwort

Ein direkter Zugriff über die Rex-API ist derzeit nicht vorgesehen.
Damit ist es aber möglich.

``` php
$module_id = rex_module::forKey('REX_MODULE_KEY')->getId();
$m_sql = rex_sql::factory()->setQuery("SELECT updatedate FROM rex_module WHERE id = $module_id");
echo date('d.m.Y, H:i:s', strtotime($m_sql->getValue('updatedate')));
```
