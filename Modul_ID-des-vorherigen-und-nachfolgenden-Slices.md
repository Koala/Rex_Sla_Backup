---
tags:
  - Modul_ID
  - REX_SLICE_ID
---

20.10.2023

# Modul_ID des vorherigen und nachfolgenden Slices


## Frage

wie bekomme ich heraus welches Modul_ID das vorherige und das nächste Slice hat …?

## Antwort

```php
$slice_id = "REX_SLICE_ID";
if($slice = rex_article_slice::getArticleSliceById($slice_id))
{
	if($prev = $slice->getPreviousSlice())
	{
		dump($prev->getModuleId());
	}
	if($next = $slice->getNextSlice())
	{
		dump($next->getModuleId());
	}
}
```
