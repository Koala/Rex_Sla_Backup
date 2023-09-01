---
tags: isOnline, isOffline
---

31.08.2023

# Hat eine Kategorie einen Artikel?


## Frage

Wie kann man abfragen ob eine Kategorie überhaupt einen Artikel enthält?

## Antwort

Jede Kategorie hat einen Startartikel. Daher ist die Frage nicht, ob eine Kategorie einen Artikel hat, sondern ob die Kategorie und damit der Startartikel der Kategorie, *Online* oder *Offline* ist.

```php
// gib eine Kategorie-ID vor
$cat = rex_category::get(REX_CATEGORY_ID);
// oder prüfe den aktuellen Artikel
$cat = rex_category::getCurrent();

if ($cat->isOnline()) {
    dump('Die Kategorie / der Startartikel der Kategorie ist online');
} else {
    dump('Die Kategorie / der Startartikel der Kategorie ist offline');
}
```

Mehrere Artikel einer Kategorie abzufragen ist ein anderes Thema :slightly_smiling_face:.

Siehe auch hier:  
[https://redaxo.org/doku/main/kategorien-artikel#kategorie-daten](https://redaxo.org/doku/main/kategorien-artikel#kategorie-daten)

