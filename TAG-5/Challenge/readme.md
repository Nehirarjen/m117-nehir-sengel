
Challenge-5

---

## 1. Mitarbeiter 

| Username | Vollständiger Name | Abteilung / Rolle | Initialpasswort¹ |
| :--- | :--- | :--- | :--- |
| `anna.meier` | Anna Meier | Geschäftsleitung (CEO) | `St@rt2026!Am` |
| `beat.schmid` | Beat Schmid | Geschäftsleitung (CFO) | `St@rt2026!Bs` |
| `clara.fischer` | Clara Fischer | Finanzen & Personal (HR-Leitung) | `St@rt2026!Cf` |
| `david.weber` | David Weber | Finanzen & Personal (Buchhaltung) | `St@rt2026!Dw` |
| `eva.meyer` | Eva Meyer | Technik & Produktion (Leitung TECH) | `St@rt2026!Em` |
| `felix.wagner` | Felix Wagner | Technik & Produktion (Engineer) | `St@rt2026!Fw` |
| `gabi.becker` | Gabi Becker | Technik & Produktion (Engineer) | `St@rt2026!Gb` |
| `hans.schulz` | Hans Schulz | Technik & Produktion (Support) | `St@rt2026!Hs` |
| `iris.hoffmann` | Iris Hoffmann | Technik & Produktion (Qualität) | `St@rt2026!Ih` |
| `jan.bauer` | Jan Bauer | Technik & Produktion (Lehrling) | `St@rt2026!Jb` |


## 2. Gruppen- und Mitgliedschaftsmatrix

| Gruppenname | Beschreibung / Zweck | Zugeordnete Mitglieder (Usernames) |
| :--- | :--- | :--- |
| `g_gl` | Global: Geschäftsleitung | `anna.meier`, `beat.schmid` |
| `g_hr_fi` | Global: Finanzen & Personal | `clara.fischer`, `david.weber` |
| `g_tech` | Global: Technische Abteilung | `eva.meyer`, `felix.wagner`, `gabi.becker`, `hans.schulz`, `iris.hoffmann`, `jan.bauer` |
| `g_all` | Global: Alle Mitarbeiter (All Staff) | *Alle 10 oben genannten Benutzerkonten* |

## 3. Verzeichnisstruktur- und Rechtematrix

| Verzeichnisname | Besitzer (Owner) | Gruppe: `g_gl` | Gruppe: `g_hr_fi` | Gruppe: `g_tech` |
| :--- | :--- | :--- | :--- | :--- |
| `01_Management` | `anna.meier` | **LS** | Kein | Kein |
| `02_HR_Finanzen` | `beat.schmid` | **L** | **LS** | Kein |
| `03_Technik` | `eva.meyer` | **L** | Kein | **LS** |
| `04_Austausch` | `Administrator` | **LS** | **LS** | **LS** |
