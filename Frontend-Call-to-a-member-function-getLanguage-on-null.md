---
tags: Frontend, getLanguage, Whoops
---

28.02.2023

# Frontend: Call to a member function getLanguage() on null


## Frage

Is bei dem letzen/letzteren Redaxo Updates was rausgeflogen?
Fehlermeldung bei Verwendung dieser Zeile im Frontend:
```rex::getUser()->getLanguage()```

rex::getUser() im FE geht nicht?

## Antwort

```php
// init user object
if(rex::isFrontend()) {
    rex_backend_login::createUser();
}
```

Mal davor reinhauen.

Man hat im FE den eingeloggten BE User nicht automatisch. Schon deshalb, weil es den ja u.U. gar nicht gibt (wenn keiner mit aktiver Session da ist). Wenn der doch da ist, dann auch nur, weil irgend ein anderes AddOn den Code da oben vorher schon ausgeführt hat und dir den BE User damit vorbereitet.

Es wurden irgendwann um 5.12 herum (nur aus dem Gedächtnis) Änderungen gemacht.