# Challenge-1 – Ethernet-Verlegekabel

**Modul:** 117 | **Block:** 1 | **Datum:** _[Datum]_

---

## Gewähltes Kabel

**Dätwyler Uninet 7060 4P – CAT 6A S/FTP**  
Lieferant: Digitec.ch | Art.-Nr. 2750330 | ca. CHF 1.40 / Meter (100m-Rolle)

---

## Kenndaten

| Kenndaten | Wert |
|-----------|------|
| **Kabelmaterial** | CU-Massivdraht, AWG 23 |
| **Kabelaufbau** | S/FTP (PiMF), 4 verdrillte Paare |
| **Störungsabwehr** | Aluminiumfolie je Paar + Kupfergeflecht aussen |
| **Ethernet-Medientyp** | 10GBase-T |
| **Datendurchsatz** | 10 Gbit/s |
| **Kabelkategorie** | CAT 6A, Klasse EA, 500 MHz |
| **Kommunikationsmodus** | Vollduplex |
| **Max. Segmentlänge** | 100 m (90m Verlegekabel + 10m Patchkabel) |

---

## Erklärung der Kenndaten

**CU-Massivdraht, AWG 23:** Ein einziger dicker Kupferdraht pro Ader. Starr, daher nur für
feste Verlegung geeignet (Wände, Böden). AWG 23 = Drahtdurchmesser 0.57 mm – dicker
Draht bedeutet weniger Widerstand und weniger Signaldämpfung. Patchkabel verwenden
CU-Litze (viele dünne Drähte) wegen der nötigen Flexibilität.

**S/FTP (PiMF):** Abschirmungsschema `Aussen/Paar TP`. S = Kupfergeflecht aussen,
FTP = Folie je Adernpaar. Drei Schutzstufen:
1. Verdrillung → hebt Gleichtaktstörungen gegenseitig auf
2. Aluminiumfolie je Paar → verhindert Crosstalk zwischen Paaren
3. Kupfergeflecht aussen → schützt gegen externe EMI (Motoren, Starkstrom)

**10GBase-T:** 10G = 10 Gbit/s, Base = Baseband, T = Twisted Pair. Benötigt min. CAT 6A.

**10 Gbit/s:** Entspricht 1'250 MB/s – zehnmal schneller als normales Gigabit-Ethernet.

**CAT 6A:** Getestet bis 500 MHz. Einzige Kategorie, die 10GBase-T über die vollen 100 m
mit normalem RJ45 ermöglicht. CAT 6 (250 MHz) schafft 10G nur bis ca. 55 m.

**Vollduplex:** Senden und Empfangen gleichzeitig, da ein Switch jede Verbindung dediziert
behandelt – keine Kollisionen, volle Bandbreite in beide Richtungen.

**100 m Segmentlänge:** IEEE-Standard für Twisted-Pair. Aufgeteilt in max. 90 m
Verlegekabel (fest in der Wand) und max. 10 m Patchkabel gesamt.

---

## Warum dieses Kabel?

Verlegekabel liegt 15–25 Jahre in der Wand – eine Neuinstallation kostet ein Vielfaches
des Kabelpreises. CAT 6A mit S/FTP ist der empfohlene Standard für Neuinstallationen:
zukunftssicher (10GBase-T), störungsresistent (Doppelschirmung) und normkonform
(ISO/IEC 11801). In Betrieben mit Maschinen und Starkstromleitungen ist S/FTP gegenüber
günstigen U/UTP-Kabeln klar überlegen.

---

## Preisliche Alternativen

| Kabel | Preis/m | Schirmung | Einschränkung |
|-------|---------|-----------|---------------|
| **Dätwyler S/FTP CAT 6A** *(Wahl)* | ~CHF 1.40 | S/FTP | – |
| Digitus U/FTP CAT 6A | CHF 0.43 | U/FTP | Kein Aussengeflecht |
| Digitus U/UTP CAT 6 | CHF 0.35 | keine | 10G nur bis ~55 m |

---

## Quellen

- Digitec.ch, Art.-Nr. 2750330
- ARJ Theoriedokumentation: https://jarnold.ch/ict/117/theory_117.pdf
