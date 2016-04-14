---
layout: post
title:  "Zwei Instanzen Ghost auf Uberspace"
date:   2014-08-11 
banner_image: ghost.png
categories: linux server blog
comments: true
---
Nachdem ich mich nun ein wenig mit Ghost beschäftigt habe, kam mir der Gedanke, wie bekomme ich einen zweiten Blog hier auf meinem [Uberspace](https://uberspace.de/) am Laufen.
Diverse Google Suchergebnisse halfen mir nicht wirklich bei der Lösungsfindung und dann mit ein wenig Hilfe von der [Ubernauten](https://twitter.com/ubernauten), war die Lösung doch so einfach. 

Nachfolgendes ToDo funktioniert nur in Verbindung mit einem [Uberspace](https://uberspace.de/). Habt ihr ein anderes System laufen, würde ich wieder zu Google greifen der im [Ghost Forum](https://ghost.org/forum/) nachfragen.

So und los geht´s.

Entgegen der vielen, meist in englisch verfassten, Beschreibungen zum Thema *More-Ghost/ Multiblog mit Ghost*, ist es auf einem Uberspace recht einfach einen zweiten, dritten usw. Blog zu erstellen. Nach Rücksprache mit den [Ubernauten](https://twitter.com/ubernauten) wird der zweite Blog in einem anderen Verzeichnis angelegt und bekommt einen eigenen Port. Zu guter Letzt wird er mittels eigenem Daemon gestartet und das war es schon.

Ich habe das ganze mittels folgender Befehle durchgeführt:

	[netbuk@hamal ~]$ curl -L https://ghost.org/zip/ghost-0.4.2.zip -o ghost-0.4.2.zip
	[netbuk@hamal ~]$ unzip ghost-0.4.2.zip -d ghost2 && cd ghost2 
	[netbuk@hamal ghost2~]$ npm install --production


Anschließend anpassen der **config.js** wie [hier  beschrieben](https://wiki.uberspace.de/cool:ghost) und die **.htaccess** erstellen (*!Achtung an den neuen Port denken!*).

Danach noch den Daemon einrichten, starten und Admin-Konto erstellen.

	[netbuk@hamal ghost2~]$ test -d ~/service || uberspace-setup-svscan
	[netbuk@hamal ghost2~]$ uberspace-setup-service ghost2 env NODE_ENV=production node ~/ghost2/index.js 2>&1
	[netbuk@hamal ghost2~]$ sed -i -e 's/exec/cd ~\/ghost2\/\nexec/' ~/etc/run-ghost/run
	[netbuk@hamal ghost2~]$ svc -u ~/service/ghost2 

Die Blogs laufen jeweils in einer eigenen Subdomain. Achtet beim Anlegen der Daemon auf die richtigen Ordner, hier Ghost2.