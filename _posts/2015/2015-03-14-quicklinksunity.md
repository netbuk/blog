---
layout: post
title: "Quicklinks in Unity-Launcher"
date: 2015-03-14
tags: [linux, ubuntu, unity, archive]
comments: true
share: true
---

Wer sich für Ubuntu mit Unity entscheidet, der wird sich bestimmt schon einmal die Frage gestellt haben, ob und wie man eigene Quicklinks in den Launcher bringt.

Nun, um die erste Frage gleich zu beantworten, ja es geht.

Kommen wir also gleich zum technischen Anteil, um eigene Quicklinks in den Launcher zu bringen. Die Links werden in einer **.desktop** Datei unter **~/.local/share/applications/** gespeichert. Die Datei an sich hat nur einen geringen Textanteil, der die Launcher-API der Unity-Shell steuert.
Wie schaut nun der Inhalt der **.desktop** aus.
Hier ein Beispiel, dass ich verwende:

    [Desktop Entry]
    Version=1.0
    Name=my stuff
    Name[de]=my stuff
    Exec=xdg-open http://netbuk.dk
    Terminal=false
    X-MultipleArgs=false
    Type=Application
    Icon=mystuff.png
    Categories=Network;WebBrowser;
    StartupNotify=true
    StartupWMClass=netbuk.dk
    
    X-Ayatana-Desktop-Shortcuts=Evernote;ToDoIst;Boxcryptor;KeePass;NixNote;Gimp;Filezilla;CrossFTP;LibreOffice;Freemind;Planner;VirtualBox;Rhythmbox
    
    [Evernote Shortcut Group]
    Name=Evernote
    Exec=xdg-open https://www.evernote.com/Home.action
    TargetEnvironment=Unity
    
    [ToDoIst Shortcut Group]
    Name=ToDoIst
    Exec=xdg-open https://todoist.com/app?lang=de&v=320#
    TargetEnvironment=Unity
    
    [Boxcryptor Shortcut Group]
    Name=Boxcryptor
	Path=/home/christian/BoxCryptor/Boxcryptor/jre/bin
	Exec=./java -jar ../../Boxcryptor.jar
	TargetEnvironment=Unity
	
	[KeePass Shortcut Group]
	Name=KeePass2
    Exec=keepass2
    TargetEnvironment=Unity

    [NixNote Shortcut Group]
    Name=NixNote
    Exec=nixnote
    TargetEnvironment=Unity

    [Gimp Shortcut Group]
    Name=Gimp
    Exec=gimp
    TargetEnvironment=Unity

    [Filezilla Shortcut Group]
    Name=Filezilla
    Exec=filezilla
    TargetEnvironment=Unity

    [CrossFTP Shortcut Group]
    Name=CrossFTP
    Exec=crossftp
    TargetEnvironment=Unity

    [LibreOffice Shortcut Group]
    Name=Libre Office
    Exec=libreoffice
    TargetEnvironment=Unity

    [Freemind Shortcut Group]
    Name=Freemind
    Exec=freemind
    TargetEnvironment=Unity

    [Planner Shortcut Group]
    Name=Planner
    Exec=planner
    TargetEnvironment=Unity

    [VirtualBox Shortcut Group]
    Name=VirtualBox
    Exec=virtualbox
    TargetEnvironment=Unity

    [Rhythmbox Shortcut Group]
    Name=Rhythmbox
    Exec=rhythmbox
    TargetEnvironment=Unity

Der Erste Teil unter *[Desktop Entry]* gibt ein paar grundlegende Dinge an, wie z.B. das Icon. Die *Variable X-Ayatana-Desktop-Shortcuts* und die nachfolgenden Abschnitte geben die Möglichkeit, weitere Quicklinks unter dem Icon hinzuzufügen.
Das Icon ist in meinem Beispiel unter dem Ordner **~/.icons** gespeichert. Verwenden könnt ihr PNG oder noch besser SVG-Zeichnung.

Mehr Informationen, Hintergrundwissen und weitere Beispiele findet ihr unter [wiki.ubuntuusers.de/.desktop-Dateien](http://wiki.ubuntuusers.de/.desktop-Dateien).