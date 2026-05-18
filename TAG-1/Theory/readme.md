
# Theorieeintrag: Ethernetverkabelung & Netzwerkgrundlagen

**Modul:** 117 | **Block:** 1  
**Thema:** Ethernetverkabelung, Adressgrundlagen & Topologien  

---

## 1. Bit vs. Byte und Präfixe

### Unterschied zwischen Bit und Byte
* **Bit (Binary Digit):** Ist die kleinste Informationseinheit in der Informatik. Es kann genau zwei Zustände annehmen: `0` oder `1`.
* **Byte:** Besteht aus einer Sequenz von **8 Bit**. Mit einem Byte lassen sich $2^8 = 256$ verschiedene Zustände (z. B. Zeichen) darstellen.
* **Anwendung im Alltag:** Speicherkapazitäten (RAM, Festplatten) werden üblicherweise in **Byte** angegeben (z. B. GB), während Datenübertragungsraten (Internetgeschwindigkeit) in **Bit pro Sekunde** gemessen werden (z. B. Mbit/s).

### SI-Präfixe vs. IEC-Präfixe
* **SI-Präfixe (Dezimalsystem):** Basieren auf der Basis $10$ ($10^3 = 1000$). Sie werden für standardisierte physikalische Masseinheiten (Meter, Sekunden, Gramm) sowie im Marketing von Festplattenherstellern verwendet.
* **IEC-Präfixe (Binärsystem):** Basieren auf der Basis $2$ ($2^{10} = 1024$). Sie werden in Betriebssystemen verwendet, um digitalen Speicherplatz exakt anzugeben, da Computer binär arbeiten.

#### Korrigierte Übersicht der Aufgaben (A1):
1. **300'000 m** verkürzt mit SI-Präfix: **300 km** (Kilometer)
2. **0.005 s** verkürzt mit SI-Präfix: **5 ms** (Millisekunden)
3. **5 g** verkürzt mit SI-Präfix: **5 g** (Bleibt unverändert, da Gramm die Basiseinheit mit Präfix-Charakter ist / keine sinnvolle weitere Verkürzung)
4. **Speicherplatzberechnung für 20 Dateien zu je 512 Byte:**
   $$\text{Gesamtgrösse} = 20 \times 512 \text{ Byte} = 10'240 \text{ Byte}$$
   Umrechnung in IEC-Präfix: 
   $$10'240 \text{ Byte} \div 1024 = \mathbf{10 \text{ KiB}} \text{ (Kibibyte)}$$

---

## 2. Netzwerktopologien

Eine Netzwerktopologie beschreibt die strukturelle Anordnung von Geräten und Leitungen in einem Netzwerk.

### Wichtige Topologietypen:
* **Bus-Topologie:** Alle Geräte hängen an einem einzigen Übertragungsmedium. Fällt das Hauptkabel aus, blockiert das gesamte Netzwerk.
* **Stern-Topologie:** Jedes Endgerät ist separat mit einem zentralen Verteiler (Switch) verbunden. Fällt ein Kabel aus, betrifft dies nur das eine Gerät.
* **Baum-Topologie:** Eine hierarchische Verknüpfung mehrerer Stern-Topologien (Switches werden untereinander kaskadiert).
* **Mesh-Topologie (Vermaschtes Netz):** Jedes Gerät ist mit mehreren oder allen anderen Geräten verbunden. Bietet maximale Redundanz und Ausfallsicherheit, ist jedoch sehr teuer und aufwendig zu verkabeln.

### Korrektur & Ergänzung zu Aufgabe A2 (Wohngemeinschaft):
Deine vorgeschlagene Struktur mit 5 Switches (einer pro Zimmer) verbindet die PCs der WG-Mitglieder. 
* **Topologie-Typ:** Dies entspricht einer **Stern-Baum-Topologie**. Die PCs bilden in den Zimmern jeweils einen Stern um den lokalen Switch, und die Switches sind hierarchisch untereinander bzw. mit dem zentralen Internetrouter verbunden.
* **Hinweis zu Mesh:** Das WG-Netz ist **keine Mesh-Topologie**, da keine redundanten Leitungen zwischen den Switches gezogen wurden. Für ein Mesh-Netzwerk müssten die Switches untereinander mehrfach vermascht sein, was zudem ein Protokoll wie *Spanning Tree (STP)* erfordern würde, um Netzwerkschleifen (Loops) zu verhindern.

---

## 3. Ethernet-Kabelmedien und Kabelaufbau

### CU-Litzenkabel vs. CU-Massivdraht (Verlegekabel)
* **CU-Massivdraht (UGV- / Verlegekabel):** Die Adern bestehen aus einem einzigen, dicken Kupferdraht (z. B. AWG 23). Es ist starr, besitzt hervorragende elektrische Eigenschaften für lange Distanzen und wird fest in Wänden und Kabelkanälen verlegt. Es bricht, wenn es häufig bewegt wird.
* **CU-Litzenkabel (Patchkabel):** Die Adern bestehen aus vielen dünnen, miteinander verflochtenen Kupferdrähtchen. Es ist hochflexibel und wird für die Verbindung zwischen Steckdose und PC oder im Rack verwendet. Für lange Strecken ist es aufgrund der höheren Dämpfung ungeeignet.

### Kabelbezeichnungen nach ISO/IEC 11801
Die Bezeichnung folgt dem Schema **XX/YTP**:
* **XX** = Gesamtschirmung des Kabels (aussen)
* **Y** = Einzelschirmung der Adernpaare
* **TP** = Twisted Pair (verdrillte Adernpaare)

| Kürzel | Bedeutung | Beschreibung |
|:---|:---|:---|
| **U** | Unshielded | Ungeschirmt |
| **F** | Foil | Folienabschirmung (Aluminiumfolie) |
| **S** | Braided Shield | Geflechtschirmung (Kupfergeflecht) |

* **S/FTP (Dätwyler Uninet 7060):** Gesamtschirm aus Kupfergeflecht (**S**), Adernpaare einzeln mit Folie geschützt (**F/TP**). Bietet den besten Schutz gegen elektromagnetische Störungen (EMI).
* **U/FTP:** Keine Gesamtschirmung (**U**), aber die Adernpaare sind einzeln mit Folie geschirmt (**F/TP**).
* **U/UTP:** Komplett ungeschirmt. Günstig und flexibel, aber extrem anfällig für Störungen und bei 10 Gbit/s stark distanzbeschränkt.

### Kabelkategorien und Frequenzen
Die Kategorie (Cat) bestimmt die maximale Signalfrequenz und damit die maximale Datenrate auf einer Standardlänge von 100 Metern.

* **Cat 6:** Bis 250 MHz spezifiziert. Unterstützt 1 Gbit/s standardmässig bis 100m. 10 Gbit/s (10GBase-T) ist nur auf kurzen Distanzen (bis ca. 55m unter Idealbedingungen) möglich.
* **Cat 6A:** Bis 500 MHz spezifiziert. Ermöglicht **10 Gbit/s (10GBase-T)** vollumfänglich über die maximale Segmentlänge von **100 Metern** (90m Verlegekabel + 10m Patchkabel).
* **Cat 7:** Bis 600 MHz spezifiziert. Setzt zwingend eine Einzelschirmung der Paare voraus (S/FTP).
