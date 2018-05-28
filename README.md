# Magento 2 German Language Pack

Deutsches Sprachpaket für Magento 2 Community Edition

Die Übersetzung wurde nach eigenem Ermessen vorgenommen. Die Übersetzung ist komplett, d.h. alle Sprachausgaben von Magento 2 wurden vom Englischen ins Deutsche übersetzt.

# Installation
 - Alle Dateien nach `/app/i18n/wilkesystems/de_DE/` kopieren

Aus dem Magento-Root-Verzeichnis folgende Befehle aufrufen:
```bash
rm pub/static/frontend/Magento/luma/de_DE/js-translation.json
php bin/magento setup:static-content:deploy de_DE -f
php bin/magento setup:upgrade
rm -rf var/di
php bin/magento setup:di:compile
```

# Installation mit Composer
```bash
composer require wilkesystems/magento2-german-language:dev-master
rm pub/static/frontend/Magento/luma/de_DE/js-translation.json
php bin/magento setup:static-content:deploy de_DE
```

# Add new phrases

To translate new phrases follow these steps:

### Get phrases from Magento

Run this in your Magento 2 installation:

```bash
php bin/magento i18n:collect-phrases -m > phrases.csv
```

### Compare phrases with old translation file

Copy the `phrases.csv` into this repository and run:

```bash
php check_new.php
```

This will output a new file `de_DE_new.csv` which only contains the
phrases that are not yet translated in `de_DE.csv`.
