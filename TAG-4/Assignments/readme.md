
# Modul 117 – Kapitel 4: Dateizugriffsrechte
## Aufgaben und Musterlösungen

---

## Aufgabe D1

**Frage 1: Aus welchem Grund benötigt mein PC ein Benutzer-Accounting?**

> Ohne Benutzer-Accounting wären keine Dateizugriffsrechte möglich, und jede Person mit Zugang zum PC könnte alle Dokumente einsehen. Grundsätzlich muss das Dateisystem die Zugriffsrechte unterstützen. Der Benutzeraccount sollte zudem durch ein Passwort geschützt sein.

---

**Frage 2: Was will man erreichen, wenn man Zugriffsrechte gruppenweise erteilt?**

> Effizienz: Neue Mitarbeiter erhalten durch die Zuweisung zur entsprechenden Gruppe sofort alle erforderlichen Zugriffsrechte. Von der Gruppe entfernte Benutzer verlieren sofort alle entsprechenden Berechtigungen.

---

**Frage 3: Wann macht eine lokale, wann eine zentrale Benutzerverwaltung Sinn? Wie heisst der Dienst und wie nennt Microsoft ihr SW-Produkt für zentrale Benutzerverwaltung?**

> **Lokal:** Für kleine Netzwerke wie ein Heimnetz gibt es bei Windows die sogenannte **Arbeitsgruppe**. Durch die Zuweisung der PCs zu einer oder mehreren Arbeitsgruppen werden logische Verbünde hergestellt. Innerhalb einer Arbeitsgruppe hat keine Maschine Kontrolle über eine andere. Arbeitsgruppen funktionieren bis maximal 20 Nutzer.
>
> **Zentral:** Je nach Firmenstruktur und Sicherheitsansprüchen macht eine zentrale Benutzerverwaltung schon ab wenigen Mitarbeitern (>10) Sinn. Man spricht dann von einem **Verzeichnisdienst (Directory Service)**, der im Netzwerk eine zentrale Sammlung von Daten zur Verfügung stellt. Bei Microsoft ist der Verzeichnisdienst unter dem Begriff **Active Directory** bekannt.

---

## Aufgabe D2 – Microsoft's Beschränkte Sicherheitseinstellungen

**Frage: Kreuzen sie an, was zusammenpasst!**

| Beschreibung | Vollzugriff | Lesen | Schreiben | Ändern | Ausführen | Ordnerinhalt auflisten |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Alle Rechte auf Objekt und untergeordneten Objekten. Lesen / Schreiben / Löschen / Modifizieren / Besitzübernahme | **X** | | | | | |
| Objektänderungen (inkl. untergeordneten) nicht erlaubt. Leserecht für alle Attribute & Inhalte | | **X** | | | **X** | |
| Nur Leserechte. Dateiausführung & Verzeichnisdurchsuchung nicht erlaubt. | | **X** | | | | |
| Auf Verzeichnisse bezogen: Gleich wie „Lesen, Ausführen". Lesen/Durchsuchen von Verzeichnis & Unterverzeichnissen. Lesen von Objekt-Attributen. | | | | | | **X** |
| Nur schreibender Zugriff. Dateiausführung & Verzeichnisdurchsuchung nicht erlaubt. Setzen von Datei/Verzeichnis-Attributen erlaubt. Nur Leserechte auf Berechtigungen. | | | **X** | | | |
| Änderungen & Löschen des Objekts. Ändern der Berechtigungen & Besitzübernahme nicht erlaubt. Kein Löschen von untergeordneten Objekten. Leserecht auf alle Objektoptionen. | | | | **X** | | |

---

## Aufgabe D3 – Microsoft's Beschränkte Sicherheitseinstellungen

**Frage: Markiere die Felder für allgemeines «Schreiben (S)»**

| Berechtigung | Zulassen |
|---|:---:|
| Vollzugriff | |
| Ändern | ✔ |
| Lesen, Ausführen | ✔ |
| Ordnerinhalt auflisten | ✔ |
| Lesen | ✔ |
| Schreiben | ✔ |

**Frage: Markiere die Felder für allgemeines «Lesen (L)»**

| Berechtigung | Zulassen |
|---|:---:|
| Vollzugriff | |
| Ändern | |
| Lesen, Ausführen | ✔ |
| Ordnerinhalt auflisten | ✔ |
| Lesen | ✔ |
| Schreiben | |

**Frage: Markiere die Felder für «Kein Zugriff (X)»**

> Alle Felder bleiben leer (kein Häkchen gesetzt).

---

**Frage: Worin unterscheiden sich die Rechte bei zusätzlichem Lesen/Ausführen?**

> **✔ Datei in Form eines Programms/Batch kann auch ausgeführt (Execute) werden**
>
> ☐ Datei kann gelesen werden
> ☐ Datei wird vom System entfernt bzw. hinausgeführt
> ☐ Metadaten einer Datei werden angezeigt
> ☐ Keine Antwort richtig

---

## Aufgabe D4 – Microsoft's Beschränkte Sicherheitseinstellungen

**Frage: Worin unterscheiden sich die Rechte bei zusätzlichem Ändern?**

> **✔ Zusätzliches Löschen des Objekts**
>
> ☐ Daten im File können auch geändert werden
> ☐ Dateipfad ändern
> ☐ Keine Antwort richtig

---

**Frage: Worin unterscheiden sich die Rechte bei zusätzlichem Vollzugriff?**

> **✔ Zusätzlich «Berechtigungen ändern»**
> **✔ Zusätzlich «Besitz übernehmen»**
> **✔ Zusätzlich «Untergeordnete Ordner/Dateien löschen»**
>
> ☐ Vollzugriff auf das ganze Dateisystem
> ☐ Zusätzlich Administratorenrechte übernehmen, wenn nicht bereits als Administrator eingeloggt

---

## Aufgabe D5 – Microsoft's Beschränkte Sicherheitseinstellungen

**Frage: Herr Muster ist Mitglied von Gruppe-A und Gruppe-B. Welche Rechte besitzt er?**

*(Gruppe-A: Ändern, Lesen/Ausführen, Ordnerinhalt, Lesen, Schreiben = Zulassen. Gruppe-B: Lesen/Ausführen, Ordnerinhalt, Lesen = Zulassen)*

> ☐ Vollzugriff
> **✔ Ändern**
> **✔ Lesen, Ausführen**
> **✔ Ordnerinhalt auflisten**
> **✔ Lesen**
> **✔ Schreiben**

*Erklärung: Bei Mitgliedschaft in mehreren Gruppen werden die Rechte addiert (union). Herr Muster erhält die Vereinigung aller Erlaubnisse aus Gruppe-A und Gruppe-B.*

---

**Frage: Frau Muster ist Mitglied von Gruppe-A und Gruppe-B. Welche Rechte besitzt sie?**

*(Gruppe-A: Ändern, Lesen/Ausführen, Ordnerinhalt, Lesen, Schreiben = Zulassen. Gruppe-B: Ändern = Verweigern, Schreiben = Zulassen)*

> ☐ Vollzugriff
> ☐ Ändern
> **✔ Lesen, Ausführen**
> **✔ Ordnerinhalt auflisten**
> **✔ Lesen**
> ☐ Schreiben

*Erklärung: **Verweigern hat Vorrang** vor Zulassen. Da Gruppe-B «Ändern» verweigert, verliert Frau Muster dieses Recht trotz Zulassung in Gruppe-A. Ebenso wird «Schreiben» blockiert, da «Ändern» verweigert wird.*

---

## Aufgabe D6 – Microsoft's Beschränkte Sicherheitseinstellungen

**Frage: Was trifft zu, wenn der Benutzer «testuser» die Berechtigungen auf sein Verzeichnis «TestDirectoryA» wie gezeigt ändert?**

*(Einstellung: Lesen/Ausführen, Ordnerinhalt, Lesen = Zulassen; Vollzugriff, Ändern, Schreiben = nicht gesetzt)*

> **✔ «testuser» kann sein Verzeichnis nicht mehr ändern oder löschen**
> **✔ «testuser» kann sein Verzeichnis lesen**
> **✔ Es werden Administratorenrechte benötigt, um dem Benutzer «testuser» wieder Schreibzugriff auf sein Verzeichnis zu ermöglichen**
>
> ☐ Da das Verzeichnis «TestDirectoryA» vom Benutzer «testuser» erzeugt wurde, hat er grundsätzlich alle elementaren Rechte darauf

*Erklärung: Die aktuell gesetzten Berechtigungen gelten absolut – die ursprüngliche Erstellung des Verzeichnisses verleiht keine dauerhaften Rechte. Ohne «Schreiben» oder «Ändern» kann testuser im eigenen Ordner keine Dateien mehr erstellen oder verändern.*

---

## Aufgabe D7

**Frage 1: Was versteht man unter der Vererbung von Zugriffsrechten?**

> Wird ein neues Verzeichnis oder eine neue Datei erstellt, werden die Berechtigungen des übergeordneten Verzeichnisses übernommen bzw. **vererbt**. Wenn dies nicht gewünscht ist, muss die Vererbung in den Verzeichnis-Eigenschaften gezielt unterbrochen werden.

---

**Frage 2: Was bedeutet dieses Kommando in der Adresszeile des WIN-Dateiexplorers: `\\10.0.1.100\projekte2024`**

> Das ist ein **UNC-Pfad** zu einer Dateifreigabe. Der dateifreigebende Server hat die IP-Adresse `10.0.1.100`. Das freigegebene Verzeichnis ist unter dem Freigabenamen `projekte2024` erreichbar.

---

**Frage 3: Auf einem FAT32 formatierten USB-Memorystick sind alle Passwörter, Cloud-Zugänge und Kreditkartendaten gespeichert. Der Stick wurde liegengelassen. Müssen Sie sich Sorgen machen?**

> **Ja**, denn FAT32-formatierte Datenträger kennen keine Zugriffsrechte. Jede Person, die den Stick in einen Computer steckt, kann alle Dateien uneingeschränkt lesen. Besser wäre es, den Memorystick mit **NTFS** zu formatieren, Berechtigungen zu vergeben und sensible Daten zusätzlich zu **verschlüsseln**.

---

**Frage 4: NTFS-Memorystick – Kann der Sitznachbar die Datei «myPassword» einsehen?**

> Ohne spezielle Berechtigungseinstellungen wird die Datei unter «Jeder» gespeichert und ist auf einem Fremdsystem lesbar. Schützen kann man die Daten, indem man auf dem Memorystick ein Verzeichnis erstellt, die Vererbung unterbricht, und ausschliesslich den eigenen Benutzernamen mit Vollzugriff einträgt. Dateien in diesem Verzeichnis sind dann auf Fremdsystemen vor unberechtigtem Zugriff geschützt.

---

## Aufgabe D8 – VM-Konfiguration

**Aufgabe: Erstellen Sie eine VM gemäss folgenden Vorgaben und überprüfen Sie Ihre Konfiguration.**

| Parameter | Wert |
|---|---|
| Betriebssystem | Windows 10 Pro |
| Netzwerkeinstellung | Nur lokal |
| Hostname | TBZ-PC |
| Arbeitsgruppe | M117 |
| IP-Adresse | 172.16.100.100/24 |
| Router (Gateway) | 172.16.100.1 |
| DNS1 | 172.16.100.2 |
| DNS2 | 172.16.100.3 |

**Gruppen (zusätzlich zu den Standard-Gruppen):**
- Fabrikation
- Entwicklung

**Benutzer (zusätzlich zum Admin):**

| Benutzer | Gruppe(n) |
|---|---|
| Paul | Fabrikation |
| Berta | Fabrikation |
| Fredi | Entwicklung |
| Nora | Entwicklung |
| Xaver | Entwicklung & Fabrikation |

**Verzeichnisse und Berechtigungen:**

| Pfad | Owner | Lesen & Schreiben | Nur Lesen |
|---|---|---|---|
| `C:\ablage\fabrikation` | Paul | Paul, Berta | Nora |
| `C:\ablage\entwicklung` | Nora | Fredi, Nora | – |

**Freigabe:**

| Parameter | Wert |
|---|---|
| Verzeichnis | `C:\ablage\datashare` |
| Freigabename | `datashare` |
| Zugriff | Jeder, Lesen & Schreiben |

> *Keine offizielle Musterlösung vorhanden – Konfiguration ist praktisch am System zu überprüfen.*
