# Modul 117 - Tag 2: 2. NETZWERKADRESSGRUNDLAGEN


---

## Aufgaben: 2. NETZWERKADRESSGRUNDLAGEN

### Aufgabe B1: Private Adressbereiche
* **Private IPv4-Adressbereiche:**
  - `10.0.0.0 - 10.255.255.255` (Ehemals Class A-Adresse)
  - `172.16.0.0 - 172.31.255.255` (Ehemals Class B-Adresse)
  - `192.168.0.0 - 192.168.255.255` (Ehemals Class C-Adresse)
* **Spezialadressen:**
  - `127.0.0.1` Localnet oder Loopbackadresse (Eigener Rechner)
  - `169.254.0.0 - 169.254.255.255` ZEROCONF/APIPA-Adressen bei DHCP-Ausfall

### Aufgaben B2: Netz- und Host-Identifikation
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

### Aufgaben B3: Anzahl IP-Adressen und Hosts im Subnetz
1. **`10.0.0.0 / 8`**
   - IP-Adressen gesamt: $2^{24} = 16'777'216$
   - Nutzbare PC-Adressen: $16'777'214$
2. **`10.0.0.0 / 16`**
   - IP-Adressen gesamt: $2^{16} = 65'536$
   - Nutzbare PC-Adressen: $65'534$
3. **`10.0.0.0 / 24`**
   - IP-Adressen gesamt: $2^8 = 256$
   - Nutzbare PC-Adressen: $254$

### Aufgabe B4 & B5: Kommunikationsfähigkeit von PCs
1. **Ja, sie können.** Beide Netz-IDs sind `192.168.1`.
2. **Ja, sie können.** Beide Netz-IDs sind `192.168`.
3. **Nein, sie können nicht.** PC1 Netz-ID ist `192.168.3`, PC2 Netz-ID ist `192.168.246`.
4. **Ja, sie können.** Beide Netz-IDs sind `10`.
5. **Nein, sie können nicht.** Identische IP-Adressen (IP-Konflikt).
6. **Vorsicht bei PC1:** `258` ist ausserhalb des gültigen Bereichs von `0..255` (Ungültige IP-Adresse).
7. **Vorsicht:** PC1 hat eine private IP-Adresse, PC2 hingegen eine öffentliche. Die beiden Geräte können somit nicht direkt miteinander kommunizieren. PC1 benötigt einen Internetzugang (Router mit NAT), der die private IP in eine öffentliche wandelt.
8. **Keine direkte Kommunikation möglich:** Der Ping von PC1 nach PC2 würde funktionieren, da aus Sicht von PC1 der PC2 im selben Subnetz liegt. Allerdings käme die Ping-Antwort von PC2 nicht an PC1 zurück, weil aus Sicht von PC2 der PC1 in einem anderen Subnetz liegt.

### Aufgabe B6: Wissensfragen Netzwerke
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

### Aufgabe B7: Topologie-Entwurf
Die Subnetzmaske `/24` bietet genau Platz für 254 Hosts (253 PCs + 1 Routerschnittstelle). Die vier Subnetze lauten somit beispielsweise:
- **LAN-A:** `10.0.0.0/24` (Router `eth0`: `10.0.0.1`)
- **LAN-B:** `10.0.1.0/24` (Router `eth1`: `10.0.1.1`)
- **LAN-C:** `10.0.2.0/24` (Router `eth2`: `10.0.2.1`)
- **LAN-D:** `10.0.3.0/24` (Router `eth3`: `10.0.3.1`)
