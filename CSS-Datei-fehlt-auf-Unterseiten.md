---
Tags: CSS, 
---

02.02.2023

# CSS-Datei fehlt auf Unterseiten


## Frage
habe ich festgestellt das er http://domain.top/unterseite/layout/main.css wohl auf Unterseiten die CSS sucht, die liegen aber im root Ordner http.//domain.top/layout/main.css. Wo schaue ich dann?


## Antwort

Dann musst auch auf die korrekte Verlinkung deiner CSS im Template achten: 
```
href="/layout/main.css"
```
steuert immer den Root an während 
```
href="layout/main.css"
```
immer im aktuell Pfad sucht und dann kommt da sowas raus wie von dir beschrieben... 

Ich vermute du hast relativ statt absolut verlinkt... 

Schau mal ob bei dir der Slash bei der CSS-Verlinkung im Template steht...

