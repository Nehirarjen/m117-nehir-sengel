# Challenge-1 – Ethernet-Verlegekabel

**Modul:** 117 – Informatik-Infrastruktur in Betrieb nehmen  
**Block:** Unterrichtsblock 1 – Ethernetverkabelung  
**Datum:** _[Datum eintragen]_

---

## Aufgabenstellung

Suche im Fachhandel (Webshop) ein Ethernet-**Verlegekabel**, das für den Einsatz im Betrieb geeignet ist.  
Es soll **mindestens Gigabit-Ethernet** ermöglichen und gegen **Störungen möglichst resistent** sein.

---

## Gewähltes Kabel

**Dätwyler Uninet 7060 4P – CAT 6A S/FTP Installationskabel**

| Kenndaten            | Wert                                                    |
|----------------------|---------------------------------------------------------|
| **Hersteller**       | Dätwyler Cables AG (Schweiz)                            |
| **Lieferant**        | Digitec.ch                                              |
| **Bestellnummer**    | Art.-Nr. 2750330                                        |
| **Preis**            | ca. CHF 1.20–1.50 / Meter (100m-Rolle)                  |
| **Kabelmaterial**    | CU-Massivdraht, AWG 23, Kupfer                          |
| **Kabelaufbau**      | S/FTP (PiMF), 4 × 2 Adern, Folie je Paar + Geflecht    |
| **Störungsabwehr**   | Aluminiumfolie pro Paar + verzinntes Kupfergeflecht      |
| **Ethernet-Medientyp** | 10GBase-T                                             |
| **Datendurchsatz**   | 10 Gbit/s (= 10'000 Mbit/s)                             |
| **Kabelkategorie**   | CAT 6A, Klasse EA                                       |
| **Max. Frequenz**    | 500 MHz                                                 |
| **Kommunikationsmodus** | Vollduplex                                           |
| **Max. Segmentlänge** | 100 m                                                  |
| **Normen**           | ISO/IEC 11801, EN 50173                                 |

---

## Erklärung aller Kenndaten

### Hersteller – Dätwyler Cables AG

Dätwyler ist ein Schweizer Industrie-Konzern mit Sitz in Altdorf (UR), der seit Jahrzehnten hochwertige
Kabel für professionelle Netzwerk-Installationen produziert. Schweizer Hersteller stehen für strenge
Qualitätskontrollen und Einhaltung europäischer Normen. Das ist für eine langfristige
Betriebsinstallation (Kabel bleibt 10–20 Jahre in der Wand) besonders wichtig.

---

### Lieferant – Digitec.ch

Digitec ist einer der grössten Schweizer Online-Händler für Elektronik und IT-Produkte. Vorteile
für den Betriebseinkauf: schnelle Lieferung (oft nächster Tag), Rechnung auf Firmenname möglich,
24 Monate Garantie, einfache Rückgabe. Alternativ wäre auch Brack.ch oder Distrelec.ch möglich.

---

### Bestellnummer – Art.-Nr. 2750330

Die Bestellnummer (Artikelnummer) identifiziert das Produkt eindeutig im Webshop des Lieferanten.
Sie verhindert Verwechslungen beim Bestellen, besonders wenn es viele ähnliche Produkte gibt
(z.B. CAT 6 vs. CAT 6A, S/FTP vs. U/FTP). Immer die Bestellnummer notieren – nie nur den Namen!

---

### Preis – ca. CHF 1.20–1.50 / Meter

Der Preis bezieht sich auf den Preis pro Laufmeter bei einer 100m-Rolle (Gesamtpreis ca. CHF 120–150).
Verlegekabel kauft man in der Regel als Kabelrollen (50m, 100m, 305m), da grosse Längen einzeln
konfektioniert werden müssen. Der Preis pro Meter ist deutlich höher als bei einer No-Name-Rolle,
aber das Kabel ist für professionellen Dauerbetrieb ausgelegt.

---

### Kabelmaterial – CU-Massivdraht, AWG 23

**CU** steht für Kupfer (lat. *Cuprum*) – das beste Material für elektrische Leitungen wegen seiner
hohen Leitfähigkeit und Verfügbarkeit. Es gibt zwei Kupfervarianten:

- **CU-Massivdraht** (gewählt): Jede Ader besteht aus **einem einzigen, dicken Draht**.
  - Vorteil: geringe Signaldämpfung über lange Strecken, kostengünstiger
  - Nachteil: starr, bricht bei wiederholtem Biegen → **nur für feste Verlegung geeignet** (Wände, Böden, Kabelkanäle)
  - Einsatz: **Verlegekabel** in der UGV (Universelle Gebäudeverkabelung)

- **CU-Litze** (nicht gewählt, für Patchkabel): Jede Ader besteht aus **vielen dünnen, verdrillten Drähten**.
  - Vorteil: sehr flexibel, hält viele Biegezyklen aus
  - Nachteil: höhere Dämpfung, teurer
  - Einsatz: **Patchkabel** (vom PC zur Wanddose oder im Patchpanel)

**AWG 23** (American Wire Gauge): Ein Normsystem für Drahtdurchmesser. Je kleiner die AWG-Zahl,
desto dicker der Draht. AWG 23 entspricht ca. 0.57 mm Durchmesser und ist der Standardwert für
CAT 6A-Verlegekabel. Ein dickerer Draht hat weniger elektrischen Widerstand → weniger Signalverlust
über lange Strecken → bessere Datenübertragung.

---

### Kabelaufbau – S/FTP (PiMF), 4 × 2 Adern

Ein Twisted-Pair-Kabel besteht immer aus **4 verdrillten Adernpaaren** (= 8 Adern total).
Das Kürzel beschreibt die Abschirmung in der Form `Aussenabschirmung/Paarabschirmung TP`:

| Kürzel | Aussenabschirmung | Paarabschirmung | Schutz |
|--------|-------------------|-----------------|--------|
| U/UTP  | Keine             | Keine           | Minimal |
| F/UTP  | Folie             | Keine           | Mittel |
| U/FTP  | Keine             | Folie je Paar   | Mittel |
| **S/FTP** | **Geflecht** | **Folie je Paar** | **Maximal** |
| SF/FTP | Geflecht + Folie  | Folie je Paar   | Höchste Stufe |

**S/FTP** (auch PiMF = *Pairs in Metal Foil*):
- Jedes der vier Adernpaare ist **einzeln mit Aluminiumfolie** umwickelt → verhindert **Übersprechen** (Crosstalk) zwischen den Paaren
- Ein **verzinntes Kupfergeflecht** umgibt alle vier Paare aussen → schützt gegen **externe elektromagnetische Störfelder** (EMI) von Motoren, Leuchtstoffröhren, Starkstromleitungen
- Das Geflecht ist geerdet → Störsignale werden in die Erde abgeleitet statt ins Kabel eingekoppelt

**Warum 4 Paare verdrillt?** Die Verdrillung ist das Grundprinzip der Störungsunterdrückung bei
Twisted-Pair-Kabeln. Jedes Paar führt zwei entgegengesetzte Signale (differentielles Signal).
Ein Störfeld trifft beide Adern nahezu gleich stark (Gleichtaktstörung). Da die Signale am Empfänger
subtrahiert werden, heben sich die Störungen gegenseitig auf. Je enger die Verdrillung, desto besser
die Unterdrückung.

---

### Störungsabwehrmassnahmen

Das Kabel verwendet **drei aufeinanderfolgende Schutzmassnahmen**:

1. **Verdrillung der Adernpaare** (Twisted Pair): Physikalisches Grundprinzip – Störungen werden
   durch differentielles Signalführen aufgehoben. Wirkt hauptsächlich bei niederfrequenten Störungen.

2. **Aluminiumfolie pro Adernpaar** (Paarabschirmung): Verhindert *Crosstalk* – also das
   Übersprechen von Signalen zwischen benachbarten Paaren im selben Kabel. Bei hohen
   Übertragungsfrequenzen (500 MHz bei CAT 6A) ist das ohne Paarabschirmung ein grosses Problem.

3. **Verzinntes Kupfergeflecht aussen** (Gesamtabschirmung): Schützt gegen externe Störquellen
   ausserhalb des Kabels. Das Geflecht wirkt wie ein *Faradayscher Käfig* – elektrische Felder
   können nicht eindringen. Besonders wichtig neben Starkstromleitungen (230V/400V), Motoren,
   Frequenzumrichtern, Leuchtstoffröhren.

**Fazit:** S/FTP ist die störungsresistenteste Kupferkabelvariante und damit ideal für Betriebsumgebungen,
wo elektrische Geräte und Maschinen betrieben werden.

---

### Ethernet-Medientyp – 10GBase-T

Das Format lautet immer: `[Geschwindigkeit]Base-[Medium]`

- **10G** = 10 Gigabit pro Sekunde = 10'000 Mbit/s
- **Base** = Baseband-Übertragung: Das gesamte Kabel trägt nur **ein** Signal, kein Frequenzmultiplexing
- **T** = Twisted Pair (Kupferkabel mit verdrillten Adernpaaren)

**Vergleich der Medientypen auf Kupfer:**

| Bezeichnung   | Geschwindigkeit | Mindest-Kategorie | Max. Distanz |
|---------------|----------------|-------------------|-------------|
| 100Base-TX    | 100 Mbit/s     | CAT 5e            | 100 m       |
| 1000Base-T    | 1 Gbit/s       | CAT 5e            | 100 m       |
| 10GBase-T     | 10 Gbit/s      | **CAT 6A**        | **100 m**   |
| 10GBase-T     | 10 Gbit/s      | CAT 6             | nur ~55 m   |
| 25GBase-T     | 25 Gbit/s      | CAT 8             | 30 m        |

Das gewählte Kabel unterstützt **10GBase-T bis 100 m** – also die volle Standardlänge der UGV –
weil CAT 6A die dafür nötige Bandbreite von 500 MHz liefert.

---

### Datendurchsatz – 10 Gbit/s

Der Datendurchsatz (auch *Datenrate* oder *Bandbreite*) gibt an, wie viele Bits pro Sekunde
übertragen werden können.

**Rechenbeispiele zum Verständnis:**
- Eine 4K-Filmdatei (25 GB) würde bei 10 Gbit/s in ~**20 Sekunden** übertragen
- Bei 1 Gbit/s (normales Gigabit-Ethernet) dauert das ~**200 Sekunden**
- Bei 100 Mbit/s (älterer Standard) ~**2000 Sekunden** = über 30 Minuten

**Wichtig:** Nicht verwechseln mit Megabyte/s!  
10 Gbit/s = 10'000 Mbit/s = **1'250 MB/s** (÷ 8, da 1 Byte = 8 Bit)

Für heutige Betriebsanforderungen (Server, NAS, Virtualisierung, Cloud-Backup) ist 10 Gbit/s
zukunftssicher. Normales Gigabit-Ethernet reicht heute zwar noch für die meisten PCs, aber
Server-to-Server-Verbindungen oder Fileserver profitieren massiv von 10GBase-T.

---

### Kabelkategorie – CAT 6A, Klasse EA

Die Kabelkategorie ist eine Norm, die festlegt, bis zu welcher **Frequenz** das Kabel zuverlässig
funktioniert. Höhere Frequenz = mehr Datendurchsatz möglich.

| Kategorie | Max. Frequenz | Typischer Einsatz          | Wann eingebaut?          |
|-----------|--------------|---------------------------|--------------------------|
| CAT 5e    | 100 MHz      | 1GBase-T                  | Vor 2010, Altbau         |
| CAT 6     | 250 MHz      | 1GBase-T, 10G bis 55m     | 2005–2015                |
| **CAT 6A**| **500 MHz**  | **10GBase-T bis 100m**    | **Ab 2010, Empfehlung heute** |
| CAT 7     | 600 MHz      | 10GBase-T                 | Spezialanwendungen, teuer |
| CAT 8     | 2000 MHz     | 25/40GBase-T bis 30m      | Rechenzentren            |

**Klasse EA** ist die Kanalklassifizierung nach ISO/IEC 11801 – sie bezieht sich auf das gesamte
Übertragungssystem (Kabel + Stecker + Dose), nicht nur das Kabel selbst. "EA" entspricht
CAT 6A und ist die Mindestanforderung für 10GBase-T über 100 m.

**Warum CAT 6A und nicht CAT 7?** CAT 7 bietet zwar 600 MHz, benötigt aber spezielle
GG45- oder TERA-Stecker (nicht der normale RJ45) und ist teurer. Da 10GBase-T bereits mit
CAT 6A und normalen RJ45-Steckern perfekt funktioniert, ist CAT 7 für die meisten Betriebe
überdimensioniert.

---

### Übertragungsart / Kommunikationsmodus – Vollduplex

Es gibt drei Kommunikationsmodi:

| Modus          | Beschreibung                                  | Beispiel                    |
|----------------|-----------------------------------------------|-----------------------------|
| **Simplex**    | Daten fliessen nur in **eine** Richtung        | Radio, TV (Broadcast)       |
| **Halbduplex** | Beide Richtungen, aber **nicht gleichzeitig** | Walkie-Talkie, älterer Hub  |
| **Vollduplex** | Beide Richtungen **gleichzeitig**             | Telefon, moderner Switch    |

Modernes Ethernet über einen Switch arbeitet immer im **Vollduplex-Modus**: Der Computer kann
gleichzeitig senden und empfangen, ohne auf den anderen warten zu müssen. Das ist möglich, weil
Twisted-Pair-Kabel **4 Adernpaare** haben – separate Paare für Senden und Empfangen.

Bei einem alten **Hub** war nur Halbduplex möglich, weil alle Geräte dasselbe Medium (die Leitung)
teilen mussten. Bei einer Kollision mussten beide aufhören zu senden und es nach einer zufälligen
Wartezeit erneut versuchen (CSMA/CD). Das ist heute bei Switches nicht mehr nötig.

---

### Max. Segmentlänge – 100 m

Die maximale Segmentlänge von **100 m** ist ein Ethernet-Standard (IEEE 802.3) für alle
Twisted-Pair-Verbindungen, unabhängig von der Geschwindigkeit (100Mbit bis 10Gbit).

**Warum genau 100 m?** Bei grösseren Distanzen wird das Signal zu schwach (Dämpfung) und
die Signallaufzeit wird zu gross (bei 10GBase-T sind die Timing-Toleranzen sehr eng). Das Kabel
absorbiert einen Teil der Signalenergie – je länger, desto mehr.

**Zusammensetzung der 100 m in der UGV:**
- Max. **90 m** festes Verlegekabel (Wand/Boden)
- Max. **10 m** Patchkabel gesamt (PC-seitig + Patchpanel-seitig)

Wenn man mehr als 100 m überbrücken muss, benötigt man einen **Switch als Repeater** oder wechselt
auf Glasfaser (dort sind Distanzen von 550 m bis mehrere km möglich).

---

## Warum wurde dieses Kabel gewählt?

### 1. Zukunftssicherheit
Verlegekabel liegt **15–25 Jahre** fest in Wänden und Böden. Eine Neuinstallation kostet ein
Vielfaches des Kabelpreises (Elektriker-Stunden, Wandöffnungen, Wiederherstellung). CAT 6A
mit 10GBase-T ist heute der empfohlene Standard für Neuinstallationen. In 10 Jahren werden
10-Gigabit-Switchports Standard sein – das Kabel ist dann bereits vorhanden.

### 2. Maximale Störungssicherheit
In einem Betrieb gibt es typischerweise viele Störquellen: Elektromotoren, Klimaanlagen,
Leuchtstoffröhren, Starkstromleitungen (230V/400V), Frequenzumrichter, Drucker. Die
**S/FTP-Doppelschirmung** schützt das Signal zuverlässig auch dann, wenn das Kabel neben
Starkstromleitungen verlegt wird (was Elektroinstallateure eigentlich trennen sollten, in der
Praxis aber nicht immer der Fall ist).

### 3. Normkonformität
Das Kabel entspricht **ISO/IEC 11801** und **EN 50173** – das sind die internationalen Normen
für strukturierte Gebäudeverkabelung. Normkonforme Verkabelung ist Voraussetzung für eine
professionelle Dokumentation und erleichtert spätere Erweiterungen oder Fehlersuche.

### 4. Schweizer Qualität
Dätwyler ist ein renommierter Schweizer Hersteller. Für einen betrieblichen Einsatz ist die
Herkunft und Qualitätssicherung relevanter als bei einem Heimnetz – ein Ausfall kostet
Produktivität und Geld.

---

## Preisliche Alternativen

| Kabel                      | Lieferant  | Preis/m      | Schirmung | Kategorie | Bewertung |
|----------------------------|-----------|--------------|-----------|-----------|-----------|
| **Dätwyler Uninet 7060** *(Wahl)* | Digitec | ~CHF 1.40 | **S/FTP** | CAT 6A | Beste Wahl für Betrieb |
| Digitus U/FTP CAT 6A 100m  | Digitec   | **CHF 0.43** | U/FTP     | CAT 6A    | Gut für störungsarme Büros |
| Digitus U/UTP CAT 6A 100m  | Digitec   | ~CHF 0.59    | keine     | CAT 6A    | Nur für störungsfreie Umgebungen |
| Digitus U/UTP CAT 6 100m   | Digitec   | ~CHF 0.35    | keine     | CAT 6     | 10G nur bis 55m – nicht empfohlen |

### Erklärung der Alternativen

**Digitus U/FTP CAT 6A (CHF 0.43/m)** wäre die günstigste Alternative, die noch CAT 6A erfüllt.
U/FTP bedeutet: keine Aussenabschirmung, aber Folie je Adernpaar. Das schützt gut gegen
internes Übersprechen, aber nicht gegen externe Störfelder. Für ein ruhiges Büro ohne schwere
elektrische Geräte in der Nähe völlig ausreichend. Für einen Industriebetrieb nicht ideal.

**Digitus U/UTP CAT 6A** hat gar keine Abschirmung. Das ist für private Heimnetzwerke
problemlos, für Betriebe mit Maschinen aber riskant. Übertragungsfehler durch EMI führen zu
Paketverlusten und langsameren Verbindungen.

**Digitus CAT 6 (CHF 0.35/m)** unterstützt zwar auch 10GBase-T, aber nur bis ca. 55 m statt
100 m. Da Verlegekabel lange im Einsatz bleiben, ist der minimale Preisunterschied zu CAT 6A
nicht die Einschränkung wert.

**Fazit:** Der Aufpreis von ca. CHF 1.00/m für das Dätwyler S/FTP-Kabel gegenüber der
günstigsten Alternative ist bei einer 100m-Rolle ein Gesamtmehrpreis von CHF 97.–. Verglichen
mit den Kosten einer Neuinstallation in 5 Jahren (Elektriker, Materialien, Betriebsausfall)
ist das eine sehr sinnvolle Investition.

---

## Quellen

- Digitec Produktseite Dätwyler Uninet 7060 4P: https://www.digitec.ch (Art.-Nr. 2750330)
- Digitec Produktseite Digitus U/FTP CAT 6A 100m: https://www.digitec.ch (Art.-Nr. 10282531)
- ISO/IEC 11801 – Norm für strukturierte Gebäudeverkabelung
- Theoriedokumentation ARJ Modul 117: https://jarnold.ch/ict/117/theory_117.pdf
