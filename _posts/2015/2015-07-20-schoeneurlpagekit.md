---
layout: post
title: "Pagekit mit schönen URLs auf Uberspace"
date: 2015-07-20
tags: [uberspace, pagekit, archive]
comments: true
share: true
---

Wer sich etwas auf seinem [Uberspace](https://uberspace.de) installiert, der schaut natürlich erst nach, ob die Anforderungen stimmig sind. Gesagt getan und Pagekit (v1.0.5) läuft auch, sonst könntet ihr das nicht lesen.
Aber etwa hat mich in den letzten Tagen immer wieder gestört. Im Pfad war zwischen der Domain und dem weiterführenden Pfad immer die index.php gestanden. 

Nachdem ich mich auf [Github durch die Issues](https://github.com/pagekit/pagekit/issues/642#issuecomment-218128665) durchgearbeitet habe, wurde mehrfach darauf hingewiesen, dass dieser Fehler mit dem Apache Modul mod_rewrite zusammen hängt. Anscheinend kann nicht sauber festgestellt werden, ob mod_rewrite aktiviert ist oder nicht und das hat zur Folge, dass die .htaccess nicht gelesen wird. Dadurch gibt es dann einen Fallback und die Pfade beim Aufrufen der Seite und ihrer Unterseiten spuckt immer die index.php mit aus.
An der Funktion ändert sich nichts, sieht nur blöd aus.

Mehr oder weniger durch Zufall bin ich dann auf einen [Artikel bei den Issues](https://github.com/pagekit/pagekit/issues/642#issuecomment-218128665) gestoßen, wo ein Workaround aufgeführt war. Und zwar liegt das Problem bei Uberspace darin, dass dort mit FastCGI gearbeitet wird, um den vielen Nutzern mehr Freiheiten bei der Konfiguration bieten zu können. Damit hat Pagekit aber noch ein paar Probleme, da es z.B. mod_rewrite nicht erkennt und wieder in den Fallback fällt.

Um gehen kann man das mit dem Workaround.

Dazu ändert man die Zeile 17 in der RequestContext.php. Zu finden unter
**/var/www/virtual/UBERSPACENAME/PAGEKITORDNER**

oder 

**DOMAIN/app/modules/routing/src/RequestContext.php**
von
```
        $this->setBaseUrl($request->server->get('HTTP_MOD_REWRITE') == 'On' ? $request->getBasePath() : "{$request->getBasePath()}/index.php");

```
in
```
        $this->setBaseUrl($request->getBasePath());
```