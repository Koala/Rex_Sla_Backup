---
tags: EP, ExtensionPoint
---

10.02.2023

# ExtensionPoint Parameter mitgeben


## Frage

Wie kann ich beim Aufruf eines Extensionpoints Parameter mitgeben?
``` php
rex_extension::register('SLICE_SHOW', array('myclass', 'myfunction'), rex_extension::LATE);
```


## Antwort

So gehts:
``` php
rex_extension::register('URL_PRE_SAVE', ['addon_url', 'rex_url_shortener'],rex_extension::LATE,['namespace'=>'event-id']);
```

Anderes Beispiel:
https://github.com/FriendsOfREDAXO/geolocation/blob/cb7a4139515de9df4ef479a385a10a7e5c022e69/lib/yform/dataset/Layer.php#L182-L188