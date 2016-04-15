---
title: Filezilla vs. OpenSSH (Uberspace)
---

> Dieser Artikel wurde aus dem Pagekit Blog übernommen!

Nachdem [Uberspace ein Versionsupdate für OpenSSH von 6.7 auf 6.8](https://blog.uberspace.de/kuck-mal-wer-da-hort-openssh-6-8/) vollzogen hatte, ging mittels Filezilla (v3.8) bei mir nichts mehr. Die verbindung wurde über Port 22 nicht mehr zugelassen. Die Ausweichmöglichkeit über den angegebenen Port 4022 hat zwar funktioniert, ist aber nur für Testzweck temporär nutzbar. 
Nach einem kurzen Informationsaustausch, bekam ich von den Ubernauten den Hinweis, auf eine neuere Filezilla Version zu aktualisieren. Damit soll das Problem behoben sein.

Also ran an den Speck und auf der Projektseite schnell nachgeschaut, wo die Version gerade steht. 3.10.3 hat sie im Moment in der Stable. 
Dann aber kamen bereits die ersten Zweifel hoch, denn eigentlich habe ich mein System (Linux Mint 17.1 Rebecca Mate) immer aktuell. Es kann doch dann gar nicht sein, das Filezilla noch mit einer älteren Version vorliegt. Nun ja, wo schaut man schnell nach um sich Gewissheit zu verschaffen? In der Anwendungsverwaltung. 

Tatsächlich wurde ich nicht enttäuscht. Die Version 3.8 stand immer noch als Höchstbieter zur Verfügung. Dann lag es erst einmal nicht an mir, sondern an der Repository, was aber mein Problem immer noch nicht löste.
Auf der Projektseite gab es zwar ein Update in Form einer tar.gz, welches sich aber nicht installieren lies (vielleicht habe ich mich auch zu doof angestellt). Aber wofür gibt es denn Suchmaschinen.
Im Launchpad fand ich dann eine interessante [PPA von Nate Muench](https://launchpad.net/~n-muench/+archive/ubuntu/programs-ppa). Diese hinzugefügt und ab ging die Post.

Nun ja, nicht ganz. Denn die wesentlichen Pakete für 3.10.3 wurden zurückgehalten. Verdammt.

Also noch ein `dist-upgrade` hinter her gejagt und dann war es endlich soweit. Version 3.10.3 war auf meiner Maschine und verband sich fröhlich mit meinem Uberspace.