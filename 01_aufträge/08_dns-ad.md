# **Aufgabe 8:** DNS in Active Directory `(1 Punkt)`
Schauen Sie sich folgende [Videos](https://sway.cloud.microsoft/qv95MgyYR8FZpGu8) zum Thema DNS in Active Directory an
- Primäre\_und\_sekundäre\_Zone\_konfigurieren.wmv
- Einstellungen\_der\_Zonenübertragung\_konfigurieren.wmv
- Benachrichtigungseinstellungen\_konfigurieren.wmv
- Bedingte\_Weiterleitung\_konfigurieren.wmv

## **Neue «nicht AD integrierte» Forward-Zone übertragen** 
1. Erstellen Sie auf dem DC1 eine neue Forward-Zone mit dem Namen «lab.tbz», welche nicht in Active Directory integriert ist.
1. Fügen Sie den DC2 zu den Nameservern dieser neuen Zone hinzu und erlauben Sie sämtlichen Nameservern eine Zonenübertragung.
1. Erstellen Sie auf dem DNS des DC2 eine sekundäre Zone von «lab.tbz»
1. Erstellen Sie einen Printscreen von der sekundären Zone auf dem DC2 und speichern Sie diesen Printscreen im Portfolio ab.

   ![Picture1](./bilder/ad-dns.png)