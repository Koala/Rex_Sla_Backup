--- 
Tags: 
--- 
03.01.2022

# rex_form MySQL Abfrage Datensätze mit bestimmten Wert auslesen


## Frage
rex_form: Warum werden die Werte von Checkboxen und Multiselectfeldern in pipeseparierten Listen und nicht in kommaseparierten Listen gespeichert und wie bekomme ich per MySql Abfrage die Datensätze mit einem bestimmten Wert in der Pipe? 


## Antwort
FIND_IN_SET('x', replace(checkboxes, '|', ','))

