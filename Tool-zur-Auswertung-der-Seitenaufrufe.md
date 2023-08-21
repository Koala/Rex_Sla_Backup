---
tags: Statistik
---

12.05.2023

# Tool zur Auswertung der Seitenaufrufe


## Frage

Gibt es in Redaxo ein Tool zur Auswertung der Seitenaufrufe?
Welche Möglichkeiten gibt es noch?


## Antwort

1. Das Statistik Addon "statistics".
2. Matomo (selbst gehostet + Matomo Addon für Redaxo)


### statistics AddOn
Im Zweifelsfalle immer den Datenschutzbeauftragten mit der Prüfung betrauen :-)
**Datenschutzhinweis:**

Streng genommen sind in der Tabelle personenbezogene Daten.  
Gespeichert wird die IP adresse, um feststellen zu können, ob aufrufe vom selben Besucher kommen oder nicht (ermöglicht Aufteilung Besuche und Besucher). Technisch wird aber nicht die IP alleine gespeichert sondern ein Hash aus IP , User agent und besuchter URL. Um also das personenbezogene Merkmal IP eines Besuchers herauszubekommen müsstest du diese drei Teile herausfinden, was aufgrund der schieren Anzahl Möglichkeiten annähernd unmöglich ist per brute force. Die IP ist also relativ gut geschützt.

- Wäre das Consent-pflichtig zu sehen?
- sehe ich auf den ersten blick nicht consentpflichtig
- Die Lösung in diesemAddOn ist vergleichbar mit Access Logs , auch die erfordern keine Consent. Aber in den dsb macht es Sinn über die Dauer der Speicherung zu informieren


