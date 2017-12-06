---
title: Über dieses Programm
type: sanskrit
order: 1
---

> Morpheus für Sanskrit

Liegt in Form eines Browser-Addons (nur für Chromium-Browser) vor und basiert auf einem einfachen praktischen samAsa-Parser und einer Morphologie-Analyseroutine. Das Programm soll demnächst - analog zu Morpheus für Altgriechisch und Chinesisch - komplett als eigenständige Desktop-Anwendung umgeschrieben werden. Dieses Addon war mein erster Versuch eines Morpheus-Programms und bleibt als historisches Beispiel bestehen, auch wenn der Code mittlerweile veraltet ist.

Morpheus für Sanskrit hat drei Hauptziele:

- Zerlegen langer zusammengesetzter Wörter (samAsa) in deren Bestandteile (padas)
- Bestimmung der Morphologie vom jedem pada
- Anzeige von Wörterbuchangeben zu jedem pada

Die Zerlegung eines zusammengesetzten Wortes (samAsa) in dessen Bestandteile (padas) funbktioniert folgendermaßen:

- Das zusammengesetzte Wort wird von Buchstabe zu Buchstabe fortlaufend und unter Berücksichtigung der Sandhi-Regeln (sandhi.js) in alle möglichen Segmente ("Flakes" oder "Splitter") zerlegt. Unmögliche Segmente werden verworfen. Danach werden mit Hilfe einer rekursiven Funktion wahrscheinlichee Segmentketten erstellt. Dies ist ein sehr ressourcenaufwendiges Verfahren, wobei - abhängig von der Komplexität und von Mehrdeutigkeiten bei den padas sowie unter Berücksichtigung der Sandhi-Regeln - ein 50-stelliges Wort 150.000 mögliche Kombinationen ergeben kann. (vigraha.js)
- Undeklinierbare Segmente werden in ein separates Array gereiht und auf diese Weise potentiell deklinierbare Segmente bestimmt.
- Für jede deklinierte Segment werden dessen
 mögliche Wörterbuchformen bestimmt.
- Separat für Verben (tiNanta.js)
- und für Nomen (subanta.js)
- Es verbleiben nur Ketten, die aus den Padas bestehen, welche in einem Wörterbuch auffindbar sind.
- Diese werden gewichtet, sodass die plausibleren Lösungen am Anfang einer Ergebnisliste zu stehen kommen.
- Die Ergebnisse werden ausgegeben.

Zum Testen der Routine vigraha.js wurden sämtliche zerlegte komplexe Wörter der Bhagavad-gita verwendet, wie sie aus zuverlässigen Quellen im Internet verfügbar sind [1], [2]
