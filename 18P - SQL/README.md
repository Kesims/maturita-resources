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

<br><br> <br>

# Ukradnuto od paní Borkovcové

## SQL - Structered Query Language (předchůdce SEQUEL)

- typ jazyka SQL - strukturovaný jazyk určený pro práci s objekty a daty v relačních databázích, jazyk 4GL, představuje standardizovaný (ISO) databázový jazyk relačních databází jako například MySQL, MSSQL, Oracle, PostgreSQL, SQL Lite, Access,...

## Kategorie SQL jazyka (DDL, DML, DCL, TCL...)

- **DDL - data definition language - pro definici dat (CREATE, ALTER, DROP)**

        - CREATE - slouží k vytváření nových databázových objektů   

        - ALTER - slouží k modifikaci databázových objektů

        - DROP - slouží k odstranění databázových objektů

- **DML - data manipulation language - pro manipulace s daty (INSERT, UPDATE, DELETE, .. SELECT)**

        - INSERT - slouží k vkládání dat

        - UPDATE - slouží k modifikaci dat

        - DELETE - slouží k odstranění dat

        - SELECT - slouží k výběru dat, může být rozšířen restrikcí (podmínka WHERE)

- **DCL - data control language - pro řízení dat (GRANT, REVOKE, ALTER USER, DROP USER)**

        - GRANT - slouží k udělení oprávnění uživateli či skupině rolí nebo samostatné roli

        - REVOKE - slouží k odebrání oprávnění uživateli či skupině rolí nebo samostatné roli

        -  ALTER USER - slouží k modifikaci uživatele, například změna hesla ALTER USER <nazev_uzivatele> IDENTIFIED BY <heslo>

        - DROP USER - slouží k odstranění uživatele

        - TCL (TCC) - transaction control language - pro řízení transakcí (COMMIT, ROLLBACK, SAVEPOINT, SET TRANSACTION)

        - COMMIT - používá se pro potvrzení transakce

        - ROLLBACK - používá se k tzv. odrolování transakce, transakce může být odrolovaná celá nebo případně lze použít ROLLBACK ve spojení se SAVEPOINT

        - SAVEPOINT - návratový bod, který je pojmenovaný buď systémem anebo může být vlastní

        - SET TRANSACTION - identifikuje počátek transakce, může mít i vlastní označení

## PŘÍKAZY DDL

### Vytvoření tabulky

```sql
CREATE TABLE <nazev_tabulky>

(
<nazev_sloupce1> <datovy_typ> NOT NULL, /tento sloupec musí vždy obsahovat nějaká data/

<nazev_sloupce2> <datovy_typ> PRIMARY KEY, /tento sloupec je primárním klíčem tabulky/

<nazev_sloupce3> <datovy_typ> UNIQUE, /tento sloupec může obsahovat jen jedinečné hodnoty, žádná hodnota v sloupci se nesmí opakovat/

<nazev_sloupce4> <datovy_typ>,

<nazev_sloupce5> <datovy_typ> DEFAULT SYSDATE,

CONSTRAINT nazev_fk FOREIGN KEY (nazev_sloupce4) REFERENCES nazev_tabulky2, (identifikator_pk) /tento sloupec je cizím klíčem tabulky2/

CONSTRAINT kontrola_vstupnich_hodnot CHECK (nazev_sloupce2 > 20)

);
```

### Modifikace tabulky

```sql
ALTER TABLE <nazev_tabulky> ADD <nazev_sloupce> <datovy_typ> <omezeni>;

ALTER TABLE <nazev_tabulky> RENAME COLUMN<nazev_sloupce>;

ALTER TABLE <nazev_tabulky> MODIFY <nazev_sloupce> <datovy_typ> <omezeni>; /problém při již existujích hodnotách - datový typ/
```

### Odstranění tabulky
```sql
DROP TABLE <nazev_tabulky>; /s odstraněním tabulky se odstraní i řádky/
```

## PŘÍKAZY DML

### Vkládání záznamů

/tabulka má jen 3 sloupce, jedná se tedy o plný výčet sloupců, sloupec1-NUMBER (pk), sloupec2-CHAR(5) NOT NULL,sloupec3-VARCHAR2(50) /

```sql
INSERT INTO <nazev_tabulky> (sloupec1, sloupec2, sloupec 3) VALUES (1,'45678','Dnes je ale krásný a slunečný den');

alternativně lze i takto:

INSERT INTO <nazev_tabulky> VALUES (1,'45678','Dnes je ale krásný a slunečný den');

INSERT INTO <nazev_tabulky> VALUES (1,'45678'); /tento příkaz nebude funkční, proč?/

správně:

INSERT INTO <nazev_tabulky> (sloupec1, sloupec2) VALUES (1,'45678');
```

### Modifikace záznamů

```sql
UPDATE <nazev_tabulky> SET <nazev_sloupce>=<hodnota> WHERE <podminka pro vyber dat k modifikaci>;
```

#### Modifikace čísla
```sql

UPDATE tabulka SET sloupec1=sloupec1+25 WHERE id>20;

UPDATE tabulka SET sloupec1=sloupec1+5;

UPDATE tabulka SET sloupec1=sloupec1+25 WHERE id<20;

UPDATE tabulka SET sloupec1=sloupec1+25 WHERE id=20;
```

### Odstranění záznamů

```sql

DELETE FROM <nazev_tabulky> WHERE <podminka pro vyber dat k odstraneni>;

DELETE FROM tabulka WHERE id=100;
```

### Vyprázdnění tabulky

```sql
TRUNCATE - oproti delete se chová tak, jako kdybychom do tabulky nevložili žádné záznamy
```

### Výběr dat

```sql
SELECT <nazev_sloupce>, <nazev_sloupce> FROM <nazev_tabulky>;

SELECT sloupec1, sloupec2 FROM tabulka;

SELECT DISTINCT sloupec1, sloupec2 FROM tabulka; - vrací pouze jedinečné řádky

SELECT UNIQUE sloupec1, sloupec2 FROM tabulka; - vrací pouze jedinečné řádky, není funkční ve všech rel.db

SELECT ALL sloupec1, sloupec2 FROM tabulka; - ALL je výchozí, nepíše se, vrací všechny řádky bez ohledu na duplicity

SELECT * FROM tabulka; /využití zástupného symbolu * znamená výběr všech sloupců z tabulky/

SELECT <nazev_sloupce>, <nazev_sloupce> FROM <nazev_tabulky> WHERE <podminka>;

SELECT sloupec1, sloupec2 FROM tabulka WHERE sloupec1=20;

SELECT <nazev_sloupce>, <nazev_sloupce> FROM <nazev_tabulky> WHERE <podminka> GROUP BY <nazev_sloupcu_pro_seskupeni>;

SELECT sloupec1, sloupec2 FROM tabulka WHERE sloupec1=20 GROUP BY sloupec2;

SELECT <nazev_sloupce>, <nazev_sloupce> FROM <nazev_tabulky> WHERE <podminka> GROUP BY <nazev_sloupcu_pro_seskupeni> HAVING <podminka_pro_filtraci_ve_skupine>;

SELECT sloupec1, sloupec2 FROM tabulka WHERE sloupec1=20 GROUP BY sloupec2 HAVING sloupec2 like 'abc';
```

# Spojování tabulek
![sql joins](/Obrazky/joins.png)
![union](/Obrazky/union.png)


## INNER JOIN - vnitřní spojení

- Za vnitřní spojení (INNER JOIN) jsou považována ta spojení, v nichž jsou záznamy ze dvou tabulek kombinovány a přidávány k výsledkům dotazu pouze tehdy, když k záznamům z první tabulky existují odpovídající záznamy v tabulce druhé, tedy když je naplněna uvedená podmínka spojení. 

```sql
SELECT a.* FROM a JOIN b ON A.id=B.a_id; /A.id je PK v tabulce A, a_id je FK v tabulce B, "rodič-potomek"/

(ON je tzv. vyhledávací podmínka použitá v kombinaci s JOIN)

alternativně lze dotaz dle standardu přepsat následovně: SELECT * FROM a, b WHERE A.id=B.a_id; 

WHERE, GROUP BY, HAVING
```

## NATURAL JOIN - přirozené spojení (vyplývá z relační algebry)

SELECT a.* FROM a NATURAL JOIN b; (databázový engine se sám rozhodne podle čeho se tabulky budou spojovat)

## CROSS JOIN 
- kartézský součin (vyplývá z relační algebry), každý záznam z jedné tabulky je spojen s každým záznamem z druhé tabulky

```sql
SELECT * FROM a CROSS JOIN b; + WHERE
```

## INTERSECT

- unikátní řádky oproti INNER JOIN (vnitřní spojení může vracet duplicity), je možné doplnění NULL oproti INNER JOIN, 

```sql
SELECT sloupec1 FROM tabulka A INTERSECT SELECT sloupec1 FROM tabulka B;
```

## EXCEPT (MINUS)

- zobrazí řádky z tabulky A očištěné od řádků, které má tabulka A a tabulka B společné

```sql
SELECT sloupec1 FROM tabulka A EXCEPT SELECT sloupec1 FROM tabulka B;
```

## OUTER JOIN (LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN)

### levé vnější spojení:

a) všechny řádky, které odpovídají vyhledávací podmínky a je zde shoda (inner join)

b) všechny řádky z levé tabulky, kde není nalezena shoda a doplní do výsledného datového setu u sloupců druhé tabulky null.

```sql
SELECT * FROM tabulkaA LEFT JOIN tabulkaB ON tabulkaA.id=tabulkaB.a_id;
```

### pravé vnější spojení:


a) všechny řádky, které odpovídají vyhledávací podmínky a je zde shoda (inner join)

b) všechny řádky z pravé tabulky, kde není nalezena shoda a doplní do výsledného datového setu u sloupců druhé tabulky null.

```sql
SELECT * FROM tabulkaA RIGHT JOIN tabulkaB ON tabulkaA.id=tabulkaB.a_id;
```

### plné vnější spojení:
a) všechny řádky, které odpovídají vyhledávací podmínky a je zde shoda (inner join)

b) všechny řádky z levé tabulky, kde není nalezena shoda a doplní do výsledného datového setu u sloupců druhé tabulky null.

c) všechny řádky z pravé tabulky, kde není nalezena shoda a doplní do výsledného datového setu u sloupců druhé tabulky null.

```sql
SELECT * FROM tabulkaA FULL JOIN tabulkaB ON tabulkaA.id=tabulkaB.a_id;

SELECT * FROM tabulkaA FULL OUTER JOIN tabulkaB ON tabulkaA.id=tabulkaB.a_id;
```

Alternativa k FULL OUTER JOIN, například v MySQL, kde není funkční příkaz FULL OUTER JOIN

**(odstranění duplicit)**

```sql
SELECT * FROM tabulkaA 

LEFT JOIN tabulkaB

ON tabulkaA.id=tabulkaB.a_id

UNION

SELECT * FROM tabulkaA 

RIGHT JOIN tabulkaB

ON tabulkaA.id=tabulkaB.a_id;
```



**(bez odstranění duplicit)**

```sql
SELECT * FROM tabulkaA 

LEFT JOIN tabulkaB

ON tabulkaA.id=tabulkaB.a_id

UNION ALL

SELECT * FROM tabulkaA 

RIGHT JOIN tabulkaB

ON tabulkaA.id=tabulkaB.a_id;
```

## USING

- použití pouze v ORACLE místo vyhledávací podmínky ON při dodržení základního pravidla, že názvy sloupců z obou tabulek mají shodný název nebo-li identifikátor, například při využití INNER JOIN by dotaz vypadal následovně:

```sql
SELECT a.* FROM a JOIN b USING (id);
```

# LOGICKÉ OPERÁTORY - AND OR NOT

## AND

```
P1 P2 R

1 1 1
1 0 0
0 1 0
0 0 0
1 null null
0 null null
null 1 null
null 0 0
null null null
```

Příklad: 
```sql
SELECT sloupec1, sloupec2, sloupec3 FROM tabulkaA WHERE sloupec2>3 AND sloupec3='maturita';
```

## OR

P1 P2 R

```
1 1 1
1 0 1
0 1 1
0 0 0
1 null 1
0 null null
null 1 1
null 0 null
null null null
```

Příklad: 
```sql
SELECT sloupec1, sloupec2, sloupec3 FROM tabulkaA WHERE sloupec2>3 OR sloupec3='maturita';
```

# ALIASY 

- aliasy nad sloupec anebo na tabulku anebo nad vnořeným dotazem:

    - v případě delších názvů tabulek nebo sloupců => přehlednost
    - v případě nutnosti v daném SQL příkazu (viz dále)
- kdy musím:
    - UNION - sloupce
    - při použití aliasu, tak např. v GROUP BY je nutné použít alias
    - self-join: SELECT * from tabulka tabA join tabulka tabB on tabA.id=tabB.id;

# Souhrnné a skupinové dotazy

- agregační funkce: **MAX, MIN, COUNT, SUM, AVG, MEDIAN (číslo, řetězec, datum)**
```
MAX - najde maximální hodnotu ve sloupci tabulky -- číslo, datum, řetězec
MIN - najde minimální hodnotu ve sloupci tabulky -- číslo, datum, řetězec
COUNT - najde počet hodnot ve sloupci -- číslo, datum, řetězec
SUM - vypočítá sumu(součet) hodnot -- číslo
AVG - vypočítá průměrnou hodnotu -- číslo
MEDIAN - najde hodnotu v půlce intervalu (seřadí výsledky a pak najde prostřední hodnotu, která rozděluje řadu na dva intervaly) -- datum, číslo
```

- SELECT AVG(rating) FROM tabulka; --rating (integer, number, real)


- NULL
- COUNT(*) - výsledek je počet všech řádků
- COUNT(sloupec) - počet řádků, kde je výskyt hodnoty ve sloupci (nezahrnuje NULL)

*sloupec poznamka neobsahuje žádnou hodnotu, všechna pole jsou prázdná*

```sql
SELECT SUM(poznamka) from pokusna; -- null
SELECT AVG(poznamka) from pokusna; --null
SELECT MIN(poznamka) from pokusna; --null
SELECT MAX(poznamka) from pokusna; -null
SELECT COUNT(poznamka) from pokusna; -0
```

**Doporučení: používat funkci NVL(NVL2), DISTINCT (duplicity)**

GROUP BY - skupinové dotazy

- využití skupinových dotazů, je rozdělení výsledného datasetu na "skupiny", mezi kterými lze provádět mezisoučty (aplikovat agregační funkce)

```sql
SELECT cislo, datum, MAX(text1) from pokusna GROUP BY cislo, datum; -- OK
SELECT cislo, datum, MAX(text1) from pokusna GROUP BY poznamka; --chybně
SELECT cislo, datum, MAX(text1) from pokusna GROUP BY cislo; --chybně
SELECT cislo, datum, MAX(text1) from pokusna GROUP BY datum; --chybně
```

HAVING

- filtrování výsledků v rámci "skupiny", liší se od WHERE

```sql
SELECT cislo, datum, MAX(text1) from pokusna GROUP BY cislo, datum HAVING cislo>1000;
```

Generování výsledku dotazu probíhá v následujících krocích:

```
1. Vytvoří se spojení tabulek uvedených za klauzulí FROM (JOIN) dle definovaných podmínek spojení (pokud jsou tyto uvedeny)

2. Obsahuje-li příkaz klauzuli WHERE, aplikuje se vyhledávací podmínka na každý řádek a zachovají se jen ty, které vyhovují uvedené podmínce. Jinak řečeno, pokud uvedená podmínka (která může mít několik částí spojených pomocí AND či OR) je vyhodnocena jako TRUE, řádek je ponechán, pokud je vyhodnocena jako FALSE nebo NULL, je řádek vyloučen z dalšího zpracování.

3. Pokud dotaz obsahuje klauzuli GROUP BY, jsou řádky rozděleny do skupin tak, aby všechny řádky v dané skupině měly shodné hodnoty ve všech seskupujících sloupcích.

4. Nad řádky v jednotlivých skupinách jsou vyhodnoceny agregační funkce, výsledkem je jeden souhrnný řádek pro každou skupinu.

5. Obsahuje-li příkaz klauzuli HAVING, aplikuje se vyhledávací podmínka na souhrnné řádky a ve výsledku jsou ponechány pouze ty, kdy vyhledávací podmínka je vyhodnocena jako TRUE.

6. Obsahuje-li příkaz klauzuli ORDER BY, je výsledek dotazu náležitě seřazen.
```

Uvedený postup je třeba chápat jako ilustrativní a o konkrétním postupu provedení dotazu rozhoduje optimalizátor databázového systému. 

## Zabezpečení db serveru ->SQL injection(sql injekce) 
**SQL Injection**
- SQL injection je technika napadení databázové vrstvy programu vsunutím (odtud „injection“) kódu přes neošetřený vstup a vykonání vlastního pozměňujícího poškozujícího SQL příkazu (dotazu DELETE, UPDATE, ALTER atp.). 
- Toto nezamýšlené neošetřené chování vzniká při propojení aplikační vrstvy s databázovou vrstvou (téměř vždy se totiž jedná o dva různé programy) a zabraňuje se mu pomocí jednoduchého escapování potenciálně nebezpečných znaků (nejčastěji apostrofu). 