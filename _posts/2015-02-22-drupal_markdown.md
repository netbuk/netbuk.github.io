---
layout: post
title:  "Drupal meets markdown"
date:   2015-02-22
banner_image: markdown.png
categories: cms server framework drupal markdown
comments: true
---
Nachdem ich mich ein wenig mit dem Feintuning von Drupal befasse, war eine der ersten Fragen, ob Drupal auch Markdown kann. 
Die Antwort ist recht einfach. Ja, Drupal kann.

Was braucht man alles dafür?
Für den einfachen Umgang von Markdown in Drupal benötigt man lediglich das **[Markdown Filter Modul](https://www.drupal.org/project/markdown)**. Nachdem das Modul installiert und aktiviert ist, könnte man einem vorhandenen Textformat den Filter dazugeben. Davon rate ich aber ab. Angenehmer ist ein eigenes Textformat, damit es nicht zu ungewollten Problemen kommt.
Ruft `/admin/config/content/formats/add` auf wählt einen aussagekräftigen Namen (z.B. Markdown). Anschließend könnt ihr die Rollen auswählen, die diesen Filter nutzen dürfen. Danach wählt ihr Markdown unter *Aktivierte Filter* aus und speichert euren neuen Filter ab. 
![](/images/drupal_Textformat.png)
Auf der Liste der Textformate taucht jetzt euer neues Format auf. Wenn ihr auch zu denjenigen gehört, die Markdown als favorisiertes Format einsetzen wollen, dann ändert die Gewichtung (Zeilenreihenfolge einblenden nicht vergessen!) auf -10. Damit ist gewährleistet, das bei einem Erstellen eines neuen Inhalts, Markdown als Standardformat vorausgewählt ist.
![](/images/drupal_Liste_textformate.png)
Was ihr auf keinen machen solltet, ist das Deaktivieren von Textformaten, da eine Re-Aktivierung nur durch den direkten Eingriff in eure MySQL-Datenbank durchgeführt werden kann.

Soweit so gut. Nun könnt ihr Markdown als Textformat in Drupal einsetzen. 
Für alle Markdown-Starter, die noch nicht alle Markdown Tags auswendig können bzw. für Gelegenheitsschreiber bietet sich das Modul **Markdown Editor** an. Dies beinhaltet eine Toolbar mit einigen Markdown Tags, wie z.B.

+ Fett
+ Kursiv
+ Überschrift
+ Code
+ Zitat
+ Listen
+ Link
+ Bilder

Aber mit der einfachen Installation des Editors ist es nicht getan. Dieser hat gewisse Abhängigkeiten, die vorher erfüllt sein müssen. Der **Markdowneditor** ist quasi ein Addon des **BUEditors**, der natürlich vorhanden sein muss, wie auch der bereits o.a. **Markdown Filter**.

Neben dem Editor bietet sich auch das Modul **Ajax Markup** an, welches eine bessere Vorschaufunktion für Nicht-HTML Markups erzeugt. Dieses Modul *muss vor dem Editor aktiviert werden*. 
Daher habe ich folgende Installations-/ Aktivierungsreihenfolge vollzogen:

+ [Markdown Filter Modul](https://www.drupal.org/project/markdown) (siehe oben)
+ [Ajax Markup](https://www.drupal.org/project/ajax_markup)
+ [BUEditor](https://www.drupal.org/project/bueditor)
+ [Markdown Editor for BUEditor](https://www.drupal.org/project/markdowneditor)

Nach jeder einzelnen Modulinstallation habe ich direkt das Modul aktiviert und den Cron laufen lassen.

Unter `/admin/config/content/bueditor` müsst ihr noch die Rollen entsprechend zuordnen. 
![](/images/drupal_BUEditor.png)

Sofern ihr vorher keine anderen zusätzlichen Editoren, wie z.B. Markup oder TinyMC, installiert habt, könnt ihr direkt mit dem neu installierten Markdown Editor Konstrukt loslegen.