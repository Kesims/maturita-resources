pojmy:

- role serveru: Označení pro skupinu funkcí, které běží na serveru. Např. DNS + DHCP role je na jednom serveru, kde běží DHCPv4 a v6 služba, k tomu DNS služba. Tzn role: proxy, dhcp, dns, Active directory, VPN, print server
- hyperv - virtualizace (vs kontejnerizace). Typy virtualizací (hypervizor 1. úrovně vs 2. úrovně (OS vrstva navíc)). KVM, WMware, Hyper-V, VirtualBox
- server manager - nástroj pro správu serveru ve WinServeru, kde lze spravovat role a funkce serveru, zařídí dotažení a instalaci potřebných balíčků
- active directory - role pro správu uživatelů, skupin, počítačů, politik, certifikátů, atd. Využívá se pro centralizovanou správu větších sítí. AD zařizuje zřízení domény, nad kterou se potom spravují služby v této doméně.
- group policy - definuje oprávnění, která se nastavují pro "subjekty" AD - možnost přiřazovat uživatele do skupin, dědit mezi nimi oprávnění apod.
- DNS - ez
- DHCP - pz



uveďte hlavní důvody, proč do serveru nasadit serverové řešení

popište funkcionality rolí (active directory certificate services, active directory domain service,
dhcp server, dns server, file and storage server, hyperv, windows server update services)


popište důvody nasazení domain controlleru - RSA vytváříme nad doménou... potřebujeme něco, co ji bude spravovat

popište DHCPv4, DHCPv6 (+ SLAAC), způsob počáteční komunikace mezi klientem a serverem

popište DNS a strukturu domén