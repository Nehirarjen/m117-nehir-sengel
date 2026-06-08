
# Zusammenfassung Theorie – Kapitel 4: Dateizugriffsrechte

---

## 1. Speichersysteme & Dateisysteme

### Speicherhierarchie

| Typ | Beschreibung |
|---|---|
| **Primärspeicher (RAM)** | Direkt an der CPU, flüchtig |
| **Sekundärspeicher** | Harddisk, SSD – enthält ein Dateisystem |
| **Dateisystem** | Baumstruktur mit Verzeichnis-Pfaden |

### Verzeichnis-Pfade

- **Absoluter Pfad:** Vollständiger Pfad ab Root-Directory  
  Beispiel: `C:\Users\FelixMuster\Documents\ArduinoProjekte`
- **Relativer Pfad:** Nur Teilpfad, abhängig vom aktuellen Verzeichnis (CWD)  
  Beispiel: `.\Documents\ArduinoProjekte`

**Spezielle Verzeichniseinträge:**
- `.` → aktuelles Verzeichnis (CWD)
- `..` → übergeordnetes Verzeichnis (Uplevel)

### Dateisysteme im Vergleich

| Dateisystem | Beschreibung |
|---|---|
| **FAT** | File-Allocation-Table, veraltet |
| **FAT32** | Keine Zugriffsrechte möglich. Dateigrösse max. 4 GiB (4.3 GB). Tipp: Bei USB-Sticks auf **exFAT** umformatieren (`diskmgmt.msc`), um das Grössenlimit zu umgehen. |
| **NTFS** | New-Technology-File-System – aktuelles Windows-Dateisystem. Unterstützt Zugriffsrechte (ACL). Cluster werden in der **MFT** (Master File Table) verwaltet. Kleine Dateien direkt in der MFT gespeichert. Hinweis: NTFS bei USB-Sticks eher ungünstig, da Windows-proprietär. |

> **Fazit:** Ohne NTFS keine Zugriffsrechte! Für Sicherheit auf USB-Sticks: NTFS verwenden und Berechtigungen setzen.

---

## 2. Warum Benutzer-Accounting?

Ohne Benutzer und Zugriffsrechte könnte jede Person mit Zugang zum Gerät alle Daten einsehen und verändern. Das Dateisystem muss die Zugriffsrechte unterstützen (NTFS), und jeder Account sollte mit einem Passwort geschützt sein.

**Tool zum Öffnen der lokalen Benutzerverwaltung:**  
`lusrmgr.msc` (gilt nur für Windows **Pro**, nicht Home)

---

## 3. Zugriffsrechte

### Grundlegende Rechtetypen (Windows)

| Recht | Bedeutung |
|---|---|
| **Vollzugriff** | Alle Rechte inkl. Berechtigungen ändern & Besitz übernehmen |
| **Ändern** | Lesen, Schreiben, Löschen – aber keine Berechtigungsänderung |
| **Lesen, Ausführen** | Lesen + Verzeichnisse durchsuchen + ausführbare Dateien starten |
| **Ordnerinhalt auflisten** | Wie Lesen/Ausführen, aber nur für Verzeichnisse |
| **Lesen** | Nur Lesezugriff, keine Ausführung, keine Verzeichnisdurchsuchung |
| **Schreiben** | Nur schreibender Zugriff, keine Ausführung |

> **Ausführungsrecht auf Verzeichnisse:** Erlaubt das Betreten des Verzeichnisses und das Einsehen des Inhalts (`ls`/`dir`). Ohne dieses Recht hilft auch ein vorhandenes Leserecht nichts.  
> **Ausführungsrecht auf Dateien:** Nur relevant bei ausführbaren Programmen, Batch-Dateien oder Skripten.

---

## 4. Benutzer vs. Gruppen

### Einzelbenutzer-Verwaltung (umständlich)

Jedem neu hinzugefügten Benutzer müssen alle Rechte auf Dateien und Verzeichnisse **einzeln** zugewiesen werden – grosser Verwaltungsaufwand.

### Gruppenbasierte Verwaltung (empfohlen)

Rechte werden der **Gruppe** erteilt. Benutzer erhalten die Rechte automatisch durch die Gruppenmitgliedschaft.

**Vorteil:** Ein neu hinzugefügter Benutzer (z.B. Gina) erhält sofort alle Rechte der Gruppe, ohne dass einzelne Berechtigungen gesetzt werden müssen. Beim Entfernen aus der Gruppe verliert er alle Gruppenrechte sofort.

---

## 5. Benutzerverwaltung: Lokal vs. Zentral

| | **Dezentral / Lokal (Peer-to-Peer)** | **Zentral (Directory Service)** |
|---|---|---|
| **Verwaltungsort** | Jeder PC verwaltet eigene Benutzer | Zentrale Instanz verwaltet alle Benutzer |
| **Benutzer-Identität** | Joe auf PC1 ≠ Joe auf PC2 | Joe ist auf allen PCs identisch |
| **Einsatz** | Heimnetz, kleine Netzwerke (<20 Nutzer) | Firmen ab ca. 10 Mitarbeitern |
| **Windows-Lösung** | Arbeitsgruppe (`lusrmgr.msc`) | **Active Directory** (Domain) |
| **Modul** | M117 | Späteres Modul |

---

## 6. Berechtigungssystem: UNIX vs. Windows

| | UNIX | Windows |
|---|---|---|
| **Modell** | Owner / Group / Others (je rwx) | ACL pro Benutzer/Gruppe (beliebig viele Einträge) |
| **Beispiel** | `felix produktion Alle anderen` | `felix`, `hanna`, `verkauf`, … |
| **Flexibilität** | Starr (3 Einträge) | Flexibel (beliebig viele) |

**ACL = Access Control List** (Zugriffssteuerungsliste) – Windows unterstützt ACL vollständig.

---

## 7. Vererbung

Wird ein neues Verzeichnis oder eine Datei erstellt, **erbt** es die Berechtigungen des übergeordneten Verzeichnisses automatisch.

- Bei Windows ist Vererbung **standardmässig aktiviert**.
- Soll sie unterbunden werden, muss sie pro Verzeichnis **explizit deaktiviert** werden (Eigenschaften → Sicherheit → Erweitert → Vererbung deaktivieren).

---

## 8. Freigaben: Datenzugriff von aussen (UNC)

Der Zugriff auf eine Freigabe erfolgt in zwei Schritten:

1. **Freigabe-Barriere:** Der externe Benutzer muss sich mit einem lokalen Benutzerkonto am Zielsystem authentifizieren.
2. **Dateisystem-Barriere:** Die NTFS-Berechtigungen auf dem freigegebenen Verzeichnis entscheiden, was der Benutzer tun darf.

### UNC-Pfade (Unified Naming Convention)

Drei Varianten für den Zugriff auf eine Freigabe:

| Variante | Syntax | Beispiel |
|---|---|---|
| Via Hostname | `\\Hostname\Freigabename` | `\\pc4\dokumente` |
| Via IP-Adresse *(Favorit in M117)* | `\\IP-Adresse\Freigabename` | `\\192.168.1.23\dokumente` |
| Via FQDN | `\\FQDN\Freigabename` | `\\pc4.firmaxy.local\dokumente` |

> Die IP-Variante funktioniert immer, sofern die Freigabe eingerichtet ist. Für Hostname und FQDN ist DNS- oder Hostfile-Auflösung erforderlich.

---

## 9. Planung (IPERKA)

Vor der Einrichtung von Benutzern, Verzeichnissen und Berechtigungen ist eine sorgfältige **Planung** unerlässlich:

- **Namenskonzept:** Einheitliche Benutzernamen und Gruppennamen
- **Benutzerzuordnung:** Welcher Benutzer gehört zu welcher Gruppe?
- **Verzeichnismatrix:** Welche Gruppe hat welchen Zugriff auf welche Verzeichnisse?
  - F = Full/Vollzugriff
  - C = Change (Lesen + Schreiben)
  - R = Read (nur Lesen)
- **Freigaben:** Welche Verzeichnisse werden nach aussen freigegeben?

> **Tipp:** Benutzer-/Projektdaten vom Betriebssystem trennen – entweder auf einem zweiten Speichermedium oder auf einer eigenen Partition.

---

## 10. Virtuelle Maschinen (VM)

Zum Üben von Freigaben und Berechtigungen können zwei virtuelle Maschinen (VM1 und VM2) auf denselben oder verschiedenen physischen Notebooks eingesetzt werden. Die VMs kommunizieren über einen virtuellen Netzwerk-Bridge-Adapter (WLAN oder Ethernet-Switch).

**Wichtig:** Bei Bridge-Modus muss die IP-Adresse der VM **eindeutig** (UNIQUE) im Netzwerk sein.

---

## Zusammenfassung auf einen Blick

```
Dateisystem → NTFS für Zugriffsrechte (FAT32 hat keine!)
      ↓
Benutzer + Passwort
      ↓
Benutzer → Gruppen zuordnen
      ↓
Gruppen → Berechtigungen auf Verzeichnisse (ACL)
      ↓
Vererbung: untergeordnete Objekte erben Eltern-Rechte
      ↓
Freigaben: Zugriff von aussen via UNC-Pfad (\\IP\Freigabename)
```
