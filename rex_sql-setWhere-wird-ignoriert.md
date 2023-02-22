---
tags: rex_sql
---

22.02.2023

# Warum wird setWhere in diesem rex_sql ignoriert?


## Frage

Kann mir jemand sagen warum hier meine setWhere ignoriert werden?  

``` php
$sql = rex_sql::factory(1);
$sql->setdebug();
$sql->setTable('rex_article');
$sql->select('name');
$sql->setWhere(['id' => $currentID]);
$sql->setWhere(['clang_id' => $leadingClangID]);
$name = $sql->getValue('name');
```

## Antwort

- Problem 1: select() führt die query aus. setwhere muss also vorher kommen 
- Problem 2: es kann nur ein setWhere geben, das zweite überschreibt das erste
- Ahhh,  also meine Wheres in ein Array in ein setWhere
