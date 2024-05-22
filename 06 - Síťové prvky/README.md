# 6 - Aktivní a pasivní síťové prvky, typy, parametry, konfigurace

## Aktivní prvky

Za aktivní prvky se považují všechny prvky, které nějakým způsobem mění signál.

---

### Hub (rozbočovač)
- rozbočuje signál do více směrů
- je součástí kolizní domény (pokud dvě zařízení komunikují, třetí nemůže vysílat)
- dnes už minulost, nahrazen switchi

**Typy:**
- Pasivní huby (dnes již nepoužívané)
- Aktivní huby (zesilují signál, ale stále vytvářejí jednu kolizní doménu)
- Inteligentní huby (mohou monitorovat provoz, ale neoddělují kolizní domény)

**Parametry:**
- Počet portů (obvykle 4, 8, 16 nebo 24)
- Rychlost (10 Mbps, 100 Mbps)
- Podpora poloduplexu/plného duplexu

Huby obvykle nevyžadují žádnou konfiguraci.

---

### Switch (přepínač)
- slouží k "chytrému rozbočení" sítě
- rozděluje síť na více kolizních domén (více zařízení může vysílat najednou, aniž by se zarušovaly)
- udržuje si tabulku MAC adres, kterou plní podle přijaté komunikace
- posílá paket pouze na port, kde se nachází cílová MAC adresa, pokud ho nezná, broadcastuje

**Typy:**

- Nepřepínané (unmanaged) – základní funkce, bez možnosti konfigurace
- Přepínané (managed) – umožňují konfiguraci VLAN, QoS, STP, atd.
- Smart switche – nabízejí některé funkce managed switchů za nižší cenu
- L2 switche – pracují na druhé vrstvě modelu OSI (linková)
- L3 switche – pracují na třetí vrstvě modelu OSI (síťová), mají funkce routeru

**Parametry:**

- Počet portů (od 4 do několika set)
- Rychlost (10/100 Mbps, 1 Gbps, 10 Gbps, 40 Gbps, 100 Gbps)
- Podpora PoE (Power over Ethernet) – napájení zařízení přes ethernetový kabel
- Velikost MAC tabulky
- Podpora VLAN, QoS, STP, agregování linek (LACP), zrcadlení portů (port mirroring)

**Konfigurace:**

- Přiřazení portů do VLAN (logické dělení sítě pomocí VLAN ID, trunk porty přenesou víc vlanek enkapsulací dot1q + nativní vlan)
- Nastavení QoS (Quality of Service) – prioritizace provozu
- Konfigurace STP (Spanning Tree Protocol) – prevence smyček (z kružnice strom), root bridge apod.
- Nastavení LACP (Link Aggregation Control Protocol) – agregování linek
- Konfigurace zrcadlení portů (port mirroring) – monitoring provozu
- Port security: omezení počtu MAC adres na portu

---

### Router (směřovač)
- směruje pakety mezi různými sítěmi
- udržuje si tabulku IP adres
- posílá paket pouze na port, kde se nachází cílová IP adresa, pokud ji nezná, používá default route
- může mít NAT (Network Address Translation) - překládá veřejnou IP adresu na privátní a naopak
- !!! Pozor - dnes hovorově jako router označujeme domácí zařízení, které zahrnuje i switch, AP, firewall, ..., avšak ROUTER v pravém slova smyslu tyto funkce neplní!
- Statické směřování (definované administrátorem) / Směrovací protokoly: Link state (řeší mnoho parametrů - rychlost linky, počet hopů...) např. OSPF) / Distance vector (počítá pouze počet hopů), např. RIP)
- Když přijde pakcet
  - Počítá adresu sítě podle ip a masky
  - Hledá v tabulce nejdelší shodu (pokud nenajde, hledá default routu)
  - Posílá

**Typy:**

- Nepřepínané (unmanaged) – základní funkce, bez možnosti konfigurace
- Přepínané (managed) – umožňují konfiguraci směrovacích protokolů, NAT, firewallu, VPN, atd.
- Edge routery – propojují vnitřní síť s internetem
- Core routery – směrují provoz uvnitř rozsáhlých sítí

**Parametry:**

- Počet a typ portů (Ethernet, SFP, ...)
- Rychlost portů
- Podpora IPv4 a IPv6
- Podpora dynamických směrovacích protokolů (RIP, OSPF, BGP, ...)
- Podpora NAT, PAT
- Podpora firewallu, VPN
- Výkon (počet paketů za sekundu)

**Konfigurace:**

- Nastavení IP adres a směrovacích protokolů
- Konfigurace NAT, PAT
- Nastavení pravidel firewallu
- Konfigurace VPN
- Konfigurace QoS
- Konfigurace DHCP serveru
- Konfigurace SNMP (Simple Network Management Protocol) – monitoring routeru

---

### Modem
- slouží k převodu mezi digitálním a analogovým signálem


**Typy:**

- VDSL modemy
- ADSL modemy
- Kabelové modemy (DOCSIS)
- LTE modemy- 

**Parametry:**

- Rychlost downloadu/uploadu
- Podpora standardů (VDSL2, ADSL2+, DOCSIS 3.1, ...)
- Počet a typ portů (Ethernet, USB, ...)

**Konfigurace:**

- Nastavení parametrů připojení (VPI, VCI, ...)
- Nastavení Wi-Fi sítě (pokud modem obsahuje Wi-Fi router)

---

### AP (Access Point)
- slouží k připojení bezdrátových zařízení do kabelové sítě

**Typy:**

- Samostatné AP
- AP integrované v routeru
- Podnikové AP (větší dosah, více funkcí)

**Parametry:**

- Podporované standardy (802.11a/b/g/n/ac/ax)
- Rychlost
- Počet a typ antén
- Výkon vysílání
- Podpora PoE

**Konfigurace:**

- Nastavení SSID (název sítě)
- Nastavení zabezpečení (WPA2, WPA3)
- Nastavení kanálu
- Nastavení výkonu vysílání

---

### Repeater
- zesiluje signál

---

---

## Pasivní prvky

Pasivní prvky nijak signál nemění.

### Kabely
- kroucená dvoulinka (UTP, STP, FTP)
- koaxiální kabel
- optický kabel - vysoká rychlost, až 10km, odolnost proti rušení, ale nejdražší
- ...

**Ethernetové kabely (kroucená dvoulinka)** dělíme na kategorie podle rychlosti a délky:
- Cat 5e (1000 Mbps, 100 m)
- Cat 6 (10 Gbps, 55 m)
- Cat 6a (10 Gbps, 100 m)
- Cat 7 (10 Gbps, 100 m)
- Cat 8 (25/40 Gbps, 30 m)
- ...

Při krimpování kabelů se obvykle využívají 2 standardy:
- T568A
- T568B

Kabely mohou být straight-through (přímý) nebo crossover (křížený).


**Optika**
- Single-mode (jednovidová) - pro velké vzdálenosti, menší ztráty
- Multi-mode (vícevidová) - použití více paprsků v jednom vlákně, pro kratší vzdálenosti, větší ztráty. Materiál s optckým gradientem, na zpomalení "přímějších" paprsků.

### Patch panel
- slouží k propojení kabelů do switchů, routerů, ... jako "zásuvka pro síť"

### Rack
- skříň, do které se montují servery, switche, routery, ...
- sbíhá se do nich kabeláž