--- 
Tags: 
--- 
03.02.2023

# FA_Icon_Picker_AddOn

## Frage
Hi Leute, ich nutze das FA Icon Picker AddOn und habe die Domain einer Webseite geändert. Anscheinend wird aber irgendwo eine feste URL gespeichert, denn alle Icon-Aufrufe gehen noch auf die alte URL, auch nach Löschung des System- umd MediaManager-Caches. Weiß jemand, wo ich das ändern kann?

## Antwort
Jo das ist ne offene Flanke leider. Wird in einem Kommenden Release gefixt. Ich kann dir nur sagen, wie du es manuell fixt (auf die Schnelle)

Hier suchst du dir das Paket das gerade aktiv ist und gehst in den entsprechenden Ordner

![Alt text](bilder/FA_Icon_Picker_AddOn_20230203.png?version%3D1675615973166)

Dort gehst du in den Ordner /css/ und editierst die Datei all.min.css
Dort suchst du in deinem Editor dann mal nach url(

Da stehen dann (leider, my bad) absolute Domains drin. Das macht Ärger. Lösch die raus mit dem Editor, sodass am Ende alles mit /index.php beginnt, also z.B.:

url(/index.php?rex_media_type=font-awesome-font-src&rex_media_file=fa-brands-400.eot)

Das müsste mit Suchen und ersetzen sehr leicht zu machen sein.

Dann funzt es für alle Domains, auch in einer Multi-Domain-Umgebung. Darüber ist mir das auch selber aufgefallen

Musste dran denken, wenn du ein anderes Paket auswählst oder ein neues hochlädst, das nochmal anzupassen.

