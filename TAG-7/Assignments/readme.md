
## Aufgabe B2: Analyse von IP-Adressen und Masken

### 1. IP-Adresse: `10.11.12.4 / 24` (Maske: `255.255.255.0`)
* **Netz-ID:** `10.11.12.`
* **Host-ID:** `.4`
* **Netzwerkadresse:** `10.11.12.0`
* **Broadcastadresse:** `10.11.12.255`

### 2. IP-Adresse: `10.11.12.4 / 16` (Maske: `255.255.0.0`)
* **Netz-ID:** `10.11.`
* **Host-ID:** `.12.4`
* **Netzwerkadresse:** `10.11.0.0`
* **Broadcastadresse:** `10.11.255.255`

### 3. IP-Adresse: `10.11.12.4 / 8` (Maske: `255.0.0.0`)
* **Netz-ID:** `10.`
* **Host-ID:** `.11.12.4`
* **Netzwerkadresse:** `10.0.0.0`
* **Broadcastadresse:** `10.255.255.255`

---

## Aufgabe B3: Host-Berechnung im Subnetz

* **10.0.0.0/8:** * Anzahl IP-Adressen im Subnetz: $2^{24} = 16'777'216$
  * Verfügbare PC-Adressen (Hosts): $16'777'216 - 2 = 16'777'214$
* **10.0.0.0/16:** * Anzahl IP-Adressen im Subnetz: $2^{16} = 65'536$
  * Verfügbare PC-Adressen (Hosts): $65'536 - 2 = 65'534$
* **10.0.0.0/24:** * Anzahl IP-Adressen im Subnetz: $2^8 = 256$
  * Verfügbare PC-Adressen (Hosts): $256 - 2 = 254$

---

## Aufgabe B4 & B5: Kommunikationsprüfung (Ja/Nein mit Begründung)

1. **PC1:** `192.168.1.23 /24` | **PC2:** `192.168.1.176 /24`
   * **Ja.** Beide PCs befinden sich im exakt selben Subnetz (`192.168.1.0`), da die ersten drei Oktette durch die Maske `255.255.255.0` identisch sein müssen.
2. **PC1:** `192.168.3.23 /16` | **PC2:** `192.168.246.29 /16`
   * **Ja.** Bei der Maske `255.255.0.0` müssen nur die ersten beiden Oktette übereinstimmen. Beide Netze lauten `192.168.0.0`.
3. **PC1:** `192.168.3.23 /24` | **PC2:** `192.168.246.29 /24`
   * **Nein.** PC1 ist im Netz `192.168.3.0`, PC2 im Netz `192.168.246.0`. Ohne Router können sie nicht kommunizieren.
4. **PC1:** `10.34.233.27 /8` | **PC2:** `10.167.246.178 /8`
   * **Ja.** Die Maske `/8` (`255.0.0.0`) vergleicht nur das erste Oktett. Beide PCs teilen sich das Netz `10.0.0.0`.
5. **PC1:** `10.34.233.27 /8` | **PC2:** `10.34.233.27 /24`
   * **Nein / Eingeschränkt.** Es liegt eine Fehlkonfiguration vor. PC1 denkt, PC2 sei im selben Netz. PC2 wiederum denkt durch seine engere Maske (`/24`), dass PC1 in einem fremden Netz liegt und will die Antwort an ein Gateway senden. Eine fehlerfreie, bidirektionale Kommunikation scheitert.
6. **PC1:** `10.34.258.21 /24` | **PC2:** `10.34.233.27 /24`
   * **Nein (Ungültige IP).** Die Zahl `258` im dritten Oktett von PC1 ist ungültig, da ein Oktett maximal den Wert 255 annehmen darf.
7. **PC1:** `172.16.1.55 /8` | **PC2:** `172.33.5.27 /8`
   * **Ja.** Durch die Maske `255.0.0.0` befinden sich beide im Netzwerk `172.0.0.0`.
8. **PC1:** `10.0.1.17 /16` | **PC2:** `10.0.2.24 /24`
   * **Nein.** Ähnlich wie bei Fall 5 liegt ein Masken-Mismatch vor. PC1 sieht PC2 im eigenen Netz (`10.0.0.0/16`), PC2 sieht PC1 jedoch ausserhalb seines Netzes (`10.0.2.0/24`) und blockiert den direkten Rückweg.

---

## Aufgabe B6: Repetitionsfragen & Antworten

1. **CSMA/CD Erklärung:** Carrier Sense (prüfen, ob das Medium frei ist), Multiple Access (mehrere dürfen zugreifen) und Collision Detection (Kollisionen während des Sendens erkennen). Bei einer Kollision stoppen alle, senden ein Jam-Signal und warten eine Zufallszeit ab.
2. **Eintragen des Hostnamens bei Windows:** In den Systemeinstellungen unter *Info* $\rightarrow$ *Diesen PC umbenennen* (oder über die klassische Systemsteuerung unter *System* $\rightarrow$ *Erweiterte Systemeinstellungen* $\rightarrow$ *Computername*).
3. **Warum ist die MAC-Adresse statisch?** Weil sie vom Hersteller fest in die Hardware (die Netzwerkkarte) eingebrannt wird und sich physikalisch nicht verändert.
4. **Befehl `arp -a`:** Er zeigt den aktuellen Inhalt des ARP-Caches (Address Resolution Protocol) an. Das ist die Zuordnungstabelle von bekannten IP-Adressen zu den dazugehörigen physikalischen MAC-Adressen im lokalen Netz.
5. **Warum ist die IP-Adresse dynamisch?** Weil sie rein logisch aufgebaut ist. Sie kann jederzeit manuell geändert oder durch einen DHCP-Server bei jedem Netzwerkstart neu zugewiesen werden.
6. **Befehl `ipconfig /all`:** Liefert eine vollständige Übersicht aller Netzwerkkonfigurationen des Systems, inklusive Hostname, DNS-Suffix, DHCP-Status, MAC-Adressen, IP-Adressen, Subnetzmasken, Standardgateways und DHCP/DNS-Servern.
7. **Befehl `ping`:** Überprüft die grundlegende Erreichbarkeit eines Hosts im Netzwerk und misst die Paketumlaufzeit (Latenz).
8. **IP-Adresse ändern bei Windows:** In den *Netzwerkverbindungen* (über `ncpa.cpl`) $\rightarrow$ Eigenschaften des Adapters $\rightarrow$ *Internetprotokoll, Version 4 (TCP/IPv4)* $\rightarrow$ Eigenschaften.
9. **Private IP-Adressbereiche:** `10.0.0.0/8`, `172.16.0.0/12` (bzw. `172.16.x.x` bis `172.31.x.x`), und `192.168.0.0/16`.
10. **Zweck von Subnetzen:** Eindämmung des Broadcast-Verkehrs zur Vermeidung von Überlastung, Erhöhung der Netzwerksicherheit (Trennung von Abteilungen) und strukturierte Organisation.
11. **Die zwei Teile der IP durch die Maske:** Netz-ID (Netzwerkanteil) und Host-ID (Geräteanteil).
12. **Subnetzmaske `255.255.0.0` in CIDR:** `/16`
13. **Definition Netzwerk- und Broadcastadresse:** Die Netzwerkadresse identifiziert das Netz (Host-Bits = 0). Die Broadcastadresse adressiert alle Teilnehmer im Netz gleichzeitig (Host-Bits = 1).
14. **Was prüft die Loopbackadresse (`127.0.0.1`)?** Sie prüft, ob der lokale TCP/IP-Protokollstack auf dem eigenen Betriebssystem korrekt installiert ist und funktioniert.
15. **Vorteil statischer Einstellungen:** Konstante Erreichbarkeit (wichtig für Server), Unabhängigkeit von einem DHCP-Server.
16. **Vorteil dynamischer Einstellungen:** Keine manuelle Konfiguration an den Endgeräten nötig, zentrale Verwaltung, Vermeidung von doppelten IP-Adressen im Netz.
17. **Wann wird DHCP benötigt?** Sobald Netzwerke automatisiert und ohne manuellen Aufwand administriert werden sollen (z. B. bei Laptops, Smartphones, grossen Firmennetzwerken).
18. **APIPA-Adresse und Bereich:** Automatic Private IP Addressing. Tritt in Kraft, wenn ein Gerät auf DHCP eingestellt ist, aber keinen DHCP-Server erreicht. Bereich: `169.254.0.0` bis `169.254.255.255`.
19. **Welche Netzwerkkomponente verbindet Subnetze?** Ein Router (oder ein Layer-3-Switch).
20. **Bedeutung Standardgateway:** Das ist der Router im lokalen Subnetz, an den alle Datenpakete geschickt werden, deren Ziel-IP-Adresse ausserhalb des eigenen Subnetzes liegt.

---

## Aufgabe C2: Wireshark-Analyse

1. **Untersuchung von `http://www.example.ch`:** Da es sich um unverschlüsseltes HTTP (Port 80) handelt, sind alle MAC-Adressen (Layer 2), IP-Adressen (Layer 3), TCP-Ports (Layer 4, z.B. Quellport 54321 und Zielport 80) sowie die HTTP-Anfragemethode (`GET / HTTP/1.1`) und der Klartextinhalt der Website im Application Layer vollständig sichtbar.
2. **Untersuchung von `https://www.zkb.ch`:** Hier kommt TLS (Port 443) zum Einsatz. MAC-Adressen, IP-Adressen und TCP-Ports sind weiterhin im Header sichtbar. Der Application Layer (die eigentlichen Bankdaten) ist jedoch komplett verschlüsselt. Über die TLS-Erweiterung im "Client Hello" (`ssl.handshake.extensions_server_name`) lässt sich aber im Klartext herauslesen, *welche* Domain besucht wird (SNI = Server Name Indication). TLS ist primär zwischen Transportschicht und Anwendungsschicht angesiedelt (OSI-Schicht 4/5).
3. **Gefahr des Abhörens am selben Switch:** Im Normalbetrieb leitet ein Switch Pakete gezielt nur an den Port weiter, an dem die Ziel-MAC angeschlossen ist. Ein Nachbar kann den Datenverkehr also *nicht* einfach mitlesen. Die Gefahr besteht jedoch, wenn:
   * **MAC-Flooding** betrieben wird: Der Angreifer überflutet den Switch mit gefälschten MAC-Adressen, bis dessen Tabelle (SAT) voll ist. Der Switch fällt dann in den "Hub-Modus" (Fail-Open) zurück und leitet alle Pakete an alle Ports weiter.
   * Der Port des Nachbarn als **Monitor-Port (Mirror Port)** konfiguriert ist, welcher den gesamten Verkehr spiegelt.
