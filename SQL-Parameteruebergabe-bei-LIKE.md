---
tags: rex_sql, like, wildcards
---

20.02.2023

# SQL Parameterübergabe bei Suche mit LIKE


## Frage

Wie muss ich das richtig schreiben, damit ich kein "Invalid parameter number" bekomme:

``` php
$schlagwort = rex_sql::factory();
    $params = array();
    $params['searchschlagwort'] = rex_request('searchschlagwort');
    $select = 'SELECT * from rex_article WHERE art_schlagwort LIKE "%:searchschlagwort%"';
    $schlagwort->setQuery($select,$params);
```


## Antwort


``` php
$schlagwort = rex_sql::factory();
    $params = array();
	$params['searchschlagwort'] = "%".$sql->escapeLikeWildcards(rex_request('searchschlagwort'))."%";
    $select = 'SELECT * from rex_article WHERE art_schlagwort LIKE :searchschlagwort';
    $schlagwort->setQuery($select, $params);
```

bei Like sind ja ```%```, ```-``` und ```\``` Sonderzeichen.
Wenn die jemand selbst eingibt als Suche, dann sollten aber exakt die Zeichen gewertet werden, somit sollten sie escaped werden.
Also wenn jemand als Suche 30% eingibt, soll damit nicht gemeint sein “30 gefolgt von Platzhalter-Zeichen für beliebige Zeichen” sondern “30 gefolgt von Prozentzeichen”

