---
tags: Backend, Frontend, rex_url, rex_getUrl, structure-addon
---

01.03.2023

# Backend rex_url anstatt rex_getUrl


## Frage

mit der Funktion `rex_getUrl($id = null, $clang = null, array $params = [], $separator = '&amp;')` kann ich einen Link aufbauen.  In einem AddOn möchte ich eine Seite im Ordner page verlinken - aber diese PHP Datei hat ja keine ID, so dass ich wohl  `href="index.php?page=stiftung/projects/meineDatei`   nutzen muss , oder?

## Antwort

`rex_getUrl` kommt aus dem **structure addon** und ist nur für frontend-urls zu artikeln.

fürs backend gibt es `rex_url::backendPage`
