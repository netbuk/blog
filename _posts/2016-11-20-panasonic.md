---
layout: post
title: "Panasonic DMC-FZ72 meets Linux"
date: 2016-11-20
tags: [linux, fotografie, archive]
comments: true
share: true
---

Für die Nachbearbeitung meiner Fotos nutze ich hauptsächlich (link: https://lightroom.adobe.com/ text: Lightroom) unter Windows. In den letzten Tagen viel mir ein Artikel zum Thema (link: https://www.darktable.org/ text: Darktable) in meinem (link: https://feedly.com/i/discover text: Feedly Stream) auf.
Bisher hatte ich mir noch keine Gedanken gemacht, ob und wie ich meine Fotos auch unter Linux (ich nutze ja noch ein Thinkpad T61 mit Manjaro Linux) importieren und bearbeiten kann. Nachdem ich gestern den Grundkurs bei (link: http://aleahorst.de text: Alea Horst) absolviert hatte, bin ich wieder voll motiviert und habe mich heute morgen gleich hingesetzt, um den o.a. Gedanken mal auszuprobieren.
Tja, wie sollte es auch anders sein. Kaum hatte ich die Kamera angeschlossen passierte - nichts. War ja auch nicht anders zu erwarten :D
Was macht also der halbwegs visierte Linux-User, er haut ein `lsusb` in die Konsole  und schaut sich das Ergebnis an. Das war dann auch sehr ernüchternd, den die Kamera wurde nicht angezeigt. Ergebnis und Siegerehrung - keine Unterstützung/ Treiber auf der Maschine.
Nach 10 Minuten rum gegoogle dann ein erster Hinweis. Manche Kameras kommunizieren mittels PTP. Also Pacman angeschmissen und `libptp2` aus den Paketquellen nach installiert. Sollte ein Fehler auftreten, dann fehlt wie bei mir wahrscheinlich eine `libusb0` (v0.x.x), da mein Manjaro mit einer höheren Version grundsätzlich arbeitet. Die `libusb0` kann man ebenfalls über Pacman und den Paketquellen nach installieren.
Ergänzend zu den beiden Bibliotheken habe ich noch die `libgphoto2` installiert. Diese wird benötigt, wenn man externe Programme (z.B. Darktable) Zugriff auf die Kamera erlauben will.

Nachdem dann alles installiert war, habe ich die Kamera noch einmal angeschlossen und anstelle der Verbindungsart PC nun PTP gewählt. Siehe da, ich kann jetzt auf die Kamera mittels Thunar und Darktable zugreifen.

Jetzt gilt es, sich ein wenig mit Darktable zu befassen. Leider ist meine Auflösung nur 1024x768. Das Darktable-Fenster braucht aber eine größere Breite. Mal schauen wie sich das Problem lösen lässt. Ich werde berichten ...

Schlußlicht
Wer ein paar deutsche Tutorials zu Darktable sucht, sollte mal bei (link: http://www.multimedia4linux.de/index.php/bildbearbeitung/darktable text: multimedia4linux.de) reinschauen.