# 12 - Instalace serverového OS a rolí serveru. Základní role - uživatelé a skupiny, servery DHCP a DNS a souborový server

## Pojmy:

- **Role serveru:** Označení pro skupinu funkcí, které běží na serveru
    - Např. DNS + DHCP role je na jednom serveru, kde běží DHCPv4 a v6 služba, k tomu DNS služba. Tzn role: proxy, dhcp, dns, Active directory, VPN, print server
- **Hyperv** - virtualizace (vs kontejnerizace). Typy virtualizací (hypervizor 1. úrovně vs 2. úrovně (OS vrstva navíc)). KVM, WMware, Hyper-V, VirtualBox
- **Server manager** - nástroj pro správu serveru ve WinServeru, kde lze spravovat role a funkce serveru, zařídí dotažení a instalaci potřebných balíčků
- **Active directory** - role pro správu uživatelů, skupin, počítačů, politik, certifikátů, atd. Využívá se pro centralizovanou správu větších sítí. AD zařizuje zřízení domény, nad kterou se potom spravují služby v této doméně.
- **Group policy** - definuje oprávnění, která se nastavují pro "subjekty" AD - možnost přiřazovat uživatele do skupin, dědit mezi nimi oprávnění apod.
- DNS - ez
- DHCP - pz

### Uveďte hlavní důvody, proč do serveru nasadit serverové řešení

### Popište funkcionality rolí (active directory certificate services, active directory domain service, dhcp server, dns server, file and storage server, hyperv, windows server update services)


### Popište důvody nasazení domain controlleru - RSA vytváříme nad doménou... potřebujeme něco, co ji bude spravovat

### Popište DHCPv4, DHCPv6 (+ SLAAC), způsob počáteční komunikace mezi klientem a serverem

### Popište DNS a strukturu domén