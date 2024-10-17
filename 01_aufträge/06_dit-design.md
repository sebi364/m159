# **Aufgabe 6:** Directory Information Tree `(2 Punkt)`
Bevor Sie mit der Aufgabe beginnen, lesen Sie das Kapitel «5.2.1 OUs und Gruppenrichtlinien» im Dokument Gruppenrichtlinien-Kapitel5.pdf

## DIT erstellen `(1 Punkte)`
Erstellen Sie aus den nachfolgenden Daten einen passenden DIT in einem visuell dafür vorgesehenen Tool. Zum Beispiel Visio oder «https://draw.io». Erstellen Sie für einen User und einen Computer den DN direkt im Diagramm gut ersichtlich.

Richtlinien für den DIT:
- Jede Abteilung darf in diesem DIT nur einmal als Organisationseinheit vorkommen
- Die Standorte müssen in diesem DIT abgebildet sein
- Alle Abteilungen, welche an beiden Standorten vorkommen, sollen über einen fiktiven Standort mit einem sinnvollen Namen abgedeckt sein
- Pro Standort gibt es einmal intern und extern
- Achten Sie darauf, dass Sie eindeutige Namen verwenden
- Die letzte Ebene soll immer zwischen Benutzer- und Computerkonten aufteilen
- Verwenden Sie eindeutige Namen


| Standort 1 | Standort 2 |
| ----------- | ----------- |
|   •	GL (intern)             |•	GL (intern) |
|   •	Sekretariat (intern)    |•	Aussendienst (extern) |
|   •	Aussendienst (extern)   |•	Promoter (extern |
|   •	Buchhaltung (intern)    |•	Messemitarbeiter (extern) |
|   •	Promoter (extern)       |•	Partner (extern) |
|   •	Partner (extern)        |•	Informatik (intern) |
|   •	Informatik (intern)     | 


## Struktur im AD anlegen `(0.5 Punkt)`
Wenn Sie sicher sind, dass Sie eine gute Struktur haben, legen Sie Ihre im DIT definierte Struktur im AD an. 

## Verschieben Sie alle Benutzer in die passenden OUs `(0.5 Punkte)`
- Kontrolle graphisches DIT 
- Zeigen Sie die erstellen OU’s im Video
