---
layout: post
title: "Git aufräumen"
date: 2016-12-29
tags: [github, git, terminal, archive]
comments: true
share: true
---

Wer gerne und viel mit Git seine Projekte versionisiert, wird nach einer gewissen Zeit feststellen, dass sich die lokalen Repositories (*.git Ordner*) schnell aufblähen.
Git bringt dafür eine kleine Funktionalität mit, die für etwas Ordnung sorgt und Speicherplatz frei gibt.

Mittels dem kleinen Befehl `git gc` im Terminal (man muss sich im jeweiligen Projektordner befinden) werden überflüssige Dateien und nicht mehr vorhandene Objekte im *.git-Ordner* entfernt bzw. Dateirevisionen komprimiert. Das sorgt für einen geringeren Speicherplatzbedarf und hat den Effekt eines Geschwindigkeitschubs für alle Git-Operationen.

Natürlich kann man den Befehl auch mit Optionen kombinieren. Meine Favoriten sind:

    --aggressive: gründlichere Optimierung (Ausführung dauert etwas länger als beim Standard)

    --auto: Git entscheidet, ob eine Optimierung notwendig ist. Ggf. wird der Vorgang durch Git abgebrochen.

Beide können natürlich auch kombiniert werden.
`git gc --agressive --auto`

Alle Informatione rund um den Befehl `git gc` findet man in der offiziellen [Git-Dokumentation]( https://git-scm.com/docs/git-gc/).