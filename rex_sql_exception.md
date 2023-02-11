---
tags: sql
---

08.02.2023

# rex_sql_exception Fehlersuche


## Frage

```rex_sql_exception```:  Wie finde ich nun nochmal raus, was diesen Fehler auslöst

![[rex_sql_exception_20230208.png]]

## Antwort

- Die Meldung tritt auf, wenn eine Query abgesetzt wird, die 0 Zeilen zurückliefert, und dann aber trotzdem auf Werte aus dem Resultset zugegriffen wird.  
z.b.  

``` php
$sql->setQuery(...); // hier eine query, die aktuell nix liefert
$sql->getValue('foo'); // hier der fehler
```

- also sollte ein  

``` php
if($sql->getRows() > 0) {
// hier dann der rest
}
```

drumrum helfen
