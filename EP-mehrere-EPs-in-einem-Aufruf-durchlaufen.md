---
tags: EP, Extensionpoint
---

22.02.2023

# Kann ich mehrere EPs in einem Aufruf durchlaufen?

## Frage

Kann ich mehrere EPs in einem Aufruf durchlaufen?

## Antwort

- als Array
- z.B.: ```rex_extension::register(['YFORM_DATA_ADDED', 'YFORM_DATA_UPDATED'], function(rex_extension_point $ep){```
- 
