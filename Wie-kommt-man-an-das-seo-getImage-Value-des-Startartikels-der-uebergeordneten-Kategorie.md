---
tags: 
---

24.02.2023

# Wie kommt man an das $seo-getImage() Value des Startartikels der übergeordneten Kategorie?


## Frage

Wie kommt man denn easy peasy an das $seo-getImage() Value des Startartikels der dem aktuellen Artikel übergeordneten Kategorie?

## Antwort

``` php
$art->getClosestValue('yrewrite_image')
``` 
könntest du nehmen.
das schaut zunächst im artikel selbst, und geht dann alle parents durch, bis irgendwo ein bild gesetzt ist

das geht zwar kategorien durch. aber kategorie ist ja  letztlich gleich startartikel, somit ist yrewrite_image auch im kategorie-objekt gesetzt, wenn es im startartikel gesetzt ist

Siehe auch: https://github.com/redaxo/redaxo/pull/3587

https://redaxo.org/cms/news/redaxo-511-veroeffentlicht/
