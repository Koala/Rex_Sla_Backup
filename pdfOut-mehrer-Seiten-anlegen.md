---
tags: PDF, Seitenumbruch
---

15.08.2023

# mit pdfOut mehrer Seiten anlegen


## Frage

Wie kann man mit pdfOut mehrere Seiten anlegen, um z.B. aus einer Teilnehmerliste alle Zertifikate (1 Zertifikat je Seite) zu erzeugen und als 1 PDF auszugeben?
Ich habe 1 Template für das Zertifikat und eine Teilnehmerliste mit den Daten.  
Nun soll dieses Template einfach mehrfach abgearbeitet werden (Erzeugung des PDF) und gesammelt in 1 PDF-Ausgabe erscheinen.

## Antwort

Hast du nach der Seite mal ein page-break versucht?  

```html
<div style="page-break-before: always;"></div>
```

**Achtung!**

Nutzt man fixe Positionieren (position: fixed) in Verbindung mit page-break, dann läuft das dompdf ins Nirvana.
