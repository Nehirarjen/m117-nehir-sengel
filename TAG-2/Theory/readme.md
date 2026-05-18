# Theoriezusammenfassung: Netzwerkadressgrundlagen

**Modul:** 117 | **Block:** 2  
**Thema:** IPv4-Adressierung, Subnetzmaske, private Adressbereiche

---

## 1. IPv4-Adressraum

Eine IPv4-Adresse besteht aus **32 Bit**, dargestellt als vier Dezimalzahlen (0–255), getrennt durch Punkte.  
Gesamter Adressraum: `0.0.0.0` bis `255.255.255.255`

Viele Adressen sind für **Sonderzwecke reserviert** und dürfen keinem Host zugewiesen werden.

---

## 2. Private & reservierte Adressbereiche

| Bereich | Adressraum | Zweck |
|---------|-----------|-------|
| **Class A privat** | `10.0.0.0 – 10.255.255.255` | Privates LAN (grosse Netze) |
| **Class B privat** | `172.16.0.0 – 172.31.255.255` | Privates LAN (mittlere Netze) |
| **Class C privat** | `192.168.0.0 – 192.168.255.255` | Privates LAN (kleine Netze, Heimnetz) |
| **Loopback** | `127.0.0.1` | Nur eigener Rechner (Netzwerkstack testen) |
| **APIPA / ZEROCONF** | `169.254.0.0 – 169.254.255.255` | Notbetrieb bei DHCP-Ausfall |

> Private Adressen tauchen im Internet **niemals** auf — Router blockieren sie.  
> NAT (Network Address Translation) übersetzt private in öffentliche Adressen am Router.

---

## 3. Subnetzmaske

Die Subnetzmaske teilt eine IP-Adresse in zwei Teile:

| Teil | Beschreibung |
|------|-------------|
| **Netz-ID** | Identifiziert das Netzwerk |
| **Host-ID** | Identifiziert das Gerät im Netzwerk |

### CIDR-Notation
Statt `255.255.255.0` schreibt man kurz `/24` — die Zahl gibt an, wie viele Bits die Netz-ID umfasst.

| Subnetzmaske | CIDR | Netz-ID Bits | Host-ID Bits |
|-------------|------|-------------|-------------|
| 255.0.0.0 | /8 | 8 | 24 |
| 255.255.0.0 | /16 | 16 | 16 |
| 255.255.255.0 | /24 | 24 | 8 |

---

## 4. Netzwerkadresse & Broadcastadresse

| Adresse | Definition | Beispiel (/24) |
|---------|-----------|---------------|
| **Netzwerkadresse** | Alle Host-Bits = `0` | `10.11.12.0` |
| **Broadcastadresse** | Alle Host-Bits = `1` | `10.11.12.255` |
| **Nutzbare Hosts** | Alle Adressen dazwischen | `10.11.12.1 – 10.11.12.254` |

---

## 5. Anzahl Hosts berechnen

Formel: $2^{\text{Host-ID Bits}}$ = Anzahl IP-Adressen, davon **–2** für nutzbare PCs (Netz- und Broadcast abziehen).

| Netz | Host-Bits | IP-Adressen | Nutzbare PCs |
|------|----------|------------|-------------|
| /8 | 24 | $2^{24}$ = 16'777'216 | 16'777'214 |
| /16 | 16 | $2^{16}$ = 65'536 | 65'534 |
| /24 | 8 | $2^{8}$ = 256 | 254 |

---

## 6. Können zwei PCs kommunizieren?

Zwei PCs können direkt kommunizieren, wenn ihre **Netz-IDs übereinstimmen**.

**Schnelle Prüfmethode:**

| Maske | Bedingung |
|-------|-----------|
| /24 | Erste drei Oktette müssen gleich sein |
| /16 | Erste zwei Oktette müssen gleich sein |
| /8 | Nur erstes Oktett muss gleich sein |

**Sonderfälle:**

| Fall | Resultat |
|------|---------|
| Identische IP-Adressen | Keine Kommunikation (IP-Konflikt) |
| Ungültige IP (z.B. `258.x`) | Ungültige Adresse, nicht verwendbar |
| Unterschiedliche Masken | Asymmetrisch: Ping kommt an, Antwort nicht |
| `172.33.x.x` mit Maske /8 | `172.33` liegt ausserhalb `172.16–172.31` → öffentliche IP |

---

## 7. Wichtige Netzwerkbegriffe

| Begriff | Erklärung |
|---------|-----------|
| **Hostname** | Menschenlesbarer Gerätename (z.B. `TBZ-PC`). Windows: `sysdm.cpl` |
| **MAC-Adresse** | 48-Bit Hardware-Adresse, fest auf Netzwerkkarte → **statisch** |
| **IPv4-Adresse** | Jederzeit änderbar → **dynamisch** |
| **DHCP** | Verteilt automatisch IP, Maske, Gateway, DNS an Clients |
| **APIPA** | Notfall-IP `169.254.x.x` wenn kein DHCP antwortet |
| **Loopback** | `127.0.0.1` — testet Netzwerkstack des eigenen PCs |
| **Standardgateway** | Router im eigenen Subnetz, leitet Pakete in andere Netze weiter |
| **Router** | Verbindet Subnetze — einziger Weg zwischen verschiedenen Netz-IDs |

---

## 8. Wichtige Windows-Konsolenbefehle

| Befehl | Funktion |
|--------|---------|
| `ipconfig /all` | Zeigt IP, Subnetzmaske, Gateway, DNS, MAC |
| `ping <IP>` | Prüft Erreichbarkeit eines Kommunikationspartners |
| `arp -a` | Zeigt ARP-Cache: bekannte MAC/IP-Zuordnungen im lokalen Netz |

IP ändern: `ncpa.cpl` → Adapter → Eigenschaften → IPv4  
Hostname ändern: `sysdm.cpl`

---

## 9. CSMA/CD

**Carrier Sense Multiple Access / Collision Detection** — Zugriffsverfahren bei Hubs:

1. Gerät lauscht ob Medium frei ist
2. Wenn frei → sendet
3. Kollision erkannt → sofort stoppen
4. Zufällige Wartezeit → erneuter Versuch

> Bei Switches mit Vollduplex gibt es keine Kollisionen → CSMA/CD nicht nötig.

---

## 10. Statisch vs. Dynamisch

| | Statisch | Dynamisch (DHCP) |
|-|----------|-----------------|
| **Vergabe** | Manuell | Automatisch |
| **Vorteil** | Immer gleiche Adresse | Flexibel, keine Doppelvergabe |
| **Einsatz** | Server, Router, Drucker | PCs, Laptops, Smartphones |

---

## Quellen

- Aufgabensammlung Modul 117: https://jarnold.ch/ict/117/jobpostings_117.pdf
- Theoriedokumentation Modul 117: https://jarnold.ch/ict/117/theory_117.pdf
