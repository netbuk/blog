---
layout: post
title: "Windows in-the-Box"
date: 2015-01-26
tags: [linux, windows, virtualbox, archive]
comments: true
share: true
---

Nach meinem Crash mit dem Laptop vor ein paar Tagen hatte ich aufgrund der UEFI Beschaffenheit keine Möglichkeit Windows wieder lauffähig auf meinen Laptop zu bringen. Was tun?

Nun ja, in der Vergangenheit habe ich schon oft mit Linux, insbesondere mit Ubuntu und Debian, gearbeitet und experimentiert. Einer vollständigen Portierung bin ich aber bisher immer aus dem Weg gegangen, da ich gerne mal eine Runde Spiele (kommt nicht oft vor). Dazu kommt noch Photoshop, das es leider nie in die Linuxwelt schaffen wird. 
Dieses mal sah es aber so aus als hätte ich keine andere Wahl. Also entschied ich mich für Ubuntu als Hauptsystem. Nachdem ich die Masse der Funktionen und Programme die ich benötige installiert hatte, blieb mir eigentlich nur noch den Lösungsweg für Photoshop zu finden. 
Dieser ließ sich in Form meines alten Bekannten, VirtualBox, identifizieren. 

Gesagt, getan. Die VBox angeschmissen und Windows 8 pro installiert. Leider hatte ich zu diesem Zeitpunkt nicht bedacht, dass ich zwar eine Version Windows 8 pro in Form einer DVD besitze, aber leider der dazugehörige Productkey nur zum Upgraden fungiert.
Egal, denn es gibt keine Probleme, sondern nur Herausforderungen.

Nachdem ich die Suchmaschine mit Daten gefüttert habe, kam ich recht schnell auf eine Lösung. Man gaukelt Windows vor, dass es nicht frisch installiert wurde, sondern angeblich von einer älteren Version aktualisiert wurde. 
Sicher, ich hätte natürlich auch die virtuelle Maschine löschen und mit einer frischen Windows 7 Version anfangen können, um dann das Upgrade auf Windows 8 pro zu vollziehen. Aber den Aufwand nur für Photoshop zu betreiben, war mir ehrlich gesagt zu viel.

So, kommen wir nun zum technischen Anteil.
Dazu gehen wir in die Registry mittels Ausführen --> regedit und ändern folgenden Wert:
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\OOBE`

`MediaBootInstall von 1 auf 0`

Anschließend die Konsole im Administrationsmodus öffnen und folgenden Befehl ausführen: 
`slmgr -rearm`

Danach wird man aufgefordert den Rechner neu zu starten. 
Nach dem Neustart kann man ohne Probleme Windows mittels dem Upgrade-Productkey aktivieren. 

Sollte es zu einer Fehlermeldung bei der Befehlseingabe kommen, dann kann es daran liegen, dass ihr den Festplattenspeicher für eure virtuelle Windowsinstallation zu gering gewählt habt.
In diesem Fall ist es, dank dem Kommandozeilen-Tool von VirtualBox, aber recht einfach, den Festplattenspeicherplatz zu vergrößern. Natürlich setzt das genug Festplattenspeicherplatz auf dem HOST voraus.

#### Wichtig!

Mittels dem nachfolgenden Befehl könnt ihr **nur den Speicherplatz vergrößern**, **nicht verkleinern**.

Jetzt wieder der technische Anteil.
Man öffnet den Terminal des HOST und navigiert in den Ordner, wo sich die VDI-Datei befindet. Dort angekommen gibt man dann folgenden Befehl ein: 
`VBoxManage modifyhd --resize 20000 Windows.vdi`

- VBoxManage ist das Kommandozeilen-Tool von VirtualBox 
- 20000 = die neue Größe in MB 
- Windows.vdi = Name der virtuellen Festplatte 

Auf diese Weise können aber nur **dynamisch** erzeugte Festplatten vergrößert werden. Anschließend muss man noch in Windows unter der Datenträgerverwaltung den neu gewonnenen Speicher der Partition zuweisen. 

Bei virtuellen Festplatten mit fixer Speichergröße, ist das erweitern nicht ganz so einfach. 
Zuerst muss man die vorhandene virtuelle Festplatte klonen und dabei den Klon auf dynamisch setzen. Das geschieht mittels folgenden Befehl.

`VBoxManage clonehd Windows.vdi Windows_klon.vdi`

Natürlich befindet man sich dazu mittels Terminal im Ordner, den die virtuelle Festplatte beherrbergt.
Dieser Vorgang kann je nach Größe etwas Zeit in Anspruch nehmen. Natürlich gilt auch hier wieder, dass genügend Speicherplatz auf dem HOST zur Verfügung stehen muss. Anschließend kann man wie bereits oben beschrieben, den Speicherplatz erweitern.