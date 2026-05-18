# Challenge 2 – ARISTA-LAN
## Komplette Lösung – Arista GmbH

---

# 1. Ausgangslage

Die Firma Arista GmbH möchte ihre Büroräumlichkeiten neu mit Ethernet verkabeln. Dabei sollen:

- 10 Arbeitsplätze eingerichtet werden
- 4 Netzwerkdrucker installiert werden
- eine saubere strukturierte Verkabelung erstellt werden
- ein logisches Layout erstellt werden
- ein Verkabelungsplan erstellt werden
- eine vollständige Stückliste erstellt werden

Die Verkabelung erfolgt mit:

- Cat6 UGV-Kabel
- RJ45-Steckdosen
- Patchkabeln
- Unmanaged Layer-2-Switches

Besondere Vorgaben:

- Aufputz-Kabelkanäle
- Keine Bohrungen im Sanitärbereich
- Keine VLANs
- Kein Subnetting
- Alle Geräte im selben Netzwerk

---

# 2. Netzwerk-Konzept

## Gewählte Topologie

Es wurde eine Stern-Topologie gewählt.

Begründung:

- einfache Verwaltung
- einfache Fehlersuche
- kostengünstig
- wenig Verkabelungsaufwand
- gut erweiterbar

Der Router verbindet das interne Netzwerk mit dem Internet.
Alle Geräte werden über die Switches verbunden.

---

# 3. Logisches Layout

## WAN / Internet

WWW / ISP
↓
RT-01 (Router)
192.168.1.1/24
↓
SW-01 (16-Port Unmanaged Layer-2 Switch)
↓
SW-02 (8-Port Unmanaged Layer-2 Switch)

---

## Geräteübersicht

| Büro | Gerät | IP-Adresse |
|---|---|---|
| Büro-A | PC-A01 | 192.168.1.11 |
| Büro-B | PC-B01 | 192.168.1.31 |
| Büro-B | PC-B02 | 192.168.1.32 |
| Büro-B | PC-B03 | 192.168.1.33 |
| Büro-B | PR-B01 (S/W Drucker) | 192.168.1.41 |
| Büro-C | PC-C01 | 192.168.1.51 |
| Büro-C | PC-C02 | 192.168.1.52 |
| Büro-C | PC-C03 | 192.168.1.53 |
| Büro-C | PR-C01 (S/W Drucker) | 192.168.1.42 |
| Büro-D | PC-D01 | 192.168.1.61 |
| Büro-D | PR-D01 (Color Drucker) | 192.168.1.43 |
| Büro-F | PC-F01 | 192.168.1.21 |
| Büro-F | PC-F02 | 192.168.1.22 |

---

## Netzwerkdaten

| Einstellung | Wert |
|---|---|
| Netzwerk | 192.168.1.0/24 |
| Subnetzmaske | 255.255.255.0 |
| Gateway | 192.168.1.1 |
| DNS | Router / ISP |

Alle Geräte befinden sich im selben Subnetz.
Es wird kein Subnetting verwendet.

---

# 4. Verkabelungsplan

## Verkabelungskonzept

Die Gebäudeverkabelung erfolgt über Kabelkanäle entlang der Wände.

Die Kabel verlaufen:

- entlang der Wand
- nicht quer durch Räume
- nicht durch den Sanitärbereich
- sauber in Kabelkanälen

---

## Farbkonzept der Kabel

| Kabeltyp | Farbe |
|---|---|
| UGV-Kabel | Blau |
| Patchkabel | Rot |
| Sonstige Linien | Schwarz |

---

## Verkabelungsregeln

### UGV-Kabel

- führen von RJ45-Steckdose zu RJ45-Steckdose
- verlaufen im Kabelkanal
- werden fest installiert

### Patchkabel

- verbinden:
  - PC ↔ RJ45-Dose
  - Drucker ↔ RJ45-Dose
  - Switch ↔ RJ45-Dose
  - Router ↔ RJ45-Dose

---

## Positionierung der Geräte

| Gerät | Standort |
|---|---|
| RT-01 | Beim Telefonanschluss / Eingang |
| SW-01 | Zentral im Gebäude |
| SW-02 | Büro-B Bereich |
| PR-B01 | Büro-B |
| PR-C01 | Büro-C |
| PR-D01 | Büro-D |

---

# 5. Begründung der Druckerstandorte

## Büro-B

Der S/W-Drucker wird von mehreren Mitarbeitenden gemeinsam genutzt.
Die Position reduziert Laufwege.

## Büro-C

Der zweite S/W-Drucker befindet sich zentral für Büro-C.

## Büro-D

Der Farbdrucker wird in Büro-D platziert.
Farbdrucke werden seltener benötigt.

---

# 6. Switch-Konzept

## Verwendete Switches

| Switch | Typ | Begründung |
|---|---|---|
| SW-01 | 16-Port Unmanaged L2 | Hauptswitch mit genügend Ports |
| SW-02 | 8-Port Unmanaged L2 | Erweiterung für zusätzliche Geräte |

---

## Portberechnung

### Benötigte Ports

| Gerätetyp | Anzahl |
|---|---|
| PCs | 10 |
| Drucker | 4 |
| Router-Uplink | 1 |
| Uplink SW-02 | 1 |
| Reserve | mehrere |

Gesamt: mindestens 16 Ports

Die Lösung erfüllt die Anforderungen mit Reserve.

---

# 7. Stückliste

| Pos | Anzahl | Artikel | Beschreibung |
|---|---|---|---|
| 1 | 10 | Office-PC | Win11 Pro, Tastatur, Maus, 24" Monitor |
| 2 | 3 | S/W Netzwerkdrucker | Laserdrucker |
| 3 | 1 | Color Netzwerkdrucker | Laser |
| 4 | 1 | Router | Gigabit WAN/LAN |
| 5 | 1 | 16-Port Switch | Unmanaged Layer-2 |
| 6 | 1 | 8-Port Switch | Unmanaged Layer-2 |
| 7 | 14 | RJ45-Steckdosen | Cat6 |
| 8 | 18 | Patchkabel | Cat6 rot, 2m |
| 9 | ca. 120m | UGV-Kabel | Cat6 blau |
| 10 | ca. 35m | Kabelkanal | Aufputz |
| 11 | 1 | Kabelbinder Set | Montage |
| 12 | 1 | Beschriftungsset | Kabelkennzeichnung |

---

# 8. Erklärung des Konzepts

## Warum funktioniert das Netzwerk?

Das Netzwerk funktioniert, weil:

- alle Geräte korrekt mit einem Switch verbunden sind
- alle Geräte im selben IP-Netz arbeiten
- keine Netzwerkschleifen vorhanden sind
- der Router den Internetzugang bereitstellt
- strukturierte Verkabelung verwendet wird

---

## Warum wurde diese Topologie gewählt?

Die Stern-Topologie:

- ist Standard in Firmennetzwerken
- reduziert Fehlerquellen
- erleichtert Erweiterungen
- ermöglicht saubere Verkabelung

---

# 10. Dateinamen für die Abgabe

Empfohlene Dateinamen:

- Arista_Logisches_Layout.jpg
- Arista_Verkabelungsplan.jpg
- Arista_Stueckliste.pdf
- Arista_Dokumentation.pdf

