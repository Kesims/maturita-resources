# SQL
SQL je skratka pro **Structured Query Language**</br>
Je to **standardizovaný** jazyk určený pro práci s **relačními databázemi**
Jeho hlavním účelem je manipulace s daty uloženými v **tabulkách** jako třeba **aktualizace, vkládání a odstraňování dat**.<br> 

### Základními operacemi v SQL jsou:<br>
**SELECT**: Výběr dat z databáze.<br>
**INSERT**: Vkládání nových dat do tabulky.<br>
**UPDATE**: Aktualizuje existující záznamy v tabulce.<br>
**DELETE**: Odstraňuje záznamy z tabulky.<br>
**CREATE**: Vytváří nové tabulky, indexy nebo další objekty v databázi.<br>
**ALTER**: Mění strukturu existujících databázových objektů, jako jsou tabulky nebo sloupce.<br>
**DROP**: Odstraňuje existující databázové objekty, jako jsou tabulky, indexy nebo pohledy.<br>

**SQL** je široce používaný v oblasti správy dat, **vývoje softwaru** a **analýzy dat**.
Existuje mnoho implementací **SQL**, které se liší v syntaxi a rozšířeních, jako jsou **Microsoft SQL Server**, **MySQL**, **PostgreSQL**, **Oracle Database** a **SQLite**.

Samotný **SQL je deklarativní jazyk**, což znamená, že se **nezabývá tím, jak by měly být operace provedeny, ale spíše specifikuje, co by mělo být provedeno.** <br>
### Mezi další klíčové vlastnosti a koncepty SQL patří:

**1. Databázové transakce**: Transakce jsou soubory SQL příkazů, které se provádějí jako celek. Jsou buď **provedeny úplně (commit), nebo vůbec (rollback)**, což zajišťuje konzistenci dat.<br>

**2. Vytváření a správa tabulek**: SQL umožňuje **vytváření nových tabulek pro ukládání dat a definování struktury** tabulek pomocí sloupců a datových typů.<br>

**3. Filtrování a řazení dat**: SQL umožňuje filtrování a řazení dat pomocí klauzulí **WHERE** a **ORDER BY** ve spojení s příkazem **SELECT**.<br>

**4. Skupinování a agregace dat**: SQL umožňuje seskupování dat podle určitých kritérií a provádění agregace funkcí jako je **SUM, AVG, MIN, MAX a COUNT**.<br>

**5. Pohledy (Views)**: **Pohledy jsou virtuální tabulky**, které se skládají z dat z jiných tabulek a jsou definovány pomocí SQL dotazů. **Poskytují možnost abstrakce nad daty a zjednodušují jejich manipulaci**.<br>

**6. Indexy**: Indexy jsou datové struktury, které urychlují vyhledávání a přístup k datům v databázi tím, že udržují seřazenou kopii určitých sloupců.<br>

**7. Transakční izolace a zámky**: SQL umožňuje definování úrovně izolace transakcí a používání zámků k **zabránění paralelnímu přístupu k datům a zajištění konzistence**.<br>

**8. Triggery**: **Triggery jsou speciální typy uložených procedur**, které se **automaticky spouštějí v reakci na určité události v databázi**, jako je vložení, aktualizace nebo odstranění dat.