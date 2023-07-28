---
tags: YForm-Addon, URL-Addon, Neuigkeiten, News, Datenbank
---

28.07.2023

# Teaser / Artikelliste


## Frage

Wie kann ein Teaser (Kurzansicht) für Artikel ausgegeben werden? Mit WeiterleitungAusgabe zu den jeweiligen Artikeln?


## Antwort

Es gibt 2 Möglichkeiten.

### Möglichkeit 1 - nur Modul

Mittels eines Modules.

Eine Kategorie in der alle Artikel reinkommen. Der Startartikel dient als Teaserausgabe.
Die weiteren Artikel in dieser Kategorie sind dann die Artikel mit den Neuigkeiten (oder was auch immer).


#### Modul *Artikelliste*

**Input**
Bleibt leer.

**Output**
```php
$articles = rex_category::getCurrent()->getArticles();

if (count($articles)) {
  $output[] = '<ul>';
    foreach ($articles as $article) {
      if ($article->getValue('status') != 0) { // Offline
        if ($article instanceof rex_article && !$article->isStartArticle()) {
            $output[] = '<li><a href="'.rex_geturl($article->getValue('id'), rex_clang::getCurrentId()).'">'.$article->getValue('name').'</a></li>';
        }
      }
    }
  $output[] = '</ul>';
}


if(!rex::isBackend()) {
  echo implode('',$output);
} else {
  echo '
  <div id="artikelliste" class="bereichswrapper">
    <div class="form-horizontal output">
     <h2>Artikelliste</h2>
       <div class="form-group">
         <div class="col-sm-12 control-label">
           <p>Die Artikelliste wird im Frontend ausgegeben.</p>
         </div>
       </div>
    </div>
  </div>
';
```





### Möglichkeit 2 - Modul + Addons

Kombination aus den Addons YForm, URL und einem Modul.
Die Artikel werden hier im Addon YForm verwaltet. Das URL-Addon übernimmt die Ausgabe in Verbindung mit einem Modul.

Festhalten, die Erklärung ist etwas länger ... 


Importiere mal zuerst dieses Tableset in yForm. Das folgende in eine Datei abspeichern für den Import. z.B. MeinImport.json
Also auf yForm klicken und dann ist da oben ein Button "Tableset importieren" - dort die Datei hochladen.
```json
{"aktuelles":{"table":{"status":1,"table_name":"aktuelles","name":"Aktuelles","description":"","list_amount":50,"list_sortfield":"id","list_sortorder":"ASC","search":0,"hidden":0,"export":0,"import":0,"mass_deletion":0,"mass_edit":0,"schema_overwrite":1,"history":0},"fields":[{"table_name":"aktuelles","prio":1,"type_id":"value","type_name":"text","db_type":"varchar(191)","list_hidden":0,"search":0,"name":"headline","label":"\u00dcberschrift","not_required":"","no_db":"0"},{"table_name":"aktuelles","prio":2,"type_id":"value","type_name":"textarea","db_type":"text","list_hidden":0,"search":0,"name":"text","label":"Text","not_required":"","no_db":"0"}]}}
```


Und dann machste noch ein neues Modul und haust das hier mal in den Output (Input leer lassen)  

#### Modul *Artikelliste*

**Input**
Bleibt leer.

**Output**
```php
<?php
use Url\Url;

$manager = Url::resolveCurrent();

if ($manager) {
    $aktuelles = rex_yform_manager_table::get('aktuelles')->query()->findId($manager->getDatasetId());
    if ($aktuelles) {
        dump($aktuelles);  
        ### => Die Ausgabe in dieser Schleife ist quasi deine "Detailansicht"
    }
} else {
### => in der Else-Schleife ist die Ausgabe sozusagen die Teaser-Ansicht, wo alle vorhandenen Datensätze mit Link ausgegeben werden
	$aktuelles = rex_yform_manager_table::get('aktuelles')->query()->find();
    if (count($aktuelles)) {
        foreach ($aktuelles as $aktuell) {
            echo '<a href="' . rex_getUrl('', '', ['aktuell-id' => $aktuell->getId()]) . '">' . $aktuell->getValue('headline') . '</a>';
        }
    }
}
?>
```

In der Struktur eine Kategorie oder einen Artikel "Aktuelles" erstellen und dort das Modul `Artikelliste` einstellen.

Danach gehst du runter in das AddOn URL und legst ein neues Profil an. Als Schlüssel (1. Inputfeld) nimmst du `aktuell-id` und wählst die SQL-Tabelle `aktuelles` aus. Natürlich auch den Artikel bestimmen, wo das ganze laufen soll. 
Den Rest kannst du dann auf Standard-Werten lassen, außer evtl. im Bereich "URL" - da wählste mal `headline` aus.

Das müsste es schon gewesen sein. Dann mal den Artikel im Frontend anschauen und gucken was passiert.  

#### Hinweis
Diese Lösungen berücksichtigen noch keine Seitenaufteilung (Pagenierung). Es werden einfach alle Artikel ausgegeben.

