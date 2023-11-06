---
layout: post
title: "Neues Jahr, neue Struktur"
description: "Dies und das, ein bisschen Technik, oder nicht?"
date: 2017-01-07
tags: [uberspace, ghost, server, blog, cloudron, services, contabo]
comments: true
share: true
---

Bekanntlich soll man ein neues Jahr immer frei von allem und mit Blick nach vorne gerichtet starten. Klappt leider nicht immer und in jedem Bereich. Für meinen virtuellen Teil habe ich dies vor, auch wenn das neue Jahr bereits Einzug gehalten hat. 

In den letzten Tagen habe ich einiges ausprobiert, um einen Konstante für meinen Blog zu finden. Da ich bekennender weise auf [Ghost](http://ghost.org) als Plattform stehe, ist die Auswahl der Hosts beschränkt. Lange Zeit habe ich einen Blog, mehr oder weniger gepflegt, auf einen bereits in die Jahre gekommenden [Uberspace](http://uberspace.de) betrieben. Die beste Lösung für einen sicheren Hafen schien mir dann aber die Pro Variante von [Ghost.org](http://ghost.org). Administrativ muss ich mich um nichts kümmern, der Blog funktioniert und die Wiese ist grün. Aber man darf eines nicht vergessen, die Kosten. 
In den Anfangszeiten von [Ghost.org](http://ghost.org) hatte ich schon einmal einen Pro Account. Damals mit 5$ ein erschwinglicher Preis. Durch Angebot und Nachfrage hat sich Ghost aber so in die Bloggerwelt (m.M.) etabliert, dass Infrastrukturen und Zeit/ Personal gemeistert werden müssen. Dies kostet Geld, was durch den Kunden beglichen werden muss. 
Mittlerweile kostet ein einfacher [Pro-Account monatlich 29$](https://ghost.org/de/pricing/). Das ist für eine Gelegenheit-Schreiberling wie meiner einer einfach zu viel für ein bisschen Technikspass. 

Also blieb die Frage, was nun?

Neben der o.a. Fragestellung habe ich mich noch mit den anderen Services beschäftigt, die ich so betrieben habe. O_o Vergangenheitsform?! 
Richtig, ein Teil von meinen kleinen Services habe ich abgeschaltet, archiviert und von den Servern gelöscht. Der Rest sollte aber auch ein neues Zuhause finden. 
Da bin ich auch [Cloudron](http://cloudron.io) gestossen. 
Diese Plattform bietet eine Grundlage um mittels einer Administrationsoberfläche Apps (eigentlich sind es [Docker](https://www.docker.com/) Container) auf einem Host zu installieren. Gepflegt werden diese Apps zentral, so dass man sich nicht ständig auf die Suche nach der neuesten Version einer seiner Services machen muss. Mhm, eine feine Sache, die es auszuprobieren gilt.

Dafür bietet sich die schnelle Lösung [Digital Ocean](http://digitalocean.com) an. Gesagt getan, ein Droplet mittels Cloudron eingerichtet und rumprobiert. Es hat auch alles wunderbar funktioniert, aber nicht alle Apps, die ich gerne betreiben wollte, konnten mangels Leistung des Droplet installiert/ betrieben werden. Ein Upgrade hätte die monatlichen Kosten so hoch getrieben, dass dies für mich in keinem Verhältnis zum Nutzen gestanden hätte. 
Also was nun? Wieder einzeln installieren und administrieren? Ein Teil der Apps (Programme) laufen nicht auf einem Uberspace.

Nö, darauf hatte ich keinen Bock.

Da ich noch einen Gutscheincode von meinem alten Serverhoster [Contabo](http://contabo.de) hatte, wagte ich mich an die Installation von Cloudron auf einem VPS. Mein Wahl viel auf den VPS M SSD. Ausreichend Leistung, ausreichend Speicherplatz und das für einen erschwinglichen Preis, wobei ich ja erstmal noch meinen Gutschein hatte.

Gesagt getan. Server wurde eingerichtet und [Cloudron](http://cloudron.io) installiert. Auch das Einrichten der Domain mittels Wildcard über [Cloudflare](http://cloudflare.com) hat einwandfrei funktioniert.

Derzeit laufen 8 Apps (Programme in Docker Container) auf dem Server und es ist noch Platz noch oben ^^.

- Rocket Chat
- Paperwork
- Ghost Blog (nicht dieser hier)
- nodeBB
- hastebin
- Lychee
- Taiga
- Wekan

### Die Auslastung

![](/images/Cloudron_Speicherplatz.png)
![](/images/Cloudron_Arbeitsspeicher.png)
![](/images/Cloudron_Graph.png)

Da ich mir noch nicht im Klaren bin, ob diese Variante VPS - [Cloudron](http://cloudron.io) für mich Bestand hat und auch das Thema Backup, Sicherheit und allgemeiner Betrieb ausschlaggebend sind, habe ich mich, dafür entschieden, meinen (Haupt)Blog wieder auf einem [Uberspace](http://uberspace.de) zu betreiben. 
Der Wartungsaufwand ist eigentlich überschaubar. Updates für [Ghost](https://ghost.org/de/developers/) bekomme ich mittels Newsletter/ Feedly mit und [Uberspace](https://uberspace.de) bietet dazu auch ein [Script](https://wiki.uberspace.de/cool:ghost#ghost_updaten_alpha) an. Backups kann ich manuell durchführen, was bei [Cloudron](http://cloudron.io) für mich derzeit noch nicht ersichtlich ist. Und zu guter Letzt kann ich den [Preis für den Blog/ Uberspace selber bestimmen](https://uberspace.de/prices).

Vielleicht komme ich nach einigem Testen und ausprobieren zum Entschluss, dass ich eigentlich die ganzen Services gar nicht brauche und eine einfache Plattform ausreichend ist. 

Das wird sich zeigen, 2017 ist noch jung ....