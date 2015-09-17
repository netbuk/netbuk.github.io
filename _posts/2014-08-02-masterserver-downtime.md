---
layout: post
title:  "Masterserver downtime"
date:   2014-08-02 
comments: true
---

Ja, es gibt noch Tactical Ops und auch einige Server. Wer in den letzten Tagen versucht hat einen Server in seiner Übersicht (Internet Games) zu finden, dachte schon an das entgültige Aus für TO AoT. Aber diese Stimmen können leiser werden, nur der Master Server **master0.gamespy.com** hat sich verabschiedet.

Damit ihr wie gewohnt die Serverübersicht durchstöbern könnt, müsst ihr nur ein paar Kleinigekteiten ändern. Dank geht an die Community, die hier schnell eine Lösung gefunden hat (siehe [ESE-Protect Forum](http://ese-protect.de/homepage/forums.php?m=posts&p=32543#32543)).

Um das Handling etwas einfacher zu gestalten habe ich beide Lösungen in eine zusammengefasst. Aufgrund der etwas verworrenen Darstellung findet ihr die wesentlichen Punkte auch unter meinem [Etherpad](http://pad.netbuk.dk/p/TO-Master-Server) wieder.


Zuerst die Änderungen in der **tacticalops.ini** (Systemordner):

####[UBrowser.UBrowserMainClientWindow]

	LANTabName=UBrowserLAN
	ServerListNames[0]=UBrowserLAN
	ServerListNames[1]=UBrowserAll
	ServerListNames[2]=TOServers
	ServerListNames[3]=None
	...
	bKeepMasterServer=True
	LANTabName=UBrowserLAN
	ServerListNames[0]=UBrowserLAN
	ServerListNames[1]=UBrowserAll`

####[UBrowserAll]

	ListFactories[0]=UBrowser.UBrowserGSpyFact,MasterServerAddress=unreal.epicgames.com,MasterServerTCPPort=28900,Region=0,GameName=ut
	ListFactories[1]=UBrowser.UBrowserGSpyFact,MasterServerAddress=master0.gamespy.com,MasterServerTCPPort=28900,Region=0,GameName=ut
	ListFactories[2]=UBrowser.UBrowserGSpyFact,MasterServerAddress=gsm.qtracker.com,MasterServerTCPPort=28900,Region=0,GameName=ut
	ListFactories[3]=UBrowser.UBrowserGSpyFact,MasterServerAddress=master.333networks.com,MasterServerTCPPort=28900,Region=0,GameName=ut
	bHidden=False
	bFallbackFactories=False

Nachfolgender Block Ändern oder Ergänzen falls nicht vorhanden.

####[TOServers]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=TO350,bCompatibleServersOnly=True

Folgende Blöcke sollen auch überschrieben werden, sind aber m.E. identisch.

####[UBrowserUT]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,bCompatibleServersOnly=True

####[UBrowserLAN]
	
    ListFactories[0]=UBrowser.UBrowserLocalFact,BeaconProduct=ut
	URLAppend=?LAN
	AutoRefreshTime=10
	bNoAutoSort=True

####[UBrowserPopulated]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,MinPlayers=1,bCompatibleServersOnly=True

####[UBrowserDeathmatch]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=DeathMatchPlus,bCompatibleServersOnly=True

####[UBrowserTeamGames]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=TeamGamePlus,bCompatibleServersOnly=True

####[UBrowserCTF]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=CTFGame,bCompatibleServersOnly=True

####[UBrowserDOM]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=Domination,bCompatibleServersOnly=True

####[UBrowserAS]
	
    ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=Assault,bCompatibleServersOnly=True

####[UBrowserLMS]

	ListFactories[0]=UBrowser.UBrowserSubsetFact,SupersetTag=UBrowserAll,GameType=LastManStanding,bCompatibleServersOnly=True


In der UBrowser.int folgendes ändern:
    
####[ServerListTitles]

	UBrowserUT=UT Servers
    UBrowserLAN=LAN Servers
    UBrowserPopulated=Populated Servers
    UBrowserAll=All Servers
    TOServers=TO Server 3.5

Ergebnis und Siegerehrung sind dann zwei neue Schaltflächen für alle Server (versionsunabhängig) und für v3.5.
![Masterserver_down](http://media.netbuk.de/netbuk/to_masterserver.jpg)