# 2 - Základy OS
## Terminologie

- **Operační systém (OS)** - SW, který ovládá HW, spouští programy, rozvrhuje úkoly (přiděluje zdroje jednotlivým procesům) a zdroje a poskytuje uživateli rozhraní k počítači
- **Proces** - Výkon instrukcí po načtení z paměti
- **Kernel** - Jádro OS, slouží jako hlavní rozhraní mezi HW a procesy OS
- **GUI (Graphical User Interface)** - Grafické rozhraní
- **TUI (Text-based UI)** - Textové rozhraní
- **API** (Application Programming Interface)** - SW, který umožňuje komunikaci mezi dvěma aplikacemi
- **GNOME (GNU Network Object Model Environment)** - GUI + set PC aplikací pro uživatele Linuxu. 
- **KDE (K Desktop Environment)** - Open source GUI pro Unix a Linux a dokonce Windows a Mac. KDE je podobnější na Windows, je otevřenější a konfigurovatelnější než GNOME.
- **LTS (Long Term Support)** - Stabilní verze OS, která je podporována po delší dobu.
- **Update** - Aktualizace SW, která opravuje chyby, zlepšuje výkon a přidává nové funkce. (např. běžný Windows Update)
- **Upgrade** - Přechod na novější verzi OS. (např. Windows 10 na Windows 11)
- **Daemon** - Daemon je označení pro službu nebo proces, který běží na pozadí operačního systému nebo ve službě a provádí určité funkce, bez interakce s uživatelem.
## Základní funkce OS

- **výkon instrukcí** -> správa procesů, přiděluje a odebírá procesům systémové prostředky počítače
- **správa paměti** -> správa paměti, kterou procesy používají k ukládání a načítání dat
- **řízení CPU**
- **souborový systém**
- **abstrakce hardware:** vytváří rozhraní pro programy, které abstrahuje ovládání hardware a dalších funkcí do snadno použitelných funkcí (API)

potažmo potom...
- **ovládání počítače:** umožňuje uživateli spouštět programy, předávat jim vstupy a získávat jejich výstupy s výsledky

## Proces

- **běžící instance kódu - program**
- v Linuxu objekt, který pracuje podle kódu programu (včetně knihoven), využívá svůj vlastní adresní paměťový prostor. Využívá služby jádra a komunikuje různými způsoby s ostatními procesy


- Má 5 základních stavů:
    - **Nový (New)** - proces byl právě vytvořen
    - **Probíhající (Running)** - instrukce procesu začala být vykonávána
    - **Čekající** **(Waiting)** - proces čeká na nějakou událost (např. na dokončení I/O operace nebo přijetí signálu)
    - **Připraven (Ready)** - proces čeká na procesor
    - **Ukončen (Terminated)** - proces dokončil svou činnost

  ![Process life cycle](https://zcu.arcao.com/kiv/zos/zos/OdSobi/Materialy/Buris/dalsi-materialy/operacni_systemy-02/cpu/cpu11.gif)


- Nejdůležitější informace uložené v tzv. **Process Control Block (PCB)**:
    1. **ID procesu (PID):** Identifikátor procesu (OS přes něj spravuje procesy)
    2. **Stav procesu**
    3. **Registry:** Momentální obsah registrů procesoru, pro umožnění přerušení a návratu k běhu procesu.
    4. **Zásobníky:** Informace o stavu zásobníku procesu, který uchovává lokální proměnné a stavy volání funkcí.
    5. **Priorita**
    6. **Rozvrhovací informace:** Čas, který proces již strávil během svého běhu, a informace pro plánovač procesů.
    7. **Paměťová mapování:** Informace o přidělených paměťových blocích procesu a jeho paměťovém kontextu.
    8. **Odkazy na otevřené soubory:** Informace o souborech, se kterými proces pracuje, a otevřených kanálech pro komunikaci se systémem nebo jinými procesy.
    9. **Informace o vstupu/výstupu:** Stav a informace o aktuálním I/O procesu (např., I/O fronty, stav čekání na vstup nebo výstup).

## Historie vývoje

1. **40-50. léta:** Původní PC bez OS (nikdo o něm nepřemýšlel) - fungovaly doslova jako “velká kalkulačka”. Pro vstup se používaly děrné štítky s binárním zápisem dírek. Programování těchto strojů tak bylo obtížné a časově náročné.
2. **50-60. léta:** Představení jazyků _Fortran_ a _Basic_ => efektivnější programování, přichází tzv. [_dávkový_](#druhy-operačních-systémů) OS. 
3. **60-70. léta:** OS s [multitaskingem](#druhy-operačních-systémů), větší podpora programátorů, lepší zpráva zdrojů.
4. **80-90. léta:** Osobní PC s [GUI](#terminologie) (Windows, Macintosh)
5. **Současnost (>2000):** Vývoj zaměřen na mobilitu, cloudové technologie, bezpečnost a efektivní využití výpočetního výkonu.

### Druhy operačních systémů:

- **Dávkové (Batch) operační systémy:** Spouštěly programy v dávkách bez interakce s uživatelem.
- **Interaktivní operační systémy:** Interake pomocí terminálů nebo textového rozhraní.
- **Síťové operační systémy:** Navrženy pro efektivní správu počítačových sítí a zpracování dat na vzdálených strojích.
- **Multitaskingové operační systémy:** Schopné provádět více úloh současně.
- **Mobilní operační systémy:** Navrženy pro chytré telefony a tablety, jako je iOS pro Apple a Android pro zařízení různých výrobců.

## Jádro
- Základ OS, spravuje hardware počítače a poskytuje služby ostatním programům

### Monolitické jádro
- Klasické **velké a komplexní jádro**, ve kterém jsou implementovány **všechny funkce OS** (ovladače, filesystémy...)
- 2 typy procesů:
  - **Bežné** - Běží v uživatelském prostoru, s omezeným přístupem k jádru, spustitelné uživateli
  - **Systémové** - Běží v jádru, neomezený přístup k HW a paměti PC, spouštěné jádrem
- K těmto funkcím se pak běžné procesy dotazují přes **systémová volání**
- Výhodami jsou **výkon** a **stabilita**

![monolitic_core.png](monolitic_core.png)


### Mikrojádro
- spravuje pouze přerušení, plánování a komunikaci mezi procesy
- velmi **malé, jednoduché jádro** OS s pouze **nejzákladnějšími funkcemi** pro menší objem bežícího kódu
- **Ostatní funkce** poskytuje jako samostatné servery, které běží **v uživatelském prostoru**
- **Bezpečné, škálovatelné, lehčí na údržbu**
![microcore.png](microcore.png)

## Správa a konfigurace
### Desktop OS:

- **Správce úloh/souborů/zařízení:**
  - Poskytuje možnost sledovat běžící procesy, spravovat soubory a ovladače zařízení.
- **Ovládací panely:**
  - Zde lze nalézt široké spektrum funkcí pro správu systému, zařízení, síťových nastavení a zabezpečení.
- **Nastavení:**
  - Modernější, uživatelsky přívětivější rozhraní umožňující základní nastavení včetně personalizace, účtů, aplikací a sítě.
- **Správce disků:**
  - Pro správu pevných disků, oddílů, formátování a změnu velikosti.
- **Správce tiskárny:**
  - Slouží k údržbě tiskáren, nastavení tiskových úloh a ověření stavu tiskáren.

### Server OS:

> Role serveru - skupina služeb, které poskytuje server

- **Správce serveru (Server manager):**
  - Poskytuje rozsáhlé možnosti pro správu serveru, včetně správy rolí, funkcí a konfigurace serveru.
- **Správce bezpečnosti:**
  - Slouží k nastavení a správě bezpečnostních politik, firewallu, šifrování a dalších aspektů zabezpečení serveru.
- **Správce úložišť:**
  - Umožňuje správu dat, zálohování, řízení disků a úložišťových zařízení.
- **Nástroje pro správu výkonu:**
  - Poskytují informace o využití výkonu serveru, sledování výkonu a optimalizaci serverových prostředků.

- Pro OS Windows např:
  - **Ovládací panely:** Rozsáhlý nástroj poskytující širokou škálu funkcí pro správu systému, zařízení, síťových nastavení a zabezpečení.
  - **Nastavení:** Modernější prostředí umožňující základní nastavení včetně personalizace, účtů, aplikací a sítě.
  - **Správce zařízení:** Podrobný nástroj pro správu hardware, ovladačů a zařízení v systému.
  - **Správce úloh:** Ukazuje běžící procesy a využití systémových prostředků, umožňuje ukončit procesy nebo sledovat výkon.
  - **Regedit (Editor registru):** Pokročilý nástroj pro úpravu a správu systémového registru Windows.
  - **Služby:** Nástroj pro správu spouštění, zastavení nebo změnu konfigurace služeb.
  - **Správce disků:** Pro správu pevných disků, oddílů, formátování a změnu velikosti.
  - **Správce tiskárny:** Umožňuje správu tiskáren, nastavení tiskových úloh a ověření stavu tiskáren.
  - _Další nástroje jako Správce serveru, bezpečnosti, úložiště jsou specifické pro servery a poskytují pokročilé možnosti pro správu serverových OS._

  

---

# Souborové systémy: NTFS, exFAT, FAT32, APFS

Souborové systémy jsou struktury, které operační systém používá k organizaci a správě souborů na pevném disku nebo jiném úložném zařízení. Zde jsou podrobné informace o čtyřech populárních souborových systémech: NTFS, exFAT, FAT32 a APFS.

## 1. NTFS (New Technology File System)

**Vývojář:** Microsoft  
**Použití:** Primárně ve Windows  
**Rok uvedení:** 1993 (Windows NT 3.1)

### Klíčové vlastnosti:
- **Podpora velkých souborů a disků:** NTFS podporuje velmi velké soubory a diskové oddíly (až do velikosti 16 EB v teorii, prakticky limitováno na 256 TB).
- **Bezpečnost:** Podpora šifrování, oprávnění a kvót. NTFS umožňuje nastavovat přístupová práva na soubory a složky.
- **Žurnálování:** Zajišťuje vyšší spolehlivost a integritu dat. Žurnálování umožňuje obnovení systému po chybě nebo výpadku proudu.
- **Komprese:** Možnost komprese souborů a složek, což šetří místo na disku.
- **Podpora dlouhých názvů:** NTFS podporuje dlouhé názvy souborů a Unicode znaky.

### Použití:
- Ideální pro moderní pevné disky a SSD, kde je důležitá bezpečnost a spolehlivost.
- Primárně používán ve všech verzích Windows od Windows XP po Windows 11.

## 2. exFAT (Extended File Allocation Table)

**Vývojář:** Microsoft  
**Použití:** Přenosná zařízení, jako jsou USB flash disky a paměťové karty  
**Rok uvedení:** 2006

### Klíčové vlastnosti:
- **Podpora velkých souborů a disků:** exFAT podporuje soubory větší než 4 GB, což je limit FAT32. Maximální velikost souboru je 16 EB.
- **Kompatibilita:** Podporován mnoha operačními systémy, včetně Windows, macOS a některých verzí Linuxu.
- **Efektivita:** Méně režijního zatížení než NTFS, což znamená lepší výkon na přenosných zařízeních.

### Použití:
- Vhodný pro flash disky, externí pevné disky a paměťové karty, které potřebují kompatibilitu mezi různými operačními systémy.
- Doporučený pro zařízení, kde jsou potřeba velké soubory, jako jsou 4K videa.

## 3. FAT32 (File Allocation Table 32)

**Vývojář:** Microsoft  
**Použití:** Přenosná zařízení a starší počítačové systémy  
**Rok uvedení:** 1996

### Klíčové vlastnosti:
- **Podpora souborů a disků:** Podpora souborů až do velikosti 4 GB a diskových oddílů až do 8 TB.
- **Kompatibilita:** Vysoká kompatibilita s většinou operačních systémů, včetně Windows, macOS, Linux a většiny herních konzolí a přenosných zařízení.

### Použití:
- Vhodný pro malé a přenosné úložné zařízení, kde je požadována vysoká kompatibilita.
- Ideální pro zařízení, kde jsou soubory menší než 4 GB, jako jsou starší hry a aplikace.

## 4. APFS (Apple File System)

**Vývojář:** Apple  
**Použití:** Zařízení Apple, včetně macOS, iOS, watchOS a tvOS  
**Rok uvedení:** 2017

### Klíčové vlastnosti:
- **Optimalizace pro flash a SSD:** APFS je navržen pro optimalizaci výkonu na moderních SSD discích.
- **Šifrování:** Silné šifrování pro vyšší bezpečnost dat, podporuje šifrování na úrovni souboru a disku.
- **Snapshoty:** Podpora snapshotů, což umožňuje rychlé zálohování a obnovení systému.
- **Rychlost:** Vysoký výkon při práci se soubory a složkami díky efektivnímu způsobu správy volného prostoru.
- **Efektivita:** Zlepšená správa volného místa a metadata, což zvyšuje celkový výkon systému.

### Použití:
- Standardní souborový systém pro všechna novější zařízení Apple, včetně MacBooků, iPhonů, iPadů, Apple Watch a Apple TV.
- Doporučený pro všechny uživatele Apple zařízení, kteří chtějí maximální výkon a bezpečnost.

## Shrnutí

- **NTFS** je ideální pro Windows systémy, kde je důležitá bezpečnost a podpora velkých souborů.
- **exFAT** je vhodný pro přenosná úložná zařízení, kde je potřeba podpora velkých souborů a vysoká kompatibilita.
- **FAT32** je starší, ale stále populární pro malé úložné zařízení díky své široké kompatibilitě.
- **APFS** je moderní souborový systém optimalizovaný pro Apple zařízení, poskytující vysoký výkon a bezpečnost.

Každý z těchto souborových systémů má své specifické výhody a nevýhody, a výběr závisí na konkrétních potřebách uživatele a zařízení, na kterém bude používán.
