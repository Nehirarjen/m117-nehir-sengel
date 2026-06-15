
# Theorie-Zusammenfassung: 5. SUBNETTING LIGHT

Diese Zusammenfassung deckt die theoretischen Kernkonzepte zu **Kapitel 5: Subnetting Light** (Modul 117) ab.

---

##  1. Was ist Subnetting?
Unter Subnetting versteht man das logische Aufteilen eines einzigen, großen IP-Netzwerkbereichs in mehrere kleinere, eigenständige Teilnetzwerke (Subnetze). 

### Hauptziele des Subnettnings:
* **Sicherheit:** Isolierung von empfindlichen Netzwerksegmenten (z. B. Buchhaltung von Gästenetzwerk trennen).
* **Struktur:** Logische Zuordnung nach Abteilungen, Standorten, Gebäuden oder Router-Verbindungsstrecken.
* **Effizienz:** Reduzierung von unnötigem Broadcast-Traffic (Datenpakete, die an alle Hosts gesendet werden).

---

##  2. Die Bausteine eines Subnetzes

In jedem Subnetz gibt es Adressen mit speziellen, festen Funktionen, die **niemals** an normale PCs oder Server vergeben werden dürfen:

1. **Netzwerkadresse (Netz-ID):** * Die allererste Adresse im IP-Bereich (endet bei `/24` immer auf `.0`). 
   * Sie dient Routern zur Identifikation des gesamten Netzwerks im Routing-Table.
2. **Broadcastadresse:** * Die allerletzte IP-Adresse im IP-Bereich (endet bei `/24` immer auf `.255`). 
   * Wird verwendet, um eine Nachricht gleichzeitig an alle Geräte innerhalb dieses spezifischen Subnetzes zu senden.
3. **Nutzbare Host-Adressen:** * Alle IP-Adressen, die mathematisch zwischen der Netzwerkadresse und der Broadcastadresse liegen (bei `/24` von `.1` bis `.254`). 
   * Diese werden an Endgeräte, Server, Drucker und Router-Schnittstellen verteilt.

---

##  3. Funktionsweise bei Subnetting "Light"

Das Prinzip "Light" bezieht sich auf die vereinfachte Aufteilung entlang der Oktett-Grenzen (Klassen-Subnetting).

* **Ausgangslage:** Ein übergeordnetes Netzwerk (z. B. `10.0.0.0/16`). Die `/16` bedeutet, dass die ersten beiden Blöcke (`10.0.`) festgeschrieben sind.
* **Aufteilung in `/24`:** Jedes Subnetz erhält eine `/24`-Subnetzmaske (`255.255.255.0`). Dadurch wird das dritte Oktett (der dritte Block) zum eindeutigen Identifikator des Subnetzes gemacht:
  * Subnetz A: `10.0.1.0/24`
  * Subnetz B: `10.0.2.0/24`
  * Subnetz C: `10.0.3.0/24` ... usw.

---

##  4. Kopplung über Router & Standardgateway

* **Der Router (RT):** Damit Geräte aus Subnetz B mit Geräten aus Subnetz C kommunizieren können, muss ein Router dazwischengeschaltet sein. Ein Router besitzt für jedes Subnetz, mit dem er physisch/logisch verbunden ist, eine eigene IP-Schnittstelle.
* **Das Standardgateway:** Auf jedem Endgerät (PC) muss die IP-Adresse der lokalen Router-Schnittstelle als *Standardgateway* eingetragen werden. Sendet ein PC Daten an eine IP außerhalb seines eigenen Subnetzes, übergibt er diese automatisch an das Standardgateway zur Weiterleitung.

---

##  5. Point-to-Point Links (Router-Strecken)
Für Netze, die ausschließlich dazu dienen, zwei Router direkt miteinander zu verbinden (z. B. Verbindungsglieder im Backend), kann statt `/24` auch eine **`/30`-Subnetzmaske** (`255.255.255.252`) genutzt werden. Diese beinhaltet exakt 2 nutzbare Host-IPs, was die Verschwendung wertvoller IP-Adressen auf reinen Datenübertragungsstrecken verhindert.
