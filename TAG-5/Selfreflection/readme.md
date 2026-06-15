
# Selbstreflexion – TAG-5

**Modul:** 117 | **Block:** 2 | **Datum:** 15.06.2026  
**Thema:** Subnetting Light

---

## Mein Lernertrag

1 Was habe ich heute verstanden oder dazugelernt?  
Ich habe verstanden, wie ein grosser Netzwerkbereich (`10.0.0.0/16`) logisch in kleinere Subnetze unterteilt wird. Durch eine `/24`-Subnetzmaske wird das dritte Oktett fest als Kennung für das jeweilige Teilnetz (Subnetz A bis I) definiert, um Netzwerke sauber voneinander zu trennen.

2 Welche Inhalte oder Fähigkeiten kann ich jetzt besser erklären oder anwenden?  
Ich kann für jedes Subnetz die Netzwerkadresse (z. B. `.0`) und die Broadcastadresse (z. B. `.255`) bestimmen. Zudem kann ich PCs freie Host-IPs zuweisen und das Standardgateway konfigurieren, welches der IP-Adresse des lokalen Router-Interfaces entspricht.

---

## Meine Herausforderungen

1 Was war schwierig, unklar oder verwirrend?  
Anfangs war es verwirrend zu unterscheiden, welche Subnetze für Host-PCs gedacht sind und welche nur als reine Verbindungsstrecken (Router-Links) dienen. Auch dass Transfer-Netze optional mit einer `/30`-Maske konfiguriert werden können, um IPs zu sparen, erforderte Umdenken.

2 Welche Fragen habe ich noch?  
Wie läuft das Routing genau ab, wenn ein PC Daten über mehrere Router-Schnittstellen und Transfer-Subnetze hinweg an ein Endgerät in einem entfernten Subnetz sendet?

---

## Mein Lernprozess

1 Wie habe ich gearbeitet (Konzentration, Zusammenarbeit, Strategie)?  
Ich habe mich konzentriert der logischen Netzwerktopologie gewidmet. Beim Lösen von Aufgabe 5.1 habe ich systematisch eine Tabelle für die Subnetze A bis I angelegt, um Netz-IDs, Broadcastadressen und Gateways strukturiert zuzuordnen und Fehler zu vermeiden.

2 Was hat gut funktioniert?  
Das schrittweise Ableiten der IP-Bereiche anhand des veränderten dritten Oktetts (`10.0.1.0`, `10.0.2.0` etc.) funktionierte sehr gut. Die Struktur der Musterlösung hat das Zusammenspiel zwischen Subnetzen und Routern sofort visuell greifbar gemacht.

3 Was möchte ich beim nächsten Mal verbessern?  
Ich möchte komplexe Topologien künftig zuerst grob skizzieren, um die Verbindungen und Schnittstellen noch schneller zu erfassen, bevor ich mit den eigentlichen IP-Berechnungen beginne.
