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

# Hlavní důvody pro nasazení serverového řešení

Nasazení serverového řešení do podnikové infrastruktury přináší několik klíčových výhod:

1. **Centralizovaná správa:**
   - Centralizované řízení uživatelů, přístupů a zdrojů z jednoho místa.
   - Usnadňuje správu uživatelských účtů, skupin, zásad a síťových zdrojů.

2. **Zvýšená bezpečnost:**
   - Robustní bezpečnostní funkce, jako je řízení přístupu, šifrování dat a autentizace.
   - Možnost zavedení a správy bezpečnostních zásad a monitorování aktivit.

3. **Efektivní správa zdrojů:**
   - Optimalizace využití hardwarových a softwarových zdrojů.
   - Lepší výkon a spolehlivost díky správě zatížení a distribuci zdrojů.

4. **Snadná škálovatelnost:**
   - Možnost snadného přidání nových uživatelů, zařízení a aplikací bez výrazných změn v infrastruktuře.
   - Podpora pro růst firmy a změny v požadavcích.

5. **Zálohování a obnovení:**
   - Centrální zálohování dat a možnost rychlého obnovení v případě havárie nebo ztráty dat.
   - Minimalizace prostojů a rizika ztráty důležitých informací.

6. **Podpora pro virtualizaci:**
   - Efektivní využití hardwarových zdrojů díky virtualizačním technologiím.
   - Zjednodušená správa virtuálních strojů a aplikací.

7. **Automatizace a údržba:**
   - Automatizace běžných úkolů a údržby serverů, jako jsou aktualizace, zálohování a monitoring.
   - Snížení administrativní zátěže a chyb způsobených lidským faktorem.

# Funkcionality rolí serverů

## Active Directory Certificate Services (AD CS)
- **Správa certifikátů:** Vytváření, vydávání a správa digitálních certifikátů.
- **Zabezpečení komunikace:** Šifrování dat a zajištění bezpečné komunikace v síti.
- **Autentizace:** Poskytování certifikátů pro autentizaci uživatelů a zařízení.

## Active Directory Domain Services (AD DS)
- **Správa uživatelů a skupin:** Centralizovaná správa uživatelských účtů, skupin a zásad.
- **Autentizace:** Ověřování uživatelů a řízení přístupu k síťovým zdrojům.
- **Replikace dat:** Distribuce adresářových informací mezi více servery.

## DHCP Server
- **Dynamické přidělování IP adres:** Automatické přidělování IP adres zařízení v síti.
- **Správa adresních rozsahů:** Definování a správa rozsahů IP adres pro různé části sítě.
- **Rezervace a vyloučení:** Možnost rezervace IP adres pro specifická zařízení a vyloučení IP adres z přidělování.

## DNS Server
- **Překlad doménových jmen:** Překlad lidsky čitelných doménových jmen na IP adresy.
- **Správa zón:** Vytváření a správa zón pro organizaci doménových jmen.
- **Replikace a delegace:** Zajištění dostupnosti DNS dat prostřednictvím replikace a delegace zón.

## File and Storage Server
- **Správa souborů:** Centrální úložiště a správa souborů a složek.
- **Sdílení souborů:** Možnost sdílení souborů mezi uživateli a zařízeními v síti.
- **Zabezpečení dat:** Řízení přístupu k souborům a složkám pomocí oprávnění a šifrování.

## Hyper-V
- **Virtualizace:** Vytváření a správa virtuálních strojů.
- **Optimalizace zdrojů:** Efektivní využití hardwarových zdrojů prostřednictvím konsolidace serverů.
- **Zálohování a obnovení:** Zálohování a rychlé obnovení virtuálních strojů.

## Windows Server Update Services (WSUS)
- **Správa aktualizací:** Distribuce a správa aktualizací pro operační systémy a aplikace.
- **Automatizace:** Automatické schvalování a nasazování aktualizací podle definovaných zásad.
- **Monitoring:** Sledování stavu aktualizací a generování reportů.

Nasazení těchto serverových rolí umožňuje firmám zlepšit efektivitu, zabezpečení a správu své IT infrastruktury.


### Důvody nasazení domain controlleru

Nasazení domain controlleru v rámci sítě přináší několik klíčových výhod a je zásadní pro správu a zabezpečení domény. Zde jsou hlavní důvody pro nasazení domain controlleru:

## 1. Centralizovaná správa uživatelů a zdrojů
Domain controller umožňuje centrálně spravovat uživatelské účty, počítače, skupiny a další síťové zdroje. Administrátoři mohou snadno provádět změny, nastavovat politiky a monitorovat aktivity napříč celou doménou z jednoho místa.

## 2. Autentizace a autorizace
Domain controller je zodpovědný za ověřování uživatelských přihlašovacích údajů a zajišťuje, že pouze oprávnění uživatelé mají přístup k síťovým zdrojům. Tímto způsobem se zvyšuje bezpečnost celé sítě.

## 3. Active Directory Domain Services (AD DS)
Domain controller poskytuje služby AD DS, které ukládají informace o objektech v doméně (např. uživatelé, počítače, tiskárny). AD DS umožňuje organizovat, spravovat a vyhledávat tyto objekty efektivně a bezpečně.

## 4. Skupinové politiky (Group Policies)
Díky domain controlleru mohou administrátoři definovat a aplikovat skupinové politiky, které umožňují centrálně řídit nastavení a konfigurace pro uživatele a počítače v doméně. To zahrnuje bezpečnostní politiky, instalace softwaru, mapování síťových jednotek a další.

## 5. Replikace a redundance
Domain controllery mohou být nasazeny v redundantních konfiguracích, což zajišťuje vysokou dostupnost a spolehlivost. Replikace mezi více domain controllery zajišťuje, že změny v Active Directory jsou synchronizovány napříč celou doménou.

## 6. Rozšiřitelnost a škálovatelnost
S nasazením domain controlleru je možné snadno rozšířit a škálovat síť podle potřeby organizace. Nové uživatele a počítače lze snadno přidávat a spravovat bez nutnosti složitých konfigurací.

## 7. Integrace s dalšími službami a aplikacemi
Domain controller může integrovat a spolupracovat s mnoha dalšími službami a aplikacemi, které vyžadují autentizaci a autorizaci. To zahrnuje aplikace třetích stran, cloudové služby, VPN připojení a další.

## 8. Zabezpečení a auditování
Domain controller poskytuje nástroje pro auditování a sledování aktivit v síti, což zvyšuje bezpečnost a pomáhá identifikovat a reagovat na potenciální bezpečnostní hrozby.

Nasazení domain controlleru je tedy nezbytné pro efektivní správu, bezpečnost a provoz síťové infrastruktury založené na doméně.

# DHCPv4, DHCPv6 (+ SLAAC) a způsob počáteční komunikace mezi klientem a serverem

## DHCPv4

### Popis
DHCPv4 (Dynamic Host Configuration Protocol for IPv4) je síťový protokol používaný k automatickému přidělování IP adres a dalších síťových konfigurací (např. maska sítě, výchozí brána, DNS servery) klientským zařízením v síti.

### Způsob počáteční komunikace mezi klientem a serverem
1. **DHCPDISCOVER:** Klient (bez IP adresy) vysílá broadcast zprávu DHCPDISCOVER, aby našel dostupné DHCP servery v síti.
2. **DHCPOFFER:** DHCP servery odpovídají na broadcast zprávu DHCPOFFER, ve které nabízejí IP adresu a další síťové informace.
3. **DHCPREQUEST:** Klient vysílá broadcast zprávu DHCPREQUEST, ve které akceptuje jednu z nabízených IP adres (obvykle první přijatou).
4. **DHCPACK:** Vybraný DHCP server potvrzuje přidělení IP adresy klientovi zasláním zprávy DHCPACK. Tato zpráva obsahuje potvrzenou IP adresu a další síťové informace.

## DHCPv6

### Popis
DHCPv6 (Dynamic Host Configuration Protocol for IPv6) je protokol určený k přidělování IPv6 adres a dalších konfiguračních informací v IPv6 sítích. DHCPv6 pracuje podobně jako DHCPv4, ale je navržen pro podporu většího adresního prostoru a některých specifických funkcí IPv6.

### Způsob počáteční komunikace mezi klientem a serverem
1. **Solicit:** Klient (bez IPv6 adresy) vysílá multicast zprávu Solicit, aby našel dostupné DHCPv6 servery v síti.
2. **Advertise:** DHCPv6 servery odpovídají multicast zprávou Advertise, ve které nabízejí IPv6 adresu a další síťové informace.
3. **Request:** Klient vysílá multicast zprávu Request, ve které žádá o konkrétní IPv6 adresu a konfigurační informace od jednoho serveru.
4. **Reply:** Vybraný DHCPv6 server potvrzuje přidělení IPv6 adresy klientovi zasláním multicast zprávy Reply. Tato zpráva obsahuje potvrzenou IPv6 adresu a další síťové informace.

## SLAAC (Stateless Address Autoconfiguration)

### Popis
SLAAC je metoda automatické konfigurace IPv6 adres, která umožňuje zařízení samočinně konfigurovat svou IPv6 adresu bez potřeby komunikace s DHCPv6 serverem. Zařízení generuje svou IPv6 adresu na základě prefixu oznámeného směrovačem v síti.

### Způsob počáteční komunikace
1. **Router Solicitation (RS):** Klient (bez IPv6 adresy) vysílá multicast zprávu Router Solicitation, aby našel směrovače v síti.
2. **Router Advertisement (RA):** Směrovače odpovídají multicast zprávou Router Advertisement, která obsahuje informace o síťovém prefixu a dalších konfiguračních parametrech.
3. **IPv6 Adresa:** Klient vytvoří svou vlastní IPv6 adresu kombinací obdrženého síťového prefixu a svého interface identifier (typicky MAC adresa). 

SLAAC umožňuje rychlou a snadnou konfiguraci zařízení v IPv6 sítích bez potřeby centrálního serveru pro správu adres.

## Co je DNS?

DNS (Domain Name System) je systém, který překládá lidsky čitelné názvy domén (např. www.example.com) na IP adresy (např. 192.0.2.1), které počítače používají k identifikaci serverů na internetu. 

### Jak funguje DNS?

1. **Zadání domény:** Uživatel zadá doménu do webového prohlížeče (např. www.example.com).
2. **DNS Resolver:** Požadavek je odeslán na DNS resolver (obvykle spravovaný ISP), který zahájí proces překladu.
3. **Kořenové servery:** DNS resolver se nejprve obrátí na kořenový DNS server, který ho nasměruje na příslušný TLD (Top-Level Domain) server.
4. **TLD servery:** TLD server (např. pro .com) poskytne adresu autoritativního DNS serveru pro konkrétní doménu (např. example.com).
5. **Autoritativní DNS server:** Autoritativní server poskytne finální IP adresu pro zadanou doménu.
6. **Vrácení IP adresy:** DNS resolver vrátí IP adresu webovému prohlížeči, který se pak připojí k cílovému serveru pomocí této IP adresy.

### Struktura domén

DNS má hierarchickou strukturu, která se skládá z několika úrovní:

1. **Kořenová doména:**
   - Nejvyšší úroveň v DNS hierarchii.
   - Značena tečkou (.), která obvykle není viditelná.
   - Obsahuje záznamy TLD serverů.

2. **Top-Level Domains (TLDs):**
   - Druhá úroveň v hierarchii.
   - TLDs jsou rozděleny na dvě hlavní kategorie:
     - **Generické TLDs (gTLDs):** .com, .org, .net, .gov, .edu, atd.
     - **Kódy zemí TLDs (ccTLDs):** .us, .uk, .de, .jp, atd.

3. **Second-Level Domains (SLDs):**
   - Jsou umístěny pod TLDs.
   - Například v doméně www.example.com je "example" SLD.

4. **Subdomény:**
   - Jsou umístěny pod SLDs.
   - Například v doméně blog.example.com je "blog" subdoména.

5. **Hostnames:**
   - Jednotlivé názvy zařízení nebo služeb v rámci domény.
   - Například "www" v www.example.com.

![image](https://github.com/Kesims/maturita-resources/assets/97666898/ce7dda6b-3c4d-42a0-bd93-97e408995266)
![image](https://github.com/Kesims/maturita-resources/assets/97666898/1e9b3ae4-e4c6-4fe5-b236-46ae84f30b48)

### Příklad struktury domény

- **Kořenová doména:** .
- **TLD:** .com
- **SLD:** example
- **Subdoména:** www
