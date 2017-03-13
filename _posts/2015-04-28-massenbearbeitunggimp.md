---
layout: post
title: "Massenbearbeitung von Bildern in Gimp"
date: 2015-04-28
tags: [gimp, bildbearbeitung, archive]
comments: true
share: true
---

Wer kennt das nicht. Es hat sich eine Menge an Bildern und Fotos angesammelt und man möchte diese zum Beispiel für einen Blog oder eine Webgallerie, am besten alle auf einmal, skalieren. Unter Photoshop kann man dafür Droplets erstellen, die dann diese Massen-/ Stapelverarbeitung durchführen. Wer aber nicht mit Photoshop arbeiten möchte (aus welchen Gründen auch immer), kann auf Gimp zurückgreifen.
Für Gimp gibt es die verschiedensten Filter, die nachinstalliert werden können. Um die o.a. Funktionalität durchzuführen, brauchen wir David's Batch Prozessor. 

Windows User können den Filter unter der [Projektwebseite](http://members.ozemail.com.au/~hodsond/dbp.html) herunterladen. Datei entpacken und den Inhalt in den Plugin Ordner von Gimp kopieren. Gimp starten und dann sollte der Filter im gleichnamigen Menü auftauchen.
Linux User werfen entweder einen Blick in ihre Paketquelle oder schauen auch auf der Projektwebseite vorbei. Unter **Linux Mint** befindet sich u.a. der Filter in dem Paket **gimp-plugin-registry**. Installieren, Gimp starten, fertig. Der Filter befindet sich nun auch unter dem gleichnamigen Menü **Filter -> Batch -> Batch process**.

Kommen wir nun zu einem Beispiel. 
Da ich für meinen Blog verschiedene Header-Fotos nutze, die aber eine Größe von 5616x3744 Pixel aufweisen (was zum Laden auf einer Webseite/Blog viel zu groß ist), möchte ich diese auf 1920x1280 Pixel skalieren.
Dazu rufen wir den Batch Process auf (siehe Pfad oben). Es erscheint ein kleines Fenster. Der Text ist in Englisch, was m.E. nicht weiter schlimm ist (kurze Erklärung der Reiter ist am Ende des Artikels angefügt).
Zuerst laden wir uns auf dem Reiter **Input -> Add Files** die zu bearbeitenden Fotos in das Programm.

![Bildschirmfoto David s Batch Processor1](https://cdn.netbuk.dk/blogposts/2015-04-28/Bildschirmfoto-David-s-Batch-Processor1.png)

Dabei ist m.E. darauf zu achten, dass die Fotos die gleichen Seitenverhältnisse haben. Das erleichtert das weitere Einstellen.

Um jetzt eine Skalierung durchzuführen, müssen wir die entsprechenden Werte für die Ausgabe festlegen. Dazu gehen wir auf den Reiter **Rezise**.
Hier haben wir die zwei Möglichkeiten, die Skalierung durchzuführen. **Relative** oder **Absolute**. **Relative** skaliert in % zum Original, **Absolut** in eine fest zu legende Größe. Bevor wir uns aber zwischen eine der beiden Varianten entscheiden aktivieren wir die Funktion und setzen den Haken von **Enable**. 
Jetzt wählen wir Absolute, da wir auf eine feste Größe skalieren wollen. Wir stellen die width und height entweder durch eintragen der Werte oder durch Verschieben des Reglers ein. Darunter können wir im **Dropdown Fit** (Anpassen) noch zwischen verschiedenen Methoden auswählen.

![Bildschirmfoto David s Batch Processor2](https://cdn.netbuk.dk/blogposts/2015-04-28/Bildschirmfoto-David-s-Batch-Processor2.png)

* Padded => Auffüllen (Sollten Bild und gewähltes Format nicht stimmig sein, wird der Rest/Hintergrund mit Farbe aufgefüllt)
* Excactly => Exakte Anpassung (Das Bild wird gezerrt. U.u. ist dies danach nicht brauchbar => Stichwort Seitenverhältnis)
* Inside => Die längste Seite des Bildes wird an die Vorgabe angepasst. Die kürzere Seite wird proportional verkleinert. 
* Outside = Die kürzeste Seite des Bildes wird an die Vorgabe angepasst. Die längere Seite wird proportional angepasst.

Da die gewählten Fotos das gleiche Seitenverhältnis haben, entscheiden wir uns für excactly.

Nachdem wir nun die vorzunehmende Skalierung eingestellt haben, müssen wir noch einen Speicherort und/oder eine andere Dateibenennung vornehmen. Dazu gehen wir auf den Reiter **Rename**. Hier haben wir die Möglichkeit einen entsprechenden Ordner anzugeben (Select Dir) oder ein Prefix für die bearbeitenden Fotos anzugeben. M.E. ist die beste Variante immer ein neuer Speicherort, sprich einen neuen Ordner anzugeben. Dazu klicken wir auf **Select Dir** und wählen den Ordner wo das Programm die bearbeiteten Fotos speichern soll aus.

![Bildschirmfoto David s Batch Processor3](https://cdn.netbuk.dk/blogposts/2015-04-28/Bildschirmfoto-David-s-Batch-Processor3.png)

Wenn ihr die bearbeiteten Fotos im gleichen Ordner wir die Quellfotos abspeichern wollt, wählt **Source Dir** und tragt ein **Prefix** oder **Postfix** ein (pre => davor; post => danach). 
Der darunterliegende Bereich Example zeigt euch gleich an, wie sich eure Auswahl auswirkt.
Mit den darunter befindlichen Einstellungen könnt ihr noch das eine und andere mit den Fotos anstellen.

* Flatten => Ebenen zusammenfügen
* Convert Grey => in Graustufen umwandeln
* Convert Indexed => indiziert die bearbeiteten Fotos
* No Dither => kein Verwischen (Einstellungen für das GIF-Format)
* Colors => Farben (Abhängig mit der Auswahl No Dither. Hier können Angaben zum Farbkanal gemacht werden.)

Zu guter Letzt gehen wir auf den Reiter **Output** um das Format und dazugehörige Einstellungen vorzunehmen. Hier wählen wir in unserem Beispiel das **Format .jpg** mit einer **Quality von 1,00 (100%)**. Die hier aufgeführten Einstellungsmöglichkeiten sind die gleichen wie beim Exportieren in Gimp. Daher gehe ich darauf auch nicht weiter ein.

![Bildschirmfoto David s Batch Processor4](https://cdn.netbuk.dk/blogposts/2015-04-28/Bildschirmfoto-David-s-Batch-Processor4.png)

Jetzt Starten wir die Verarbeitung mit dem **Start-Button**. Wer sich anschauen möchte wie Gimp den Prozess abarbeitet, der kann noch **Show Images** aktivieren.
So bald dann der Ladebalken durchgelaufen ist und darüber *--done--* steht, ist der Prozess beendet und alle Fotos sollten in das gewünschte Format skaliert sein.

###Reiterbeschriftung (Eng-Deu)

* Input => Eingabe (Bildquelle festlegen)
* Turn => Drehen
* Blur => Weichzeichnen
* Color => Einfärben
* Resize => Skalieren
* Crop => Zuschneiden
* Sharpen => Schärfen
* Rename => Dateibenennung und Ausgabeort
* Output => Ausgabeformat und Eigenschaften