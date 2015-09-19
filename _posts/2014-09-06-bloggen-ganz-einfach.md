---
layout: post
title:  "Bloggen, ganz einfach"
date:   2014-09-06 
banner_image: evernote.jpg
categories: blog evernote
comments: true
---
Für einen Fan der Blogsoftware [Ghost](http://ghost.io) eigentlich ein Tabu, aber im Sinne des freien Internets wieder richtig.
Wer schon immer mal einen einfachen Weg gesucht hat, seine Gedanken, Meinung, Stimme usw dem World Wide Web mitzuteilen, hat sein Ziel mit [Postach.io](http://Postach.io) gefunden. Mittels einfachen Mitteln, nämlich [Evernote](http://evernote.com) und/oder [Dropbox](http://dropbox.com). Postach.io nimmt die Notizen/ Dateien und bastelt daraus einen recht ansehnlichen Blog(-eintrag).
#### Nur wie funktioniert das? ####
Nachdem ihr euch bei Postach.io angemeldet und ihr eine Site erstellt habt (der Freeaccount lässt nur eine Site zu), verbindet ihr unter *Sources* Evernote und Dropbox mit eurem Postach.io. Natürlich setzt das voraus, dass ihr einen Dropbox und/ oder Evernote Account habt. Die anderen Konfigurationsmöglichkeiten wie Sharing, RSS, Kommentare mittels Disqus werde ich mal auslassen, da dies nicht die Welt ist. Das Tolle an diesem, ich nenne es mal System ist, das man für diese Art der Webpräsentation nichts ausgeben muss. Evernote, Dropbox und Postach können kostenlos verwendet werden (natürlich mit ein paar Einbußen, was aber nicht weiter stört).

Kommen wir zuerst zu Evernote. Nach dem Verbinden mit Evernote wird autoamtisch ein Notzblock mit eurer Postoch.io Domain erstellt. In diesem Notizbuch erstellt ihr nun eure Notizen/ Beiträge, die ihr veröffentlichen wollt. Sobald ihr eine Notiz fertig habt und diese veröffentlichen möchtet, fügt ihr nur **published** unter den Tags ein und nach dem Synchronisieren ist auch schon eure Notizen unter der Postach.io Domain zu lesen.
Alle Funktionen der Werzeugleiste könnt ihr ganz normal verwenden. Formatierungen und auch Bilder werden eins zu eins übernommen.

Bei Dropbox ist das vorgehen ähnlich. Nach dem Verbinden erstellt Postach.io in eurer Dropbox eine Ordnerstruktur.

    Apps > Postach.io > eurebezeichnung.postach.io
Es kann sein, dass der letzte Ordner mit der Domainbezeichnung nicht automatisch erstellt wird (so bei mir geschehen). Aber kein Thema, einfach selbst erstellen und fertig. Jetzt könnt ihr eure Artikel in Form von .html oder .md Dateien dort ablegen und sie werden automatisch unter eurer Postach.io Domain gezeigt.

Es gibt aber einen gravierenden unterschied zu Evernote. Unter Evernote könnt ihr die Werkzeuleiste zum Formatieren eurer Beiträge zur Hilfe nehmen. Bei Dropbox sieht das etwas anders aus. Hier müsst ihr euch entweder mit HTML-Dateien und ihrer Auszeichnungssprache auskennen oder zum Erstellen von .md Dateien einen Markdown-Editor zur Hand nehmen. Egal für welche Dateiart ihr euch entscheidet, damit die Dateien Beiträge durch Postach.io veröffentlicht werden, müsst ihr in die Datei Meta-Angaben machen. Diese können so aussehen.
####HTML####
	<html>
	<head>
	<title>My Awesome HTML Blog Post</title>
	<meta name="date" content="2014-01-01" /><!-- YYYY-MM-DD -->
	<meta name="type" content="post" /><!-- use "post" or "page" -->
	<meta name="tags" content="food, tech" /><!-- comma separated -->
	</head>
	<body>
	...
####Markdown####
	title: My First Post
	date: 2014-04-15
	tags: life, photos
	type: post

	Here beginns my Content!
Wie das umgesetzt aussieht, könnt ihr euch unter meiner Postach.io Domain anschauen ([http://netbuk.postach.io](http://netbuk.postach.io)). Nicht erschrecken das ihr auf [http://blog.netbuk.org](http://blog.netbuk.org "blog.netbuk.org") landet, da ich eine Subdomain auf mein Postach.io gesetzt habe (ja auch eigene Domains könnt ihr nutzen). Der erste Artikel mit dem Logo von State of decay wurde unter Evernote erstellt. Der Zweite ist mit Dropbox und einer .md Datei erstellt worden. Als Editor nutze ich unter Windows das [Markdown Pad 2](http://markdownpad.com).

#### Wo liegt jetzt der Vorteil gegenüber einem Wordpress Blog, Tumblr oder anderen Angeboten? ####

Nun ja, kostenlos sind die meisten Bloganbieter. Aber ihr müsst immer den Browser zur Hilfe nehmen und eine Onlineverbindung haben. Mit den Methoden Evernote und Dropbox könnt ihr eure Artikel aber ganz gemütlich offline schreiben und sobald ihr Internetzugriff habt synchroniseren. Dabei braucht ihr nicht wie zum Beispiel bei Wordpress, den Administrationsbereich laden, was mit unter lange dauern kann und zeitaufwendig ist. 

Wenn ihr auch mobil Artikel verfassen wollt, benötigt ihr in der Regel eine speziellle App des jeweiligen Bloganbieters. Evernote und Dropbox hat man normalerweiseauf seinem Mobilgerät, egal ob Android, Windows oder iOS. Dadurch hat man auch die Möglichkeit, zu jeder Zeit plattform unabhängig Artikel zu schreiben und zu veröffentlichen. Alleine das macht die Postach.io Sache sehr interessant.

Davon mal abgesehen schafft Markdown eine reinen *Code*. Diverse Anbieter fügen den erstellten Artikelen meist noch jede Menge andere Codeschnipsel hinzu, die niemand braucht. Mit MD bleibt alles so, wie ihr es erstellt habt.

**Kommentare könnt ihr hier verfassen -> [Board: Bloggen, ganz einfach](https://board.netbuk.dk/showthread.php?tid=8)**