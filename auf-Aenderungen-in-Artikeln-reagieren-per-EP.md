---
tags: EP, ExtensionPoint
---

08.02.2023

# auf Änderungen in Artikeln reagieren per ExtensionPoint


## Frage

Gibt es einen ExtensionPoint wenn Slices online/offline geschaltet werden?
Gibt es einen ExtensionPoint der auf Artikeländerungen reagiert.

## Antwort

```ART_CONTENT_UPDATED```

- wobei der an ganz vielen stellen greift.  
gibt aber einen param “action” oder so im ep, worüber man auslesen kann, welcher grund es genau ist fürs content-update
- das ist okay, ich muss nur wissen wenn sich der content geändert hat
- Ah, ja dann passt der EP genau. denn der wurde extra so eingeführt, dass er möglichst bei allen content-änderungen greift. egal ob neuer slice, slice offline oder oder
