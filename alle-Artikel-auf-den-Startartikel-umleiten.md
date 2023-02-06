--- 
Tags: 
--- 
02.02.2023

# alle Artikel auf den Startartikel umleiten


## Frage
Wie kann ich am einfachsten alle Artikel auf den Startartikel umleiten (Seitenschließung...)


## Antwort

das ins template?

``` 
if(rex_article::getCurrentId() != rex_article::getSiteStartArticleId()) {
	header(‚Location: https://abc.de‘);
exit;
}
``` 

Aus SEO Sicht lieber keine 301 machen, sondern 404 ausgeben.
