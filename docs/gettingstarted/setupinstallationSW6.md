---
pageClass: theguide
---

# Kickstart mit Shopware 6

## Backend

Für Shopware 6 als Backend bietet hubble eine direkt nutzbare Integration.

Shopware's [Sales Channel](https://docs.shopware.com/en/shopware-platform-dev-en/sales-channel-api) und [Store API](https://docs.shopware.com/en/shopware-platform-dev-en/store-api-guide)'s werden direkt über das __`@hubblecommerce`__ Modul angesprochen.

## Überblick

Das Repository besteht aus einer vorkonfigurierten [NuxtJS](https://nuxtjs.org/) Version,
die hubble als NuxtJS Modul im __`~/modules/`__ Ordner enthält:
Das [@hubblecommerce](https://github.com/hubblecommerce/hubble-frontend-pwa/tree/master/modules/%40hubblecommerce)
Modul.

__Hinweis:__ Die folgenden Installationsanweisungen wurden für MacOS und Linux Umgebungen getestet.
 

## Requirements

* [Node.js](https://nodejs.org/en/) \(&gt;=10.20.1\) - enthält __npm__
* __npm__ \(&gt;=6.14.4\)
* [Shopware](https://docs.shopware.com/en/shopware-platform-dev-en/system-guide/system-installation-guides)
* [Shopware 6 API Plugin](https://github.com/hubblecommerce/shopware6-api-plugin)
* [Shopware 6 Payone Plugin](https://store.shopware.com/payon69044615910f/payone-payment-fuer-shopware-6.html)


## Installation und Konfiguration der hubble PWA

Der Code der hubble PWA befindet sich auf GitHub und kann über das Terminal heruntergeladen werden:

``` bash
git clone git@github.com:hubblecommerce/hubble-frontend-pwa.git
cd hubble-frontend-pwa
cp .env_example .env
npm install 
```

Um die Entwicklung zu beginnen wird eine __`~/.env`__ benötigt, in die Credentials wie API Keys und Auth Token
aus den Admin Bereichen der jeweiligen Services einzutragen sind.
Im Projekt existiert dafür die __`~/.env_example`__ als Referenz für mögliche Einträge. Außerdem enthält die Dokumentation 
den Abschnitt [Konfiguration](../pwa/configuration.md) mit einer Beschreibung zur korrekten
und sicheren Verwendung der __`~/.env`__.

Im Zusammenhang mit Shopware sind mindestens folgende Einträge notwendig:

```dotenv
API_TYPE          = 'sw'
API_SW_ACCESS_KEY = 'ENTER_YOUR_ACCESS_KEY_HERE'
API_BASE_URL      = 'http://shopware.local'
```
Dabei ist zu beachten, dass der __`API_SW_ACCESS_KEY`__ für den Storefront Verkaufskanal eingetragen wird und __nicht__ für den
Headless Verkaufskanal, denn die Headless Variante liefert zur Zeit keine SEO URLs.

![Sales Channel Access](../pwa/saleschannelaccess.png) 

## Starten der hubble PWA im Entwicklungsmodus
``` bash
npm run dev
```
Das hubble Frontend ist nun unter __`http://localhost:3336/`__ einsehbar.


## Starten der hubble PWA im Production Modus
``` bash
npm run build
npm run start
```