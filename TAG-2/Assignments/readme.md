# Modul 117 - Tag 2: 2. NETZWERKADRESSGRUNDLAGEN

---

## Aufgaben: 2. NETZWERKADRESSGRUNDLAGEN

### Aufgabe B1: Private Adressbereiche
Bekanntlich erstreckt sich der $IPv4$-Adressraum zwischen `0.0.0.0` und `255.255.255.255`, wobei viele IP-Adressen nicht Hosts zugewiesen werden dürfen, weil sie für Sonderzwecke reserviert sind.
Um der IPv4-Adressverknappung entgegenzuwirken, wurden verschiedene Adressbereiche für ausschliesslich internen Gebrauch reserviert. Dies bedeutet, dass man diese Adressen im Internet niemals antreffen wird.

**Finden sie heraus, wie die IP-Adressbereiche lauten.**
*Hinweis: Drei davon sind für die reguläre, private Verwendung. Einer betrifft nur den eigenen Rechner. Einer davon sichert einen Notbetrieb bei Ausfall der automatisierten Netzwerkparameter-Zuweisung (Stichwort: DHCP).*

---

### Aufgaben B2: Netz- und Host-Identifikation
Ermitteln Sie die Netz-ID, Host-ID, Netzwerkadresse und Broadcastadresse für die folgenden Angaben:

1. **`10.11.12.4 / 24`** (`/24` bedeutet `255.255.255.0`)
   - Netz-ID: ?
   - Host-ID: ?
   - Netzwerkadresse: ?
   - Broadcastadresse: ?

2. **`10.11.12.4 / 16`** (`/16` bedeutet `255.255.0.0`)
   - Netz-ID: ?
   - Host-ID: ?
   - Netzwerkadresse: ?
   - Broadcastadresse: ?

3. **`10.11.12.4 / 8`** (`/8` bedeutet `255.0.0.0`)
   - Netz-ID: ?
   - Host-ID: ?
   - Netzwerkadresse: ?
   - Broadcastadresse: ?

---

### Aufgaben B3: Anzahl IP-Adressen und Hosts im Subnetz
Berechnen Sie für die folgenden Netzwerke die theoretisch mögliche Anzahl IP-Adressen sowie die tatsächlich nutzbaren PC-/Host-Adressen:

1. **`10.0.0.0 / 8`**
   - Anzahl IP-Adressen im Subnetz: ?
   - Anzahl nutzbare PC-Adressen: ?

2. **`10.0.0.0 / 16`**
   - Anzahl IP-Adressen im Subnetz: ?
   - Anzahl nutzbare PC-Adressen: ?

3. **`10.0.0.0 / 24`**
   - Anzahl IP-Adressen im Subnetz: ?
   - Anzahl nutzbare PC-Adressen: ?

---

### Aufgabe B4 & B5: Kommunikationsfähigkeit von PCs
Können die beiden PCs jeweils direkt miteinander kommunizieren? (Ja/Nein/Warum?)

1. **PC1:** `192.168.1.23` (`255.255.255.0`) &nbsp;|&nbsp; **PC2:** `192.168.1.176` (`255.255.255.0`)
2. **PC1:** `192.168.3.23` (`255.255.0.0`) &nbsp;|&nbsp; **PC2:** `192.168.246.29` (`255.255.0.0`)
3. **PC1:** `192.168.3.23` (`255.255.255.0`) &nbsp;|&nbsp; **PC2:** `192.168.246.29` (`255.255.255.0`)
4. **PC1:** `10.34.233.27` (`255.0.0.0`) &nbsp;|&nbsp; **PC2:** `10.167.246.178` (`255.0.0.0`)
5. **PC1:** `10.34.233.27` (`255.0.0.0`) &nbsp;|&nbsp; **PC2:** `10.34.233.27` (`255.255.255.0`)
6. **PC1:** `10.34.258.21` (`255.255.255.0`) &nbsp;|&nbsp; **PC2:** `10.34.233.27` (`255.255.255.0`)
7. **PC1:** `172.16.1.55` (`255.0.0.0`) &nbsp;|&nbsp; **PC2:** `172.33.5.27` (`255.0.0.0`)
8. **PC1:** `10.0.1.17` (`255.255.0.0`) &nbsp;|&nbsp; **PC2:** `10.0.2.24` (`255.255.255.0`)

---

### Aufgabe B6: Wissensfragen Netzwerke
1. Erklären sie in wenigen Sätzen das Zugriffsverfahren gemäss CSMA/CD.
2. Wo können sie bei Microsoft-Windows den Hostnamen (Computernamen) eintragen?
3. Warum nennt man die MAC-Adresse eine statische Adresse?
4. Öffnen sie an ihrem Notebook eine Konsole und geben sie den Befehl `arp -a` ein. Was bewirkt dies?
5. Warum nennt man die IPv4-Adresse eine dynamische Adresse?
6. Was liefert uns das WIN-Konsolenkommando `ipconfig /all`?
7. Was kann man mit dem `ping`-Kommando überprüfen?
8. Wo können sie bei Microsoft-Windows die IP-Adresse ändern?
9. Welche IP-Adressbereiche sind für private Zwecke reserviert?
10. Was bezweckt man mit der Bildung von Subnetzen?
11. Die Subnetzmaske teilt die IP-Adresse in zwei Teile auf. Wie nennt man diese?
12. Schreiben sie die Subnetzmaske `255.255.0.0` in CIDR-Notation.
13. Wie sind Netzwerkadresse und Broadcastadresse definiert?
14. Was kann ich mit der Loopbackadresse überprüfen?
15. Was ist der Vorteil von statischen Netzwerkeinstellungen?
16. Was ist der Vorteil von dynamischen Netzwerkeinstellungen?
17. Wann wird DHCP benötigt?
18. Was versteht man unter einer APIPA-Adresse und welchen Adressbereich betrifft dies?
19. Welche Netzwerkkomponente verbindet Subnetze?
20. Was meint Microsoft mit der Bezeichnung Standardgateway?

---

### Aufgabe B7: Topologie-Entwurf
Erstellen bzw. zeichnen sie eine LAN-Netztopologie für die gilt:
- Gegeben ist ein LAN mit der Netzwerkadresse `10.0.0.0/16`. (Ausgangssituation)
- Darin sollen vier Subnetze, LAN-A, LAN-B, LAN-C und LAN-D mit je 253 PCs erstellt werden. (Aufteilen des Ausgangsnetz)
- Die vier Subnetze werden mit einem Router verbunden, der 4 Ethernetschnittstellen besitzt: `eth0` in LAN-A, `eth1` in LAN-B, `eth2` in LAN-C, `eth3` in LAN-D.

Beschriften sie die Topologie vollständig (Hostname z.B. PC-A1, IP, Subnetzmaske, Router-IP/Standardgateway, Ethernetschnittstellen).

---
---

## MUSTERLÖSUNGEN: 2. NETZWERKADRESSGRUNDLAGEN

### Musterlösung B1: Private und Spezialadressen
* **Private IPv4-Adressbereiche:**
  - `10.0.0.0 - 10.255.255.255` (Ehemals Class A-Adresse)
  - `172.16.0.0 - 172.31.255.255` (Ehemals Class B-Adresse)
  - `192.168.0.0 - 192.168.255.255` (Ehemals Class C-Adresse)
* **Spezialadressen:**
  - `127.0.0.1` Localnet oder Loopbackadresse (Eigener Rechner)
  - `169.254.0.0 - 169.254.255.255` ZEROCONF/APIPA-Adressen bei DHCP-Ausfall
* *Tipp: Diese fünf Adressbereiche gleich auswendig lernen!*

### Musterlösungen B2: Netz- und Host-Identifikation
1. **`10.11.12.4 / 24`**
   - Netz-ID: `10.11.12`
   - Host-ID: `4`
   - Netzwerkadresse: `10.11.12.0`
   - Broadcastadresse: `10.11.12.255`
2. **`10.11.12.4 / 16`**
   - Netz-ID: `10.11`
   - Host-ID: `12.4`
   - Netzwerkadresse: `10.11.0.0`
   - Broadcastadresse: `10.11.255.255`
3. **`10.11.12.4 / 8`**
   - Netz-ID: `10`
   - Host-ID: `11.12.4`
   - Netzwerkadresse: `10.0.0.0`
   - Broadcastadresse: `10.255.255.255`

### Musterlösungen B3: IP- und PC-Anzahl
1. **`10.0.0.0 / 8`**
   - IP-Adressen gesamt: $2^{24} = 16'777'216$
   - Nutzbare PC-Adressen: $16'777'214$
2. **`10.0.0.0 / 16`**
   - IP-Adressen gesamt: $2^{16} = 65'536$
   - Nutzbare PC-Adressen: $65'534$
3. **`10.0.0.0 / 24`**
   - IP-Adressen gesamt: $2^8 = 256$
   - Nutzbare PC-Adressen: $254$

### Musterlösung B4 & B5: Kommunikationsfähigkeit
1. **Ja, sie können.** Beide Netz-IDs sind `192.168.1`.
2. **Ja, sie können.** Beide Netz-IDs sind `192.168`.
3. **Nein, sie können nicht.** PC1 Netz-ID ist `192.168.3`, PC2 Netz-ID ist `192.168.246`.
4. **Ja, sie können.** Beide Netz-IDs sind `10`.
5. **Nein, sie können nicht.** Identische IP-Adressen (IP-Konflikt).
6. **Vorsicht bei PC1:** `258` ist ausserhalb des gültigen Bereichs von `0..255` (Ungültige IP-Adresse).
7. **Vorsicht:** PC1 hat eine private IP-Adresse, PC2 hingegen eine öffentliche. Die beiden Geräte können somit nicht direkt miteinander kommunizieren. PC1 benötigt einen Internetzugang (Router mit NAT), der die private IP in eine öffentliche wandelt.
8. **Keine direkte Kommunikation möglich:** Der Ping von PC1 nach PC2 würde funktionieren, da aus Sicht von PC1 der PC2 im selben Subnetz liegt. Allerdings käme die Ping-Antwort von PC2 nicht an PC1 zurück, weil aus Sicht von PC2 der PC1 in einem anderen Subnetz liegt.

### Musterlösung B6: Antworten zu den Wissensfragen
1. **CSMA/CD:** Netzwerkprotokoll, das in lokalen Netzwerken (Half-Duplex Ethernet) den Zugriff auf ein gemeinsames Übertragungsmedium regelt und Kollisionen erkennt.
2. **Hostname eintragen:** In den Windows-Systemeigenschaften über den Kurzbefehl `sysdm.cpl`.
3. **MAC-Adresse (statisch):** Ist unveränderbar und permanent auf der Netzwerkkarte (NIC) eingebrannt.
4. **`arp -a`:** Zeigt den aktuellen Inhalt des ARP-Caches des PCs mit den bisher kontaktierten Geräten in Form von MAC-Adresse zu IP-Adresse an.
5. **IPv4-Adresse (dynamisch):** Kann jederzeit manuell geändert oder dynamisch durch einen Server neu zugewiesen werden.
6. **`ipconfig /all`:** Liefert alle detaillierten eigenen Netzwerkparameter (IP, Subnetzmaske, MAC-Adresse, DNS, DHCP-Server, Gateway).
7. **`ping`:** Mit dem Ping-Kommando kann die Erreichbarkeit eines Kommunikationspartners auf IP-Ebene überprüft werden.
8. **IP-Adresse ändern:** In den Netzwerkeinstellungen (Netzwerkverbindungen) über den Kurzbefehl `ncpa.cpl`.
9. **Private IP-Bereiche:** `10.x.x.x`, `172.[16..31].x.x`, und `192.168.x.x`.
10. **Subnetzbildung:** Subnetze teilen den Netzwerk-Traffic und die Broadcast-Domänen auf, um Performance und Sicherheit zu erhöhen.
11. **Teile der IP-Adresse:** Netz-ID (Netzwerkanteil) und Host-ID (Hostanteil).
12. **`255.255.0.0`:** Entspricht der CIDR-Notation `/16`.
13. **Definition:**
    - Netzwerkadresse: Alle Hostbits sind logisch `0`.
    - Broadcastadresse: Alle Hostbits sind logisch `1`.
14. **Loopbackadresse:** Prüft die TCP/IP-Netzwerkfunktionalität des eigenen Protokollstacks bis zur Netzwerkkarte, jedoch nicht die physische Verkabelung darüber hinaus.
15. **Vorteil statische IPs:** Geräte sind permanent unter exakt derselben IP-Adresse erreichbar. Ein Must für Server, Router und Drucker.
16. **Vorteil dynamische IPs:** Hohe Flexibilität, einfache zentrale Verwaltung und Vermeidung von Adressdoppelvergaben.
17. **DHCP benötigt:** Ein Dienst auf einem Server, der Clients automatisch mit dynamischen IP-Adressen und weiteren Angaben (Router/Standardgateway, DNS) versorgt.
18. **APIPA-Adresse:** Ein Notfallszenario zur Aufrechterhaltung der Kommunikation im physikalischen Subnetz bei Ausfall des DHCP-Servers. Bereich: `169.254.x.x`.
19. **Verbindungskomponente:** Der **Router** verbindet verschiedene Subnetze miteinander.
20. **Standardgateway:** Damit meint Microsoft den Default-Router, welcher IP-Pakete in ein anderes/fremdes Netz weiterleitet, wenn sie das eigene Subnetz verlassen müssen.

### Musterlösung B7: Topologie-Planung Hinweis
*Zur korrekten Aufteilung von `10.0.0.0/16` in 4 Subnetze für je 253 PCs:*
Die Subnetzmaske `/24` bietet genau Platz für 254 Hosts (253 PCs + 1 Routerschnittstelle). Die vier Subnetze lauten somit beispielsweise:
- **LAN-A:** `10.0.0.0/24` (Router `eth0`: `10.0.0.1`)
- **LAN-B:** `10.0.1.0/24` (Router `eth1`: `10.0.1.1`)
- **LAN-C:** `10.0.2.0/24` (Router `eth2`: `10.0.2.1`)
- **LAN-D:** `10.0.3.0/24` (Router `eth3`: `10.0.3.1`)
