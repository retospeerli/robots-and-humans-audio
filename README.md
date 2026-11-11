# Listen & Choose – Human or Robot?

Neue Hör-Lernapp mit denselben 47 englischen Begriffen. Komplette Website ohne Backend.

## Ablauf
1. 47 gesprochene englische Begriffe hören und die englische Wortkarte unter sechs Optionen wählen.
2. Dieselben 47 englischen Begriffe hören und die deutsche Übersetzung unter sechs Optionen wählen.
3. Dieselben Begriffe **nur hören** und das passende Bild Humans / Robots / Both anklicken.

Die Wörter werden bei jedem Durchgang neu gemischt. Das englische Wort wird in allen Runden langsam (Sprechtempo 0.76) mit einer verfügbaren englischen Stimme des Browsers gesprochen. Der Lautsprecherknopf kann beliebig oft verwendet werden. Die App spricht **nie deutsche Begriffe** vor. Wenn die Sprachausgabe im Browser nicht funktioniert, bitte Chrome, Edge oder Safari verwenden und den Lautsprecher anklicken. Offline funktioniert die Sprachausgabe nur mit auf dem Gerät installierter englischer Stimme.

Nach jeder Runde: «Check answers» → nur Anzahl Fehler. Falsche Antworten werden nicht hervorgehoben und die richtigen Antworten nicht verraten. Bei Fehlern muss die Runde erneut absolviert werden.

## Dateien
- index.html: gesamte Webapp (keine Fremd-JavaScript-Libraries)
- robot.jpg, human.jpg, both.jpg: eigene Illustrationen für Runde 3.

## GitHub Pages
Dateien direkt in den Root eines Repositories hochladen, dann Settings → Pages → Deploy from a branch, main / (root) aktivieren. Alle vier Dateien müssen im selben Ordner bleiben. Die Google-Schrift ist optional; ohne Netz wird eine Systemschrift verwendet.

## LearningView
Bei LearningView als **Interaktiv (extern)** mit der URL der veröffentlichten App einbinden. Die App speichert nach Rundenerfolgen den Lernstand über LearningViews Embed API. Ausschliesslich nach drei vollständig korrekten Runden sendet sie `{result:{score:{scaled:1}}}` an `https://learningview.org`. Nach dem Schliessen übernimmt LearningView diesen Score. Für eigenständige Nutzung im Browser ist kein LearningView nötig. Keine vorzeitige Erfolgsbestätigung. Browser-Sprachausgabe setzt Nutzerinteraktion voraus.

Dokumentation: https://learningview.org/embed-api.php


## Version 1.1 – Wiederholungen und Bildreihenfolge

- Bildrunde: Links **Humans** (human.jpg), Mitte **Both** (both.jpg), rechts **Robots** (robot.jpg). Die Bilder sind unverändert.
- Nach dem Check werden bei Fehlern **alle falschen Begriffe** erneut abgefragt. Falls weniger als ein Drittel (16 von 47) falsch waren, wird die Wiederholung zufällig mit bereits richtig beantworteten Begriffen auf 16 ergänzt. Bei mehr als 16 Fehlern werden alle falschen wiederholt.
- Bei weiteren Fehlern folgt eine weitere verkürzte Runde nach demselben Prinzip. Welche Begriffe falsch waren, wird nie angezeigt.
- Die nächste Hauptübung wird erst nach einer fehlerfreien Wiederholungsrunde freigeschaltet. LearningView-Erfolg wird erst ganz am Ende gemeldet.


## Version 1.2 – Startfehler behoben
Der Startknopf übergibt kein Klick-Ereignis mehr an die Wiederholungsfunktion. Start, erste Runde, Check und Wiederholungsstart wurden im Chromium-Browser getestet.
