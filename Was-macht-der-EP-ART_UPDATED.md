---
tags: EP, Extensionpoint
---

22.02.2023

# Was macht der Extensionpoint ART_UPDATED?

## Frage

Seh ich das richtig dass der EP  ```ART_UPDATED``` nicht aufgerufen wird wenn ich innerhalb eines Artikels etwas ändere (also z.B. einen Slice lösche oder hinzufüge) ?

## Antwort

- wird nur aufgerufen, wenn der Artikel selbst verändert wird
- ART_UPDATED hat nix mit slices zu tun, nur mit dem artikel selbst
- wird nur in ```rex_article_service::editArticle()``` aufgerufen
- hier eine liste der EPs: man nehme was man brauche[https://redaxo.org/doku/main/extension-points#structure](https://redaxo.org/doku/main/extension-points#structure)

## Hinweis

Für alle Content-Änderungen gibt es einen zentralen EP `ART_CONTENT_UPDATED`.  
der greift bei neuen slices, veränderten slices, slice on/off, arbeitsversion/live, etc
[[auf-Aenderungen-in-Artikeln-reagieren-per-EP#Antwort|Siehe: auf Änderungen in Artikeln reagieren per ExtensionPoint]]

