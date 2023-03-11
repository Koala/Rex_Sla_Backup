---
tags: YFORM, Platzhalter
---

21.02.2023

# YFORM - Label deaktivieren?


## Frage

yform - label: gibts ne Möglichkeit die Label zu deaktivieren? Möchte nur Placeholder haben und wenn ich beim Label ‘’ nur Ausgebe, dann macht er mir dennoch ne leere Zeile

## Antwort

- Das regle ich immer im CSS.
- ... über CSS. Ohne es ausprobiert zu haben in Analogie zu den Bootstrap-Badges, die ja auch ausgeblendet sind wenn leer.  
``` css
.yform .form-group > label.control-label:empty { display:none }
```
- oder ein eigenes theme/template: [https://github.com/yakamara/redaxo_yform/blob/master/docs/07_formbuilder.md#objparams-zur-formular-optik](https://github.com/yakamara/redaxo_yform/blob/master/docs/07_formbuilder.md#objparams-zur-formular-optik)

## Hinweis

[https://joshuawinn.com/ux-input-placeholders-are-not-labels/](https://joshuawinn.com/ux-input-placeholders-are-not-labels/)

[https://www.nngroup.com/articles/form-design-placeholders/](https://www.nngroup.com/articles/form-design-placeholders/)

