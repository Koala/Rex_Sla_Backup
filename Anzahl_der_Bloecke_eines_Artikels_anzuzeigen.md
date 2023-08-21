---
tags: rex_sql, ctype
---

08.02.2023

# Anzahl der Blöcke im 2. ctype anzuzeigen

## Frage

Gibt es eine Funktion, um die Anzahl der Blöcke im 2. ctype anzuzeigen?


## Antwort

Mittels SQL

``` php
$artcount = rex_sql::factory();
$artcount->setQuery('SELECT * FROM rex_article_slice WHERE article_id = :aid AND ctype_id = :cid', ['aid' => 1, 'cid' => 1]);
dump($artcount->getRows());

echo 'Anzahl Blöcke = '.$artcount->getRows();
``` 

