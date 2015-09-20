---
layout: post
title:  "Conky startet nicht nach großem Update (Arch Linux)"
date:   2015-09-20 
banner_image: arch.png
categories: linux os arch update
comments: true
---
Nach dem großen Update Tag am Freitag wollte Conky nicht mehr starten. Manuell über Terminal ausgeführt, bekam ich immer folgende Meldung angezeigt
{% highlight sh %}
	conky: error while loading shared libraries: libncursesw.so.5: cannot open shared object file ...
{% endhighlight %}
Meine Vermutung lag darin, das ncurses auf v6 gehoben wurde, conky aber noch auf v5 zugreift (welches nicht mehr da ist).

Nach 5 Minuten Suchmaschinen-Orakel war die Lösung doch recht einfach -> Softlink.
Mittels
{% highlight sh %}
$ ln -s /usr/lib/libncursesw.so.6  /usr/lib/libncursesw.so.5
{% endhighlight %}
war der Fehler schnell behoben und Conky strahlt mir wieder fröhlich entgegen.
Ist vielleicht nicht elegantes Lösung (da das Problem an sich nicht gelöst ist), aber es funktioniert für's erste.