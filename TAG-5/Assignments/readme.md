
#  Aufgabe 5.1 

Dieses Dokument enthält die offiziellen Musterlösungen und Konfigurationsdaten zu **Aufgabe 5.1** aus dem Modul 117.

---

##  Teil 1: Netzwerk- und Broadcastadressen (Subnetze A bis I)

Basierend auf der übergeordneten Netzwerkadresse `10.0.0.0/16` und der Vorgabe, alle Subnetze standardmäßig mit einer `/24`-Subnetzmaske (`255.255.255.0`) zu versehen, ergeben sich folgende Adressstrukturen:

| Subnetz | Subnetz-Präfix | Netzwerkadresse | Broadcastadresse | Zugeordnete Router-Schnittstellen (Musterlösung) |
| :---: | :--- | :--- | :--- | :--- |
| **A** | `10.0.1.0/24` | **`10.0.1.0`** | **`10.0.1.255`** | RT-2 eth3: `10.0.1.1`<br>RT-3 eth2: `10.0.1.2` |
| **B** | `10.0.2.0/24` | **`10.0.2.0`** | **`10.0.2.255`** | RT-3 eth0: `10.0.2.1` |
| **C** | `10.0.3.0/24` | **`10.0.3.0`** | **`10.0.3.255`** | RT-2 eth2: `10.0.3.1` |
| **D** | `10.0.4.0/24` | **`10.0.4.0`** | **`10.0.4.255`** | RT-2 eth1: `10.0.4.1` |
| **E** | `10.0.5.0/24` | **`10.0.5.0`** | **`10.0.5.255`** | RT-4 eth1: `10.0.5.1` |
| **F** | `10.0.6.0/24` | **`10.0.6.0`** | **`10.0.6.255`** | RT-4 eth2: `10.0.6.1` |
| **G** | `10.0.7.0/24` | **`10.0.7.0`** | **`10.0.7.255`** | RT-1 eth3: `10.0.7.1`<br>RT-3 eth1: `10.0.7.2` *(Auch `/30` möglich)* |
| **H** | `10.0.8.0/24` | **`10.0.8.0`** | **`10.0.8.255`** | RT-1 eth2: `10.0.8.1`<br>RT-2 eth0: `10.0.8.2` *(Auch `/30` möglich)* |
| **I** | `10.0.9.0/24` | **`10.0.9.0`** | **`10.0.9.255`** | RT-1 eth0: `10.0.9.1`<br>RT-4 eth0: `10.0.9.2` *(Auch `/30` möglich)* |

---

##  Teil 2: IP-Konfiguration für die Endgeräte (PCs)

Jeder PC benötigt eine eindeutige IP-Adresse aus dem nutzbaren Adressbereich seines jeweiligen Netzes sowie die passende Subnetzmaske und das korrekte Standardgateway (IP des lokalen Routers).

###  PCs im Subnetz B (z. B. PC-B1)
* **IP-Adresse:** `10.0.2.10` *(Oder jede freie Host-IP von `10.0.2.2` bis `10.0.2.254`)*
* **Subnetzmaske:** `255.255.255.0`
* **Standardgateway:** `10.0.2.1` *(Schnittstelle RT-3 eth0)*

###  PCs im Subnetz C (z. B. PC-C1)
* **IP-Adresse:** `10.0.3.10` *(Oder jede freie Host-IP von `10.0.3.2` bis `10.0.3.254`)*
* **Subnetzmaske:** `255.255.255.0`
* **Standardgateway:** `10.0.3.1` *(Schnittstelle RT-2 eth2)*

###  PCs im Subnetz D (z. B. PC-D1)
* **IP-Adresse:** `10.0.4.10` *(Oder jede freie Host-IP von `10.0.4.2` bis `10.0.4.254`)*
* **Subnetzmaske:** `255.255.255.0`
* **Standardgateway:** `10.0.4.1` *(Schnittstelle RT-2 eth1)*

###  PCs im Subnetz E (z. B. PC-E1)
* **IP-Adresse:** `10.0.5.10` *(Oder jede freie Host-IP von `10.0.5.2` bis `10.0.5.254`)*
* **Subnetzmaske:** `255.255.255.0`
* **Standardgateway:** `10.0.5.1` *(Schnittstelle RT-4 eth1)*

###  PCs im Subnetz F (z. B. PC-F1)
* **IP-Adresse:** `10.0.6.10` *(Oder jede freie Host-IP von `10.0.6.2` bis `10.0.6.254`)*
* **Subnetzmaske:** `255.255.255.0`
* **Standardgateway:** `10.0.6.1` *(Schnittstelle RT-4 eth2)*
