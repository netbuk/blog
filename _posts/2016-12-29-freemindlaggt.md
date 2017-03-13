---
layout: post
title: "Freemind laggt beim Scrollen"
date: 2016-12-29
tags: [macos, freemind, programme, bug]
comments: true
share: true
---

Verwendet wird Freemind v1.0.1 auf MacOS Sierra v10.12.2

Beim Scrollen in Vollansicht kommt es zum laggen/ rubbern der Anzeige. Ein sauberes Arbeiten ist nicht möglich. Das Problem sind die vorrausgesetzten Java-Version seitens Freemind und der aktuellen Java-Version, die auf dem Mac installiert ist.

Um den Fehler auszubügeln, muss man folgende Schritte ausführen:

1. Freemind schließen
2. Im Finder unter Programme >> Freemind >> Paketinhalt zeigen
3. Anschließend Contents >> Info.plist öffnen
4. Dort sucht man sich die folgenden Zeilen und löscht sie aus der Datei.

    `<key>JVMRuntime</key>`<br>
    `<string>jdk1.7.0_45.jdk</string>`

5. Speichern, schließen und Freemind starten.

Jetzt sollte ein normales h/v Scrollen möglich sein.

Den Originalbeschreibung in Englisch findet man im Ticketsystem von Sourceforge >> Freemind >> *[#1158 FreeMind is rubber banding when scrolling](https://sourceforge.net/p/freemind/bugs/1158/#64ec)*