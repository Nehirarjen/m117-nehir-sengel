

# Theorie-Zusammenfassung: Netzwerkadressierung & Grundlagen

## 1. Identifikation im Netzwerk: Namen und Adressen
In einem TCP/IP-Netzwerk besitzt jede Netzwerkschnittstelle verschiedene Identifikatoren, um eine eindeutige Kommunikation zu ermöglichen:
* **Hostname (Computername):** Ein frei wählbarer, alphanumerischer Name für ein Gerät (ohne Sonderzeichen). Er dient der menschlichen Lesbarkeit und folgt idealerweise einem strukturierten Namenskonzept (z. B. raumbezogen oder nach Themen wie Bergen).
* **MAC-Adresse (Media Access Control):** Die physikalische, weltweit eindeutige und unveränderbare Adresse einer Netzwerkkarte. Sie ist 48 Bit lang und arbeitet auf der OSI-Schicht 2 (Sicherungsschicht).
* **IP-Adresse (Internet Protocol, IPv4):** Eine logische, veränderbare Adresse mit einer Bitbreite von 32 Bit (aufgeteilt in 4 Oktette zu je 8 Bit, z. B. `192.168.1.1`). Sie arbeitet auf der OSI-Schicht 3 (Vermittlungsschicht). Die theoretische Obergrenze liegt bei $2^{32} \approx 4,29$ Milliarden Adressen.

## 2. Medienzugriffsverfahren: CSMA/CD
Um Datenkollisionen in einem gemeinsamen Netzwerksegment (einer Kollisionsdomäne) zu verhindern, nutzen Ethernet-Geräte das Verfahren **CSMA/CD** (*Carrier Sense Multiple Access with Collision Detection*):
1. **Carrier Sense (Leitungsprüfung):** Das Gerät lauscht, ob die Leitung frei ist.
2. **Multiple Access (Mehrfachzugriff):** Ist die Leitung frei, beginnt das Gerät mit der Übertragung.
3. **Collision Detection (Kollisionserkennung):** Während des Sendens prüft das Gerät, ob eine Kollision auftritt (wenn ein anderes Gerät gleichzeitig gesendet hat). 
4. **Verhalten bei Kollision:** Wird eine Kollision erkannt, brechen die Geräte die Übertragung ab, senden ein Störsignal (Jam-Signal) und warten eine zufällige Zeitspanne (Backoff-Zeit), bevor sie einen neuen Versuch starten.

## 3. Subnetzierung (Netzwerke aufteilen)
Würden alle Milliarden Hosts in einer einzigen grossen Domäne kommunizieren, käme es durch Broadcasts zu einer totalen Verkehrsüberlastung. Netzwerke werden daher mithilfe einer **Subnetzmaske** in logische Teilnetze aufgeteilt. 

Die Subnetzmaske trennt die IP-Adresse in zwei Bereiche:
1. **Netz-ID:** Identifiziert das spezifische Netzwerk/Subnetz.
2. **Host-ID:** Identifiziert das konkrete Endgerät innerhalb dieses Netzwerks.

### Wichtige Masken-Varianten (Standard in M117):
* **/8** (Dezimal: `255.0.0.0`) $\rightarrow$ Das erste Oktett ist die Netz-ID, die restlichen drei Oktette gehören der Host-ID.
* **/16** (Dezimal: `255.255.0.0`) $\rightarrow$ Die ersten zwei Oktette bilden die Netz-ID, die letzten zwei die Host-ID.
* **/24** (Dezimal: `255.255.255.0`) $\rightarrow$ Die ersten drei Oktette bilden die Netz-ID, das letzte Oktett die Host-ID.

### Reservierte Adressen pro Subnetz:
In jedem Subnetz sind zwingend zwei Adressen für Sonderzwecke reserviert und dürfen **nicht** an Endgeräte vergeben werden:
* **Netzwerkadresse:** Alle Bits der Host-ID sind logisch `0`. Sie kennzeichnet das gesamte Netz.
* **Broadcastadresse:** Alle Bits der Host-ID sind logisch `1`. Sie dient dazu, Nachrichten an *alle* Teilnehmer des Subnetzes gleichzeitig zu senden.

## 4. Private und Spezielle IP-Adressbereiche
Zur Einsparung von IPv4-Adressen wurden Adressbereiche reserviert, die ausschliesslich intern (im LAN) verwendet und im öffentlichen Internet niemals geroutet werden:
* **Class A (gross):** `10.0.0.0` bis `10.255.255.255` (Sehr viele Subnetze/Hosts möglich)
* **Class B (mittel):** `172.16.0.0` bis `172.31.255.255`
* **Class C (klein):** `192.168.0.0` bis `192.168.255.255` (Typisch für Heimnetzwerke)
* **Loopback- / Localnet-Adresse:** `127.0.0.1` (Zeigt auf den eigenen Rechner, zur Überprüfung des lokalen IP-Stacks).
* **APIPA- / ZEROCONF-Bereich:** `169.254.0.0` bis `169.254.255.255` (Automatische Zuweisung zur Sicherung eines lokalen Notbetriebs, wenn die automatische DHCP-Zuweisung fehlschlägt).

## 5. Adressvergabe und Kopplung
* **Statische Vergabe:** Die IP-Parameter werden manuell eingetragen. Vorteile: Ausfallsicher, Geräte behalten immer dieselbe IP (wichtig für Server/Drucker).
* **Dynamische Vergabe (DHCP):** Ein DHCP-Server teilt den Geräten beim Start automatisch eine IP-Adresse, Subnetzmaske, DNS-Server und das Standardgateway zu. Vorteil: Extrem geringer Administrationsaufwand, Vermeidung von IP-Konflikten.
* **Standardgateway:** Die IP-Adresse der Routerschnittstelle im eigenen LAN. Ein **Router** ist die zwingend benötigte Netzwerkkomponente, um unterschiedliche Subnetze miteinander zu verbinden.
