---
layout: post
title: "New comment system online"
date: 2017-01-26
tags: [isso, blog, kommentare]
comments: true
share: true
---

Mit Disqus als Kommentarsystem war und bin ich bisher zufrieden. Einzig das die Inhalte auf auswärtigen Server irgendwo liegen, ist mir ein Dorn im Auge.
Daher habe ich mich [Isso](https://posativ.org/isso/) zugewandt, einem self-hosted Kommentarsystem.

Isso benötigt [Python](https://www.python.org/), was ein [Uberspace](https://uberspace.de) bereits hergibt. Die Installation ist recht einfach und gespeichert werden die Kommentare in einer [SQLite](https://sqlite.org/)3 Datenbank.

Von den Usern wird neben dem Kommentar nur /24 bzw. /48 der IP-Adresse für IPv4 respektive IPv6 in der Datenbank gespeichert. Wiederkehrende Nutzer können sich per E-Mail-Adresse das gleiche Identicon wiederholen.

Wer sich Isso für seinen Blog oder Webseite einrichten möchte findet [hier eine kleines HowTo](https://blog.posativ.org/2014/isso-und-uberspace-de/). Ansonsten schaut einfach bei [Github](https://github.com/posativ/isso) oder auf der [Projektseite](https://posativ.org/isso/) vorbei.