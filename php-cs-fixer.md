FOR-Tricks: https://friendsofredaxo.github.io/tricks/development/editor-vscode

Das ist teilweise veraltet. Schau auch mal hier rein.Bei mir auf dem Mac hab ich es am Ende so installiert (zumindest sagen das meine Notizen):https://marketplace.visualstudio.com/items?itemName=junstyle.php-cs-fixer
https://github.com/redaxo/php-cs-fixer-config

Für den einheitlichen Look in Redaxo-Projekten gibt es Redaxo-Regeln, die separat eingebunden werden müssen. Das passiert in diesen Schritten:


1. Installation mit Composer im Terminal
2. composer require --dev redaxo/php-cs-fixer-config
3. Die Dateien liegen dann im Verzeichnis ~/vendor/redaxo/php-cs-fixer-config
4. Im Konfigurationsverzeichnis für VSCode wird eine zusätzliche php-Datei ~/.vscode/.php-cs-fixer.php platziert, die den Auruf inkl. Dependency durchführt: 

include getenv('HOME').'/vendor/redaxo/php-cs-fixer-config/src/Config.php';
return include getenv('HOME').'/vendor/redaxo/php-cs-fixer-config/.php-cs-fixer.dist.php';

Der PHP CS Fixer wird in den settings so konfiguriert, dass die Redaxo-Einstellungen nachgelagert zu Einstellungen in den jeweiligen VSC-Workspaces geladen werden:

``` 
{
    "php-cs-fixer.config": ".php-cs-fixer.php;.php-cs-fixer.dist.php;~/.vscode/.php-cs-fixer.php",
    "[php]": {
        "editor.defaultFormatter": "junstyle.php-cs-fixer"
   },
}
```

