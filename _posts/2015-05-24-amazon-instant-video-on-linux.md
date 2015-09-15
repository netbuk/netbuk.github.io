---
layout: post
title:  "amazon instand video on linux"
date:   2015-05-24 
comments: true
---

Amazon Instant Video ist einer von vielen Streaming Services und alle haben etwas gemeinsam, unter Linux ist dies nicht so einfach wie unter den anderen OS.
Für die Nutzung ist Silverlight, ein Plugin von Microsoft, notwendig. Um dies unter Linux lauffähig zu bekommen, nutzt man [Pipelight](http://pipelight.net).
Die nachfolgende Beschreibung habe ich von [Heise](http://www.heise.de/open/artikel/Online-Videotheken-mit-Linux-nutzen-2157416.html). Sie basiert auf die Installation unter Ubuntu.

1.) Repository hinzufügen

      sudo add-apt-repository ppa:pipelight/stable
      sudo apt-get update
      sudo apt-get install --install-recommends pipelight-multi
      sudo pipelight-plugin --update

2.) Silverlight Plugin installieren

    sudo pipelight-plugin --enable silverlight

Pipelight wird beim ersten/ nächsten Browser-Start konfiguriert. Zur Kontrolle gibt man in die Firefox-Adresszeile *about:plugins* oder in die Chrome-Adresszeile *chrome://plugins* ein. Das Plugin sollte aufgelistet sein.

3.) User Agent Switchers (Chrome/ Firefox)

Für Firefox sollte dieses Plugin verwendet werden: https://addons.mozilla.org/de/firefox/addon/user-agent-overrider
In der Auswahlliste den Eintrag "Windows / Firefox 26" auswählen.

Für Chrome sollte dieses Plugin verwendet werden: https://chrome.google.com/webstore/detail/user-agent-switcher-for-c/djflhoibgkdhkhhcedjiklpkjnoahfmg
In der Auswahlliste den Eintrag "Firefox/Windows Firefox 15" auswählen.

Ob User Agent und Silverlight-Plugin funktionieren, kann man mittles der [Pipelight-Diagnostic-Seite](http://fds-team.de/pipelight/) testen.  

So weit so gut. Dieses Vorgehen funktioniert bei den meisten, nur leider nicht bei mir. Nach langer Recherche habe ich dann [folgendes Vorgehen gefunden](http://askubuntu.com/questions/515879/amazon-instant-video-14-04-1-lts).

1.) Installation Flash-Plugin

    sudo add-apt-repository ppa:mjblenner/ppa-hal
    sudo apt-get update 
    sudo apt-get install hal

2.) Anschließend im Terminal folgende Zeilen (jede einzeln nach einander) eingeben

    sudo mkdir /etc/hal/fdi/preprobe
    sudo add-apt-repository ppa:pipelight/stable
    sudo apt-get update
    sudo apt-get install --install-recommends pipelight-multi
    sudo pipelight-plugin --update
    sudo mkdir /etc/hal/fdi/information

    /usr/sbin/hald --daemon=yes --verbose=yes

    rm -rf ~/.adobe

danach folgendes ausführen

    sudo apt-get remove --purge hal

Jetzt das Flash-Plugin aktivieren

    sudo pipelight-plugin --enable flash

Jetzt den Browser starten und wieder beenden.
Zu guter Letzt das Silverlight-Plugin aktivieren.

    sudo pipelight-plugin --enable silverlight

Dieses Vorgehen hat bei mir funktioniert, aber auch nur mit Firefox. Unter Chrome bringe ich kein Video zum Laufen.