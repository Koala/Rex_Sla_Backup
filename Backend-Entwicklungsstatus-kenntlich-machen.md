---
tags: Backend
---

27.07.2023

# Backend: Entwicklungsstatus kenntlich machen


## Frage

Ist es möglich das Backend im Aussehen so zu ändern, dass es auch durch Einspielungen vom Backup nicht geändert werden kann oder automagisch wieder zurückgeändert wird?
Hintergrund:  
Ich möchte besser sehen, ob ich gerade auf dem lokalen System oder auf der externen Seite bin.



## Antwort

![[Backend-Entwicklungsstatus-kenntlich-machen_20230727.png]]

Die Badges kommen aber über das Addon für ydeploy, oder?

Ja genau. somit nicht direkt einzeln nutzbar. aber man kann sich den code ggf. aus ydeploy rauskopieren und adaptieren

[https://github.com/yakamara/ydeploy/blob/main/lib/handler.php#L27-L50](https://github.com/yakamara/ydeploy/blob/main/lib/handler.php#L27-L50)

da wird es per output filter eingefügt

und das css dazu ist im assets ordner