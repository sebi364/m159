# **Aufgabe 5:** Gruppen und Berechtigungen im AD `(5 Punkt)`

Für diese Aufgabe müssen Sie wissen, wie man Freigaben und Berechtigungen unter Windows verwendet. Falls Ihnen der Unterschied zwischen Freigabe- und NTFS-Berechtigungen nicht bekannt ist, Fragen Sie Ihre Klassenkameraden oder lesen Sie es im Internet nach. Falls Sie nicht sicher sind, Fragen Sie die Lehrperson.

> [!TIP]
> Im Ordner resources finden Sie verschiedene PowerShell Skripte, mit dem Sie diese Aufgabe beschleunigen können. Dieses Skript wurde einst von einem sehr guten Schüler erstellt, es fehlen aber noch Einstellungen. Kannst Du das PS-File verbessern? Falls ja zeig deine Idee dem Lehrer.

## User und Gruppen anlegen `(1 Punkt)`
- Erstellen Sie Ihre Benutzer wie im Portfolio definiert
Falls Sie Probleme mit dem Anlegen der Benutzer haben, weil Ihre Passwörter zu schwach sind, ziehen Sie Aufgabe «9.1 Default Domain Policy - Verändern der Passwortrichtlinien» vor. Falls Sie überfragt sind, kann Ihnen die Lehrperson kurz helfen, da dieses Thema erst später im Modul behandelt wird.
- Erstellen Sie für jede Abteilung, sowie für intern und extern “globale” Sicherheitsgruppen. Intern und extern werden wie die Abteilungen als normale Sicherheitsgruppenerstellt. Anschliessend fügen Sie alle internen Abteilungen in die Gruppe intern und alle externen Abteilungen in die Gruppe extern.
    -  GL (intern) 
    - Aussendienst (extern) 
    - Sekretariat (intern) 
    - Buchhaltung (intern) 
    - Promoter (extern) 
    - Partner (extern) 
    - Informatik (intern) 
    - Messemitarbeiter (extern)
- Fügen Sie die Benutzer in die entsprechenden Gruppen (Siehe Portfolio)
- Fügen Sie die Abteilungsgruppen in Gruppen intern und extern
- Testen Sie einige Benutzer, indem Sie sich mit diesem am Windows 10/11 Client anmelden


## UNC
Sie müssen wissen, wie UNC-Pfade aufgebaut sind und verwendet werden können
- https://de.wikipedia.org/wiki/Uniform_Naming_Convention
- https://gitlab.com/ch-tbz-it/Stud/m159/-/blob/main/02_Unterrichtsressourcen/04_%C3%9Cbungen/%C3%9Cbung UNC.docx

## Ordner und Freigaben erstellen + ABE aktivieren `(2 Punkt)`
- Erstellen Sie die Ordner- und Freigabestruktur wie in der Tabelle aufgeführt
- Setzen Sie für jede Freigabe die Freigabeberechtigungen für «Jeder» auf «ändern/change»
- Deaktivieren Sie die Vererbung auf der Freigabe «Daten» und allen Unterordnern
- Entfernen Sie die Standardgruppe «Domänenbenutzer»
- Vergeben Sie die NTFS-Berechtigungen aus der Matrix für sämtliche Ordner.
- Es reicht für die volle Punktzahl, nur die Berechtigungen der grün markierten Zeilen zu erfassen

| Pfad:                  | Freigabe  | LB | GL | Aussendienst | Sekretariat | Buchhaltung | Promoter | Partner | Informatik | Messemitarbeiter | Intern | Extern |
|------------------------|-----------|----|----|--------------|-------------|-------------|----------|---------|------------|------------------|--------|--------|
| `C:\Daten\`            |           | D: | c  | -            | -           | c           | -        | -       | c          | -                | -      | -      |
| `C:\Daten\Pool`        | Pool      | P: | c  | c            | c           | c           | c        | c       | c          | c                | -      | -      |
| `C:\Daten\Abteilungen` | Abteilung | A: | c  | r            | r           | r           | r        | r       | r          | r                | -      | -      |
| ..\GL                  |           |    | c  | -            | -           | -           | -        | -       | -          | -                | -      | -      |
| ..\Aussendienst        |           |    | c  | c            | -           | -           | -        | -       | -          | -                | -      | -      |
| `..\Sekretariat`       |           |    | c  | r            | c           | -           | r        | r       | r          | r                | -      | -      |
| `..\Buchhaltung`       |           |    | c  | r            | r           | c           | r        | r       | r          | r                | -      | -      |
| `..\Promoter`          |           |    | c  | -            | -           | -           | c        | -       | -          | -                | -      | -      |
| ..\Partner             |           |    | c  | -            | -           | -           | -        | c       | -          | -                | -      | -      |
| ..\Informatik          |           |    | c  | -            | -           | -           | -        | -       | c          | -                | -      | -      |
| ..\Messemitarbeiter    |           |    | c  | -            | -           | -           | -        | -       | -          | c                | -      | -      |
| C:\Daten\Profiles      |           |    | c  | -            | -           | -           | -        | -       | -          | -                | -      | -      |
| `C:\Daten\Intern`      | Intern    | I: | c  | -            | -           | -           | -        | -       | -          | -                | c      | -      |
| `C:\Daten\Extern`      | Extern    | E: | c  | -            | -           | -           | -        | -       | -          | -                | -      | c      |

LB = Laufwerksbuchstabe (Wird erst bei Aufgabe 9 für die Netzlaufwerk benötigt)</br>
r = Read</br>
c = Change</br>
"-"  = Kein Zugriff

## Einige Berechtigungen testen
- Melden Sie sich mit dem Benutzer der Abteilung «Sekretariat» an. Prüfen Sie, ob Sie auf den UNC-Pfad «Buchhaltung» Leserechte haben.
- Melden Sie sich mit dem Benutzer der Abteilung «GL» an. Prüfen Sie, ob Sie auf den UNC-Pfad «Pool» Schreibrechte haben.
- Melden Sie sich mit dem Benutzer der Abteilung «Promoter» an. Prüfen Sie, ob Sie auf das Laufwerk «Aussendienst» keine Rechte haben.
- Machen zwei bis fünf Tests Ihrer Wahl, damit Sie sicher sind, dass alles stimmt.

## ABE
- Informieren Sie sich über ABE
- Aktivieren Sie anschliessend ABE für alle Freigaben

## Erstellen Sie Ihr eigenes "[Group Nesting](https://gitlab.com/ch-tbz-it/Stud/m159/-/blob/main/02_Unterrichtsressourcen/03_Fachliteratur&Tutorials/AGDLP-AGUDLP/Group-Nesting.md?ref_type=heads)" Konzept `(2 Punkte)`
- Überlegen Sie sich, wie Sie die vorgegebene Berechtigungsstruktur verbessern können.
- Erstellen Sie eine visualisierte Version der neuen Berechtigungsstruktur mit Rollengruppen & Berechtigungsgruppen basierend auf [AGDLP](https://www.youtube.com/watch?v=zHHzjjqVhTc&t=5s).
- Rekonfigurieren Sie zwei Abteilungen Ihre Umgebung entsprechend der neuen Planung.
