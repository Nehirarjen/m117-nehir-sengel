
# Selbstreflexion: Themenblock Netzwerkadressierung

**1. Was habe ich gelernt und was lief gut?**
Ich habe verstanden, wie IP-Adressen mithilfe der Subnetzmaske logisch in Netz-ID und Host-ID unterteilt werden und warum diese Separierung zur Vermeidung von Broadcast-Überlastungen notwendig ist. Das Bestimmen von Netzwerk- und Broadcastadressen bei den Standardmasken (/8, /16, /24) fiel mir leicht, ebenso wie das logische Prüfen, ob zwei PCs direkt im selben Netz kommunizieren können oder einen Router benötigen.

**2. Was war schwierig oder wo hatte ich Probleme?**
Anfangs war es etwas verwirrend zu sehen, wie sich fehlerhafte Masken-Konfigurationen (wenn PC1 eine /16 und PC2 eine /24 Maske im selben IP-Bereich nutzt) auswirken. Erst durch das genaue Analysieren des Rückwegs der Datenpakete wurde mir klar, warum eine saubere, bidirektionale Kommunikation in solchen Fällen asymmetrisch scheitert.

**3. Wie bin ich vorgegangen und was mache ich das nächste Mal anders?**
Ich bin die theoretischen Grundlagen Schritt für Schritt durchgegangen und habe mir die Analogien zur realen Welt (wie die Telefonvorwahl) als Merkhilfe genommen. Bei den Kommunikationsaufgaben habe ich mir die Netzgrenzen farblich im Kopf markiert. Das nächste Mal werde ich direkt ein Simulationswerkzeug wie den Cisco Packet Tracer nutzen, um die asymmetrischen IP-Konfigurationen direkt visuell zu testen und per Ping zu validieren.
