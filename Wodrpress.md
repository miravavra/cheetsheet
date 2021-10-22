# Zabezpečení Wordpressu

## Nutné zajistit

### Wordfence plugin
- limit počtu přihlášení

### Uživatelské jméno do administrace
Nepoužívat jméno "Admin".

### Zakázat zjišťování uživatelských jmen podle ID autora
Přidáním do souboru **.htaccess**, který se nachází v kořenové složce webu.
```
# blokace skenovani autoru
RewriteEngine On
RewriteBase /
RewriteCond %{QUERY_STRING} (author=\d+) [NC]
RewriteRule .* - [F]
# ---
```

### Zamezit přímý přístup k souboru wp-config.php
Soubor obsahuje informace pro přihlášení k databázi.
Přidáním do souboru **.htaccess**, který se nachází v kořenové složce webu.
```
# Blokace pristupu k WP-config
order allow,deny
deny from all
# --
```
Ušetří se tím také výkon webového serveru, neboť se v případě přístupu robotů na tento soubor nebude vůbec zpracovávat.

### Skryjte verzi WordPressu
Ve výchozím stavu wordpressový web prozradí v meta tagu **generator** číslo verze Wordpressu.
Přidat tento řádek na konec souboru **functions.php**, který se nachází ve složce s šablonou. Ta se nacházií ve složce `/wp-content/themes/`.

`add_filter( 'the_generator', '__return_null' )`

## Na zvážení

### Vypnutí editoru šablon a pluginů
Zapsat do **wp-config.php**.

`define( 'DISALLOW_FILE_MODS', true );`
