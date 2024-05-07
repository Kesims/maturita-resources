# 2 - Základy OS
## Terminologie

- **Operační systém (OS)** - SW, který počítači říká, jak se chovat. Ovládá HW, spouští programy, rozvrhuje úkoly a zdroje a poskytuje uživateli rozhraní k počítači
- **Proces** - Výkon instrukcí po načtení z paměti
- **Kernel** - Jádro OS, slouží jako hlavní rozhraní mezi HW a procesy OS
- **GUI (Graphical User Interface)** - Grafické rozhraní
- **TUI (Text-based UI)** - Textové rozhraní
- **API** (Application Programming Interface)** - SW, který umožňuje komunikaci mezi dvěma aplikacemi
- **GNOME (GNU Network Object Model Environment)** - GUI + set PC aplikací pro uživatele Linuxu
- **KDE (K Desktop Environment)** - Open source GUI pro Unix a Linux a dokonce Windows a Mac

## Základní funkce OS

- **ovládání počítače:** umožňuje uživateli spouštět programy, předávat jim vstupy a získávat jejich výstupy s výsledky
- **abstrakce hardware:** vytváří rozhraní pro programy, které abstrahuje ovládání hardware a dalších funkcí do snadno použitelných funkcí (API)
- **správa prostředků:** přiděluje a odebírá procesům systémové prostředky počítače

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
- velmi **malé, jednoduché jádro** OS s pouze **nejzákladnějšími funkcemi** pro menší objem bežícího kódu
- Typicky správu paměti a podporu pro plánování procesů a meziprocesové komunikace
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

- **Správce serveru:**
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


NTFS, exFAT, FAT32, APFS