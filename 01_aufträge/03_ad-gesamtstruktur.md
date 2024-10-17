# **Aufgabe 3:** Neue Gesamtstruktur aufsetzen
Unter einer neuen Gesamtstruktur versteht man eine neue Domäne aufsetzen.
> [!WARNING]
> Weitere DCs werden erst später in die Domäne aufgenommen.

Videos zur Aufgabe 3: [Einen ersten Domänencontroller installieren](https://sway.office.com/qv95MgyYR8FZpGu8?ref=Link)

## AD DS-Rolle auf dem DC1 hinzufügen
- Server Manager Rolle hinzufügen

## DC1 promoten `(1 Punkt)`
- Neue Gesamtstruktur
- Domainname Spezifikationen (a-z, 0-9, ‘-‘)
- Standardspeicherorte belassen

## DNS `(0.5 Punkt)`
- Richten Sie eine DNS-Weiterleitung an 8.8.8.8 (oder alternative Ihrer Wahl) für Ihren ersten DNS-Server ein.
- Forward-Zone einrichten (Wird beim Promoten eines DC automatisch erstellt)
- Für Jedes Subnetz müssen Sie eine «Reverse-Zone» einrichten
- Wenn Sie Ihren DC in der Forward-Zone finden, machen Sie eine Aktualisierung des PTR-Records, damit der Host auch in der Reverse-Zone zu finden ist.
- «NS LOOKUP» auf dem Server vorwärts und rückwärts testen

### Diverse AD-Einstellungen `(0.5 Punkt)`
- Ändern Sie den Namen des Administrators auf den von Ihnen vorgesehenen Namen ab (0.5 Punkte)
- Aktivieren Sie den AD-Papierkorb