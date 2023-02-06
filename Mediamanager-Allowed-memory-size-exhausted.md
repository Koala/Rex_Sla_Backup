---
Tags: 
---

06.02.2023

# Mediamanager "Allowed memory size exhausted"


## Frage
Woran kann denn so ein Fehler im Log zustande kommen?

```
Allowed memory size of 83886080 bytes exhausted (tried to allocate 24576 bytes)
 redaxo/src/addons/media_manager/lib/managed_media.php
```


## Antwort
- Dein Bild ist zu groß um vom Mediamanager verarbeitet werden zu können

- mhmm, tatsächlich. es tritt nur bei einer grafik auf.
wobei diese auch "nur" 3,6 mb hat.
Ich dachte, das müsste der medienpool und der media manager schaffen

- kommt drauf an was du damit anstellst

- hat nur zwei effekte:

        focuspint fit
        skalieren (auf 500x500)


- PHP Speicher auf mindestens 128 MB erhöhen
