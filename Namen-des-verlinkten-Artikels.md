---
tags: 
---

10.07.2023

# Namen des verlinkten Artikels


## Frage

wie bekomme ich den namen des verlinkten artikels

## Antwort

```php
$article = rex_article::get($value['link_intern']);
if($article) {
       echo $article->getName();
}
```
