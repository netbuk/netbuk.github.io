---
layout: post
title:  "kernel-update crashes virtualbox"
date:   2015-02-01
banner_image: virtualbox.png
categories: linux ubuntu virtualbox
comments: true
---
####Schock-Moment!####
Nach einem Kernel-Update heute morgen ließ sich keine VM mehr in Virtualbox starten. Grund dieses Problems lag in der alten Version von Virtualbox, die nicht mit dem Kernel arbeiten kann.
Deinstallation uvm. brachte keine Hilfe.
Durch Zufall habe ich dann diese [tolle Anleitung](http://axebase.net/blog/2013/02/28/virtualbox-repository-in-ubuntu-hinzufuegen/) gefunden, mit der man die Virtualbox Repository in Ubuntu hinzufügt und damit up-to-date ist.
Und wie ein Wunder, alles funktioniert wieder wunderbar.

*Link: [axebase.net](http://axebase.net/blog/2013/02/28/virtualbox-repository-in-ubuntu-hinzufuegen/)*