---
tags: 
---

19.08.2023

# Aktuellen Artikel im Menü einfärben


## Frage

Wie war denn das nochmal mit dem current article im Menü einfärben?

## Antwort

Prüfen, ob `rex_article::getCurrent()->getId()` der jeweiligen Artikel-ID entspricht.
Dann die gewünschte / passende Klasse am `<li>` oder `<a>`-Element des Menüpunkts setzen, z.B: `class="active"`.

Oder via rex_navigation, ein Beispiel findet sich in der Doku
https://redaxo.org/doku/main/navigationen#factory-komplex

