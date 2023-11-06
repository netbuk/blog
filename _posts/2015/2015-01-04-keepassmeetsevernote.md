---
layout: post
title: "Keepass meets Evernote"
date: 2015-01-04
tags: [secure, evernote, keepass, archive]
comments: true
share: true
---

Wer [Keepass](http://keepass.info/) bzw. [KeepassX](http://www.keepassx.org/) nutzt um seine Passwörter sicher abzulegen, wird sich bestimmt schon einmal Gedanken um eine schnelle und einfache Speicherung seiner .kdbx Datei gemacht haben.
Lange habe ich meine .kdbx Datei in [Dropbox](https://dropbox.com) und später in [OneDrive](https://onedrive.live.com) gesichert. Eine vernünftige Synchronisation setzt aber voraus, dass die entsprechenden Clientprogramme permanent laufen. Auf Dauer ist das aber nervig, da die vielen kleinen Tools den Arbeitsspeicher zu setzen.

Daher bin ich auf die Variante gewechselt, die .kdbx in [Evernote](http://evernote.com) zu speichern und von dort zu öffnen, da ich Evernote so oder so am Laufen habe.

Der Vorteil spielt sich beim Beenden von Keepass aus Denn so bald man Keepass schließt wird die aktualisierte .kdbx automatisch in Evernote eingefügt bzw. die alte wird überschrieben. Dabei ist nur zu beachten, dass die Funktion *automatisch Speichern beim Beenden* in Keepass aktiviert ist.

So weit so gut und an sich eine feine Sache. Einziger Nachteil, um mal schnell ein Passwort nach zu schlagen, muss man erst in Evernote und öffnet dann mit Doppelklick die Datenbank in Keepass.
Da greift dann Plan B.
Man nutzt die Evernote Funktion *Ordner importieren*.
![Menue Ordner Import](https://cdn.netbuk.dk/blogposts/2015-01-04/menueordnerimport.png)
![Ordner Import Auswahl](https://cdn.netbuk.dk/blogposts/2015-01-04/ordnerimportauswahl.png)
Hierbei gibt man in Evernote einen Ordner an, der überwacht wird und Dateien automatisch in Evernote als neue Notiz einfügt.
Vorteil gegenüber der andere Variante,

- man öffnet einfach Keepass und greift auf die in dem überwachten Ordner gespeicherten .kdbx zu
- schnelleres Öffnen der .kdbx
- geänderte Dateien werden als einzelne Notiz in Evernote eingefügt. Dadurch hat man die älteren Versionen der .kdbx noch immer zur Verfügung (Stichwort: Versionisierung).

Da die .kdbx Datei an sich nicht besonders groß ist, stellt das auch kein Hindernis da, wenn man Evernote nur in der Freeversion nutzt.