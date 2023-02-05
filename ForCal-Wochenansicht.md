03.02.2023

# ForCal-Wochenansicht

## Frage
kriege ich ForCal irgendwie dazu im Frontend initial (und ausschließlich) eine Wochenansicht zu zeigen, evtl auch noch mit der Einschränkung nur Zeiten zwischen 8.00 - 18.00 auszugeben? Mit  initialView: 'timeGridWeek', komme ich da nicht weiter.


## Antwort
minTime: "08:00:00",
maxTime: "18:00:00"'

:+1: das funzt - aber die Wochenansicht bekomme ich nicht hin...
muss mich später wohl nochmal in die Docs von 

timeGridPlugin

Ha!
plugins: ['timeGrid'],
in Hochkommata funzt

PS: das scheint zu gehen:
     slotMinTime: '08:00:00',
    slotMaxTime: '18:00:00'

Wobei es wohl max 19 sein muss

