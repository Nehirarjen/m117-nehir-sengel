
# Selbstreflexion – TAG-4

**Modul:** 117 | **Block:** 2 | **Datum:** 13.01.2026  
**Thema:** Dateizugriffsrechte

---

## Mein Lernertrag

1 Was habe ich heute verstanden oder dazugelernt?  
Ich habe verstanden, warum ein Betriebssystem ein Benutzer-Accounting benötigt und wie Zugriffsrechte durch lokale oder zentrale Benutzerverwaltung (wie Microsofts Active Directory) gesteuert werden. Besonders klar wurde mir der Unterschied zwischen den NTFS-Sicherheitsberechtigungen (Vollzugriff, Ändern, Lesen, Schreiben, Ausführen) und wie diese auf Dateien und Ordner angewendet werden.

2 Welche Inhalte oder Fähigkeiten kann ich jetzt besser erklären oder anwenden?  
Ich kann die Standard-Berechtigungen im Windows-Dateisystem zuordnen und erklären, was ein Benutzer mit Rechten wie "Ändern" im Vergleich zu "Schreiben" oder "Lesen" darf. Zudem kann ich das Prinzip der Vererbung von Zugriffsrechten erklären und weiss, dass das FAT32-Dateisystem im Gegensatz zu NTFS keine lokalen Dateiberechtigungen unterstützt – weshalb sensible Daten auf einem verlorenen FAT32-Stick für jeden sofort einsehbar sind.

---

## Meine Herausforderungen

1 Was war schwierig, unklar oder verwirrend?  
Die genaue Abgrenzung zwischen den Rechten "Ändern" und "Vollzugriff" war anfangs verwirrend. Dass man mit "Ändern" zwar Dateien löschen und modifizieren, aber keine Berechtigungen anpassen oder den Besitz übernehmen darf, war mir nicht sofort logisch. Auch die Tatsache, dass NTFS-Rechte beim Kopieren auf einen anderen USB-Stick je nach Dateisystem verloren gehen können, erforderte einiges Umdenken.

2 Welche Fragen habe ich noch?  
Wie verhalten sich die Berechtigungen genau, wenn sich NTFS-Freigabeberechtigungen (über das Netzwerk mit `\\IP\Freigabe`) und die lokalen NTFS-Sicherheitsberechtigungen überschneiden – welches Recht setzt sich am Ende durch?

---

## Mein Lernprozess

1 Wie habe ich gearbeitet (Konzentration, Zusammenarbeit, Strategie)?  
Ich habe mich konzentriert den theoretischen Grundlagen gewidmet und die Tabellen zu den Berechtigungen ausgefüllt. Beim praktischen Experiment mit dem NTFS-formatierten USB-Stick habe ich eng mit meinem Banknachbarn zusammengearbeitet, um zu überprüfen, ob ein fremder PC die restriktiven Dateirechte einhält oder ignoriert.

2 Was hat gut funktioniert?  
Das Lösen der Zuordnungsaufgaben (D2–D5) zu den Microsoft-Sicherheitseinstellungen hat geholfen, das Schema schnell zu verinnerlichen. Der Praxis-Test mit dem USB-Stick hat die graue Theorie sofort greifbar und verständlich gemacht.

3 Was möchte ich beim nächsten Mal verbessern?  
Ich möchte offene Fragen zu Netzwerkpfaden und Freigaben direkt während der Praxisübung mit der Lehrperson klären, anstatt zu viel Zeit mit dem Suchen in den Dokumenten zu verlieren.
