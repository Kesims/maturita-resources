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
    - **Nový (New)** - proces byl právě vytvořen
    - **Probíhající (Running)** - instrukce procesu začala být vykonávána
    - **Čekající** **(Waiting)** - proces čeká na nějakou událost (např. na dokončení I/O operace nebo přijetí signálu)
    - **Připraven (Ready)** - proces čeká na procesor
    - **Ukončen (Terminated)** - proces dokončil svou činnost

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

1. Původní PC bez OS (nikdo o něm nepřemýšlel) - fungovaly doslova jako “velká kalkulačka”. Pro vstup se používaly děrné štítky s binárním zápisem dírek.
2. **50-60. léta** - Představení jazyků _Fortran_ a _Basic_ => efektivnější programování, přichází myšlenka o OS pro ušetření práce.
3. **70. léta** - První OS, rozšíření mezi lidmi celkem trvá. Programy byly napsány na páskách a uživatel si musel sám napsat spouštěcí skript v jazyce Basic. Většina lidí však s Basic neumělo, tak se začaly dělat OS s předprogramovanými aplikacemi (Atari, Commodore).
4. **MS-DOS** - Představení v roce 1981, první masivně rozšířený OS na domácích PC.