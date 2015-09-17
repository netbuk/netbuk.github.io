---
layout: post
title:  "Ghost update v0.5.0"
date:   2014-08-12 
banner_image: ghost.png
categories: linux server blog
comments: true
---
Gestern wurde die Version 0.5.0 released. 
Neuerungen sind unter anderem Multi-User-Support, d.h. Ghost unterstützt nun mehrere Benutzer auf einem Blog. Dies ist für Communitys, Organisationen und Unternehmen interessant. 

Alle weiteren Neuerungen sind nicht unbedingt sichtbar, da sie sich mehr *unter der Haube* befinden. Dies hat Ghost-Gründer, John O'Nolan, dazu gezwitschert:
>Ghost 0.5 is kind of like a Boing 787 Dreamliner. Took ages to make + no big visual difference, but holy shit everything is so much better.
— *John O'Nolan (@JohnONolan) [6. August 2014](https://twitter.com/JohnONolan/statuses/496985179626684417)*

Hier eine kleine Übersicht zu den Neuerungen in der v0.5.0:

* **Multi-User:** Ein Blog - mehrere User - verschiedene user roles
* **Home**: Mit Einführung der home.hbs kann man seine Home-Seite komplett im Style ändern, ohne Einfluß auf die nachfolgenden Seite zu nehmen. Ist die home.hbs in euerem Theme-Baum nicht vorhanden, wird automatisch auf die index.hbs zurückgegriffen.
* **Autoren**: Mit Einführung der oben erwähnten Multi-User-Funktion haben auch Autorenseiten einzug gehalten. Unter *deinedomain.de/user/username* könnt ihr die jeweilige Autorenseite aufrufen. Dort werden euch die geschriebenen Posts des Users zusammengefasst angezeigt und es gibt auch einen individuellen RSS-Feed.
Bearbeiten könnt ihr dies unter author.hbs.
* **Theme Casper**: Das mit Ghost standardmäßig ausgelieferte Theme hat jetzt den v1.0 status erreicht. Es hat eine bessere mobile Funktionalität und kann mit den neuen Profilseiten umgehen.

####Jetzt kommen wir in den Bereich *unter der Haube* ;)

* **ember.js**: Bereits im Februar hatten die Entwickler sich dazu entschloßen den Adminbereich auf Basis von ember.js zu erstellen.

>	Was bedeutet das? 
Ghost ist jetzt ein voll ausgestattetes clientseitige JavaScript-Anwendung. Alles, was Sie im Browser tun geschieht in Echtzeit. Wir sind nun in der Lage Benutzerschnittstellenkomponenten zu entwickeln, die so aussehen und funktional reagieren, wie Sie es von einem Desktop (oder mobile) Betriebssystem erwarten.

* **Public JSON API**: Ghost hat eine öffentliche JSON-Schnittstelle spendiert bekommen. Damit lassen sich jetzt auch Apps für iOS, Android, Desktop and the hole web auf Grundlage der Ghost Blogging Plattform entwickeln.

... und so weiter. Ein komplettes Changelog findet ihr auf [GitHub](https://gist.github.com/ErisDS/b7aa1a6e954f415cbb5b).

Lange Rede kurz Sinn, jetzt mal zum Update selbst.
Wenn ihr Ghost pro Nutzer seit, dann wird euer Blog automatisch dem Update unterzogen.
Für Entwickler und selbst gehostet Ghost-Blogs steht alles in der [Upgrade Documentation](http://support.ghost.org/how-to-upgrade/) von Ghost.

Wer einen Uberspace nutzt kann auch auf das Script der Ubernauten zurück greifen. Ihr müsst nur die Versionsnummer von 0.4.2 -> 0.5.0 im Script ändern.

####ToDo
Script herunterladen

	wget https://raw.github.com/dictvm/shellscripts/master/update-ghost.sh
Mit einem Editor (vi oder extern) öffnen und die Zeile 7 bearbeiten, speichern & schließen

	5 ...
    6 # set the current ghost-version here
    7 VERSION='0.5.0'
    8 ...
Anschließend das Script in den Ghost -Ordner verschieben, falls noch nicht geschehen, und ausführbar machen

	[netbuk@hamal ghost]$ chmod +x update-ghost.sh

Jetzt könnt ihr das Script starten, euch zurück lehnen und noch ein paar Momenten startet euer Ghost mit der neuen Version *(sofern alles richtig lief; Garantie/ Gewähr gebe ich keine, da das Script 1. nicht von mir ist und 2. sich das Script in einer Alpha-Version befindet)*

	[netbuk@hamal ghost]$ ./update-ghost.sh
    
###!Achtung
Solltet ihr mehrere Ghost-Blogs auf einem Server laufen haben, ist das Update mittels Script in der o.a. Variante nur für den Blog in dem Ordner *Ghost* möglich. Andere Verzeichnisse werden mit dem Script nicht abgedeckt. D.h. wenn ihr z.B. einen zweiten Blog unter Ghost2 laufen habt, müsst ihr entweder das Script umschreiben oder manuell das Update vollziehen (was nicht besonders schwierig ist).