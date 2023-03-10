---
tags: Geolocation, curl_exec
---

10.03.2023

# Geolocation: Error Call to undefined function curl_exec()


## Frage

Ich hab hier noch Geolocation 1 im Einsatz.
Dann neulich auf PHP 8.1 umgestellt direkt nach der Migration auf den Live-Server. Das wirft folgenden Fehler:

```php
Error Call to undefined function curl_exec() | redaxo/src/addons/geolocation/lib/yform/dataset/layer.php | 385
```

## Antwort

- schau mal in die phpinfo, ob die funktion vielleicht in `disable_functions` enthalten ist
- Soll/muss er Hoster gerade biegen.
