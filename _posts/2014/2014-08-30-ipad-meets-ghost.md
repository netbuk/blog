---
layout: post
title: "iPad meets Ghost Blog"
date: 2014-08-30
tags: [ios, apple,ipad air, ghost, archive]
comments: true
share: true
---

So, das soll er sein. Der erste Eintrag über mein iPad. 

Funktionell gibt es keine Einbußen gegenüber Laptop & Co beim Schreiben in Ghost. Habe aber auch nichts anderes erwartet.

Da dies der erster Ausflug von mir in die große bunte Apple-Welt ist, überraschte mich doch der einfache und logische Umgang mit dem iPad und iOS sehr. Mittlerweile kann ich gut verstehen, warum so ein Hype um Apple und seine Produkte gemacht wird. Tja, lange habe ich davon abgeschworen, aber nun mitten drin. Sicher bin ich mir auch schon, was mein nächster Laptop wird - ein MacBook Air.
Das einzige was mir tatsächlich gefehlt hat, war der Evernote Webclipper. Aber was wären die Suchmaschinen, wenn sie nicht auch dafür einen Ratschlag geben würden. 

Auf [Macdaily](http://www.macdaily.co/add-evernote-web-clipper-safari-ios/) wurde ich fündig. Man muss eigentlich nur ein Lesezeichen in seinem Safari für iPad erstellen. Anschließend das Lesezeichen umbenennen und in der URL-Zeile folgendes hinein kopieren.

``` javascript
javascript:(function() {EN_CLIP_HOST='http://www.evernote.com';try{var%20x=document.createElement('SCRIPT');x.type='text/javascript';x.src=EN_CLIP_HOST+'/public/bookmarkClipper.js?'+(new%20Date().getTime()/100000);document.getElementsByTagName('head')[0].appendChild(x);}catch(e){location.href=EN_CLIP_HOST+'/clip.action?url='+encodeURIComponent(location.href)+'&title='+encodeURIComponent(document.title);}})();
```

Wichtig ist nur, das ihr in den Einstellungen von Safari Drittanbieter- Cookies zulasst.
Jetzt könnt ihr die Webseite in Evernote speichern, wenn ihr auf der gewünschten Seite das Lesezeichen aufruft. Leider kann man nur die gesamte Webseite speichern und keine Ausschnitte, wie in der Webclipper Version, aber mit ein paar Klicks in Evernote bekommt man die Quintessenz hin.

*Quelle: macdaily.com*