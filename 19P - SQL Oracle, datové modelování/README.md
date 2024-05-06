# SQL Server/Oracle

- SQL Server je databázový software Microsoft SQL Server od Microsoftu, Oracle Database je databázový software od Oracle Corporation. Oba jsou představitelé relačních databází, lze sem zařadit i MySQL, PostgreSQL, apod.
- relační databázový systém založený na relační algebře, databáze je centralizovaná a strukturovaná sada dat.
- Databázový server - server obsahující databázový software a další programové prostředky umožňující práci s daty a přístup klientů k těmto datům
- Databáze - v tomto případě relační, která obsahuje nástroje (zajištění integrity, ACID, apod.), strukturu dat a samotná data.
- Každá relační databáze je založena na tzv. Systému řízení báze dat (SŘBD nebo RDBMS).
- ACID = atomicity, consistency, isolation, durability. Jedná se o základní princip všech relačních databází vycházející z teorie množin a je součástí tzv. transakčního mechanismu. Atomicita je založena na principu 1 databázové transakce. Konzistence říká, že všechny integritní pravidla nad daty musí být dodrženy v rámci transakce. Izolace značí, že transakce je izolovaná, jinými slovy neviditelná pro ostatní transakce. Odolnost značí, že data budou uložena trvale po commitnutí transakce.

- ACID je zkratka z oboru informatiky, přesněji z oblasti databází. Jde o první písmena čtyř anglických slov vystihujících čtyři žádoucí vlastnosti databázových transakcí. 

```
atomicita (atomicity) 

konzistence (consistency) 

izolovanost (isolation) 

trvalost (durability) 
```

**Atomicita** 
- Atomicita znamená u databázových transakcí totéž, co atomicita v informatice obecně, totiž že se operace provede z hlediska uživatele buď celá, nebo vůbec – tedy výsledkem nebude žádný nedefinovaný mezistav.

**Konzistence** 
- Konzistencí se rozumí požadavek, že transakce nesmí narušit databázovou integritu. To nevylučuje ztrátu konzistence na vyšší, aplikační úrovni, požadavek se týká pouze zachování podmínek, které byly definovány na databázové úrovni.

**Izolace** 
- Požadavek izolace znamená, že se vícero současně probíhajících transakcí nesmí ovlivnit. „Jedna transakce nesmí ovlivnit druhou“.

**Trvalost**  
- Trvalost transakce znamená, že jakmile je již transakce dokončena, znamená to, že je zaznamenána trvalým způsobem, takže ji nevymaže například následný výpadek napájení.



# Modelování v relačních databázích

DATOVÉ MODELOVÁNÍ je prvním krokem procesu vývoje databáze. Zahrnuje sběr a analýzu dat, které podnik potřebuje sledovat a následně modelování diagramu ERD.

![alt text](/Obrazky/konceptulani.png)

## Konceptuální model:

Zahrnuje funkcionální a informační potřeby podniku.

1. Je založen na aktuálních potřebách, ale může reflektovat budoucí potřeby.
2. Adresuje potřeby organizace tedy to, co je konceptuálně ideální, ale není adresována implementace, co je fyzicky možné. 
3. Je označován jako entitně relační model označovaný jako ERM.
4. Je ilustrován s použitím entitně relačního diagramu, zkratka ERD.
5. Je výsledkem dokončení procesu datového modelování.
6. Podnik používá data například ke zvýšení prodejů nebo redukci ceny.
7. Na to, aby byla data vhodně analyzována, podnik musí vytvořit konceptuální model dat, která považuje za důležitá.

**Konceptuální model je důležitý protože:**

Popisuje přesně informační potřeby podniku, diskuse o dostupných řešeních, je prevencí omylů a nedorozumění, formuje důležitou dokumentaci „ideálního systému“, formuje podobu základního fyzického databázového designu.
### Entita
1. Entita: Představuje něco, co reprezentuje organizaci nebo systém. Je to pojmenování pro soubor podobných věcí, které lze vyjmenovat, obvykle podstatné jméno (například: objekty, události a osoby).
2. Instance: Jsou jednotlivé příklady entit. Některé entity mají mnoho instancí, zatímco jiné pouze několik.
3. Znalost organizování a klasifikace dat umožňuje lépe porozumět a analyzovat informace. Pomáhá lépe identifikovat skryté souvislosti a události na základě dostupných dat.
4. Například ve škole je potřeba ukládat data o různých entitách, jako jsou studenti, učitelé, lekce, místnosti a výsledky, aby bylo možné správně organizovat vzdělávací proces a vyhodnocovat výsledky.


### Atribut
1. Atribut specifikuje informaci o entitě.
2. Každý atribut má jednu hodnotu.
3. Hodnoty atributů jsou datové typy (číslo, znak, řetězec, zvuk, obrázek atd.).
4. Atributy mohou být neměnné (datum objednávky) nebo volitelné (telefonní číslo).
5. Neměnné atributy jsou stabilní a mění se zřídka.
6. Vybrání neměnných atributů je preferované.
7. Některé atributy jsou mandatorní (jméno zaměstnance), jiné volitelné.
8. Atributy poskytují rozšířené informace o entitách.
9. Pomáhají rozlišovat mezi instancemi entit.


### Identifikátor
Každý zaměstnanec má svůj unikátní identifikátor označovaný jako UID. UID je jeden atribut nebo kombinace vícero, pomocí kterých lze zaměstnance od sebe vzájemně odlišit. Jsou rozdílem mezi jednotlivými instancemi entit, např.: ve třídě je nutno rozlišit studenty v knihovně je nutné jednotlivá knihy rozlišovat.

### UID
Představuje hodnotu nebo kombinace hodnot, která umožňuje uživateli vyhledat jednu unikátní věc v celém obsahu.

**JEDNODUCHÝ UID** se skládá z jednoho atributu. Nicméně někdy není jeden atribut dostatečně unikátní na to, aby mohla být identifikovaná instance entity.

**SLOŽENÉ UID** je kombinace více atributů použitá jako UID.

**UMĚLÝ UID** je to, co se nenachází v přirozeném světě, ale je vytvořeno pro potřeby identifikace v rámci systému. Lidé nejsou narození s číslem a hodně systému přiřazuje právě lidem unikátní čísla pro následnou snadnou identifikaci => zavedení atributů ID.

*Jak lze jednoznačně identifikovat například studenta? Lze použít kombinaci jména a příjmení? Ano ale pouze v případě jistoty, že v systému opravdu není více Janů Nováku, což nelze i pro budoucí růst systému zaručit. Často je tak jednodušší zavést umělý atribut, pomocí kterého budeme danou osobu identifikovat i když bude Janu Nováků v systému 100, UID může být umělý a zároveň složený.*

**KANDIDÁTNÍ UID** - Někdy existují dva a více možných UID v rámci entity, například při objednávce z e-shopu, kde je uživatel registrován, má na svém účtu svoje user ID a zároveň email, který by se dal také použít. Každý z těchto atributů je potom kandidátem na UID, pouze jeden je pak vybrán jako UID a říká se mu primární UID. Ostatní kandidáti jsou označeni jako sekundární UID.Z vybraného primárního UID se následně stává primární klíč a ten je použit v databázi pro identifikaci záznamu.

**ERD** 
je nástroj, pomocí kterého lze reprezentovat požadavky na data, bez ohledu na jejich budoucí implementaci. Správně navržený konceptuální model zůstává stejný bez ohledu na typ databázového systému, jedná se o bezimplementační model. Prezentuje seznam všech entit, stejně tak jako relací mezi těmito entitami. Poskytuje informace jako je popis entit, datové typy a omezení. Tenhle model obvykle nepotřebuje ani diagram, ale diagram je typicky velmi užitečným nástrojem. Hlavními cíli ER modelování je zahrnout všechny informace a zajistit, aby se všechny informace vyskytovaly pouze jedenkrát. Dále nemodelovat informace, které je možné odvodit z již zaznamenaných informací, lokalizovat informace prediktivní, logicky uspořádané, např.: záznamy o studentech po celou dobu jejich studia, jako jsou známky, absence, zkoušky, apod. Vše je potřeba mít logicky uspořádané tak, aby bylo možné přistupovat a aktualizovat efektivně a snadno data = cíle datového modelování toto umožňují.

**Relace** <br>
Být schopný identifikovat vztahy mezi entitami, zajišťuje jednodušší porozumění spojení mezi rozdílnými částmi dat. RELACE neboli vztahy mezi entitami napomáhají zobrazit, jak rozdílné části systému dopadají na ostatní. Například entity student a kurz jsou spolu ve vztahu, pro přesné namodelování problému jsou vztahy stejně tak důležité, jako samotné entity. Vztah je způsob, jakým jsou 2 a více lidí nebo věcí vzájemně propojeny. Název vztahu nám říká, jak jsou členové spojeni.

## Relace v datovém modelu:

- Reprezentuje něco specifického a důležitého pro organizaci a ukazuje, jak jsou entity na sebe vzájemně napojeny.
- Existuje pouze mezi entitami (nebo entita se sama sebou), jsou obousměrné (bi-directional) a pojmenované na obou koncích.
- Mají volitelnost relace, mohou být také povinné nebo volitelné. VOLITELNOST RELACE znamená, že budoucí instance dané entity vstupuje povinně nebo nepovinně do vztahu s instancí druhé entity. Například máme dvě entity: zaměstnanec a práce - v závislosti na tom, co známe o instancích entit, můžeme podle toho určit volitelnost.
- Mají kardinalitu, musí mít každý zaměstnanec práci? Musí každá práce být přidělena nějakému zaměstnanci? KARDINALITA RELACE měří kvantitu (množství) něčeho, v relaci nám určuje stupeň, odpovědi na otázku "Kolik?" Například Kolik prací může mít zaměstnanec? Jenom jednu nebo více? Kolik zaměstnanců může vykonávat danou práci? Jeden nebo více? Například každé sedadlo může být prodáno pouze jednomu cestujícímu, každý cestující si může zakoupit jedno sedadlo, sedadlo je prodáno cestujícímu.

*Datové modelování používá terminologii také - je nazývaná ERDish - pro potřeby tohoto kurzu- jsou to slovíčka pro jasnou komunikaci obchodních podmínek (rolí), které jsou zahrnuty v ERD. Erdish je jazyk používaný pro stav relací mezi entitami v ERD.*

![alt text](/Obrazky/erdish.png)

Komponenty ERDish:
- každá
- entita A
- volitelnost (musí/může)
- název relace
- kardinalita (jeden a pouze jeden/ jeden nebo více) entita 

**ERDish je nutné číst z obou stran!**
Každý zaměstnanec musí pracovat v jednom a pouze v jednom oddělení. Každé oddělení může být odpovědné za jednoho nebo více zaměstnanců.

### Pravidla kreslení entit:

- Entity jsou zakreslovány jako obdélníky se zakulacenými rohy - SOFTBOXY.
- Názvy entit jsou v těchto „softboxech“.
- Název entity je vždy jednotný a psaný velkými písmeny.
- Atributy jsou v seznamu pod názvem entity.
- povinné atributy jsou označeny hvězdičkou *
- volitelné atributy jsou označené malým o (z angličtiny optional)
- unikátní identifikátory (UID) jsou označené hash symbolem - #

### Pravidla kreslení relací:
- Relace jsou linky, které spojují entity.
- Tyto linky jsou kreslené s plnou čarou nebo tečkovaně.
- Linky končí buď rovnou čarou (single toe) nebo tak zvanou slepičí nohou (crows foot).


### Supertypy a subtypy (podtypy)
SUPERTYP je taková entita, která je rodičovskou pro jiné entity a SUBTYP je taková entita, který je potomkem rodičovské tzv. supertyp entity. S obojím se lze hojně setkat v běžném životě, např. typ objednávky (s sebou, v restauraci), typ tašky, typ platby v obchodě, apod. Typicky se dají super a sub typy asociovat s výběrem platební metody. Pokud se jedná o nějaký výběr, potom je to vhodné k zavedení sub a super typu. Někdy dává větší smysl rozdělit entitu na dílčí podtypy. To může být případ, kdy skupina instancí má speciální nastavení, jako jsou atributy nebo relace, které existují právě v dané skupině. V tomto případě se entita nazývá supertyp a každá skupina potom subtyp. Příkladem může být supertyp Zvířata a subtyp obratlovci a bezobratlovci. 

*Pro přehlednost je vhodné tytu charakteristiku uvést následujícím výčtem:*

- přebírá všechny atributy supertypu,
- přebírá všechny relace supertypu,
- obvykle obsahuje vlastní atributy a relace,
- je zakreslován bez supertypu,
- nikdy neexistuje osamoceně,
- může mít další subtypy.

![alt text](/Obrazky/supertyp.png)

Z důvodu první podmínky je dobré zahrnovat vždycky podtyp „ostatní“ tak, aby opravdu došlo k pokrytí všech možných typů instancí. Každá entita může být rozdělena pomocí vytvoření pravidla, které rozdělí instance do skupin. Ale není hlavním úkolem dosáhnout rozdělení na podtypy - úkolem je toho docílit, pokud je zde důvod k těmto podtypům. Vždy když ukazuje úloha na podobnosti a rozdílnosti mezi instancemi, potom je důležité vytvářet subtypy. Důležité je i zmínit, že podtyp se může stát sám supertypem, jelikož subtypy lze vnořovat, jedná se o tzv. nested subtypes. V okamžiku, kdy dochází k modelování supertypů a subtypů, je důležité si odpovědět na následující 3 otázky: Je subtyp druhem supertypu? Jsou pokryty všechny možné případy? Opravdu každá instance odpovídá pouze jednomu subtypu? (výlučnost).

### Přenositelnost relací

Výchozí situace: Jeden předmět má přiděleného garanta, může být následně přesunut k jinému vyučujícímu, například v polovině semestru? Obvykle ano, protože co by se dělo, kdyby původní vyučující dlouhodobě onemocněl? Jinak je to u sportovních klubů, ty většinou nedovolují přepis členství na jinou osobu. Toto je příklad pravidel organizace.

Výchozí situace:

- Relace mezi entitami zaměstnanec / oddělení:
- Musí každý zaměstnanec být přiřazen do oddělení?
- Musí každé oddělení být odpovědné za zaměstnance? 
- Kolik zaměstnanců může být v jednom oddělení?
- Kolik oddělení může mít přiřazeno jednomu zaměstnanci?
- Může být zaměstnanec přesunut z jednoho oddělení do jiného? 

**PŘENOSITELNOST RELACÍ** značí, že relace je nepřenositelná v okamžiku, kdy daná instance je vázaná pouze na konkrétní instanci druhé entity. Stejně tak může být přesouván student mezi jednotlivými cvičeními, jakmile ale jde o předpis úhrady školného, certifikátů apod. již není možné tyto platby měnit na jiného studenta. Nepřesunutelná relace se označuje diamantem na relaci. 

![alt text](/Obrazky/prenositelnost.png)

# Typy relací:

### 1:M vztah

Tento vztah se nejčastěji vyskytuje v entitně relačním modelu. Existuje několik variant tohoto vztahu, které se vztahují na povinnost vstupovat do vztahu či nikoliv, pro lepší pochopení značí při přepisu 0 nepovinnost a 1 povinnost. VZTAH 1:Mznamená, že 1 instance entity může vstupovat do M vztahů s několika instancemi druhé entity.

![alt text](/Obrazky/1_m.png)

### Více k více vztah M:M

Stejně jako u předchozího typu vztahu, i u vztahu více k více existujte několik variant tohoto vztahu, které se vztahují na povinnost vstupovat do vztahu či nikoliv. Jelikož pro fyzickou implementaci tohoto typu vazby do databáze je nutné provést rozpad této vazby, je toto řešeno v následujících kapitolách. VZTAH M:Mznamená, že M instancí jedné entity může vstupovat do M vztahů s několika instancemi druhé entity.

![alt text](/Obrazky/m_m.png)

### Vztah 1:1

Použití vztahu 1:1 je výjimečné v ER modelu. Je tedy nutné mít na paměti, používat tento typ vazby velmi opatrně a velice zřídka. VZTAH 1:M znamená, že 1 instance entity může vstupovat pouze do vztahu pouze s 1 instancí druhé entity.

![alt text](/Obrazky/1_1.png)

### Redundatní relace 
Tyto relace mohou být odvozeny z existujících relací v modelu - jsou to zbytečné relace, které neukazují žádnou novou relaci. Na následujícím obrázku se jedná o červeně ohraničenou vazbu.

### Spíše jako doplněk - ARC relace

Arc v datovém modelování pomáhá návrhářům ujasnit exklusivní OR skrze relaci, čím lépe jsou specifikovány klientovy požadavky, tím přesnější je finální implementace. Každý podnik má svá omezení na hodnoty atributu a na to, které relace jsou dovoleny. Tato omezení se nazývají constrainty. Mohou být zaměřeny na jednotlivé atributy entit nebo na relace mezi entitami. Příkladem omezení, může být pravidlo, kdy každý zaměstnanec musí pracovat v jednom a pouze v jednom oddělení.

#### EXKLUSIVNÍ OR RELACE 
je to relace mezi jednou entitou a dvěma nebo více entitami, ze kterých může existovat pouze jedna v daný okamžik. V rámci ERD je toto modelováno pomocí ARC. Arc je zakreslován v ERD pomocí plné čáry se zakulacenými rohy tzv. oblouky. Oblouky jsou cestou, jak reprezentovat vzájemnou výlučnost v rámci ERD. Kruh zakreslený na této čáře je na každé relaci, která je součásti tohoto oblouku. Oblouk náleží vždycky jedné entitě, může zahrnovat více než 2 relace, ne všechny relace entity potřebují být zahrnuty v oblouku, entita může mít několik oblouku, oblouk by se měl vždy skládat z relací se stejnou volitelností, všechny relace v oblouku musí být povinné anebo všechny nepovinné. Relace mohou mít rozdílnou kardinalitu, i když je to spíše vzácné. Např. tréninková akce může být uspořádána v domě trenéra nebo u externí tréninkové společnosti. Každá z akcí však může být uspořádána pouze buď v domě trenéra, nebo u externí společnosti.

![alt text](/Obrazky/arc.png)

### Rekurzivní relace

![alt text](/Obrazky/rekurze.png)

**REKURZIVNÍ RELACE** má tendenci problém zjednodušovat, protože používá pouze jednu entitu. Diagram tak není moc zatížen, nicméně je to méně specifické. Není možné mít mandatorní atributy v každé instanci entity, jako je tomu u hierarchické relace. Rekurzivní relace je zakreslena pomocí smyčky, označované také jako „pig ear“ - prasečí ouško.

# MAPOVÁNÍ

### Zákládní proces transformace
Konceptuální model je transformován do relační databáze, to znamená, že entity, atributy, relace a UID budou přeloženy do objektů relační databáze. DATABÁZOVÁ TABULKA je jednoduchá struktura, ve které jsou data organizována a ukládána. Tabulka obsahuje řádky a sloupce, řádky jsou také nazývány jako záznamy. Sloupce jsou původní atributy entity.  Entita nese název podstatným jménem v jednotném čísle, tabulka je označena podstatným jménem v množném čísle.

Základní pravidla databázových tabulek v relačních databázových systémech:


1. Tabulka má řádky a sloupce.
2. Každý sloupec je používán k uložení specifických typu hodnot, jako je číslo zaměstnance, příjmení nebo křestní jméno. (datový typ)
3. Každá tabulka má sloupec, který je zároveň primárním klíčem. Takový primární klíč značí, že všechny hodnoty v tomto sloupci budou unikátní a zároveň také je nad primárním klíčem v relačních databázových systémech vytvořen index (pro rychlejší přístup k datům), primární klíč je označován jako jedinečný identifikátor řádku v tabulce.
4. Tabulka může obsahovat cizí klíč, který může být povinný nebo nepovinný, což znamená, že se může jednat o FK s omezením not null nebo i bez tohoto omezení.


### Transformace

- Probíhá z ER diagramu, který je označován jako konceptuální model do relačního modelu a následně do fyzického modelu. Fyzická implementace do relační databáze obsahuje příkazy pro vytvoření tabulek, sloupců, omezení, apod.
![alt text](/Obrazky/idk.png)
![alt text](/Obrazky/idk2.png)


*Pojmenovací konvence při převodu tabulek a sloupců*

1. Název entity je podstatné jméno v jednotném čísle, název tabulky je množné číslo z názvu entity.
2. Názvy sloupců tabulky jsou identické k názvům atributů.
3. Sloupec může obsahovat až 30 alfanumerických znaků a musí začínat písmenem.
4. Název tabulky a sloupce nemůže obsahovat mezery, speciální znaky, diakritiku.
5. Název tabulky musí být unikátní v rámci celé databáze jednoho uživatele.
6. Názvy sloupců musí být v rámci tabulky jedinečné.
7. Nemohou být použita rezervovaná slova (table, number, sequence, ...).

## Mapování relací

- relace jsou mapovány mezi PK a FK
- relace vytváří jeden nebo více cizích klíčů v tabulce s vícestrannými relacemi
- pro pojmenovávání sloupců cizích klíčů se používá krátký název,
- cizí klíč musí být povinný nebo nepovinný v závislosti na potřebě organizace.

### Druhy mapování relací:

- Mapování povinné relace na jedné straně - použití not null u FK tam, kde existuje povinnost
- Mapování povinné relace na obou stranách - použití not null u FK
- Mapování nepovinných relací na obou stranách - bez omezení
- Mapování nepřesunutelných relací - FK nemůže být modifikován (nelze provést update)
- Mapování barred relace - BARRED RELACE je mapována na cizí klíč na straně více, stejně jako ve vztahu 1:M. V tomto případe cizí klíč hraje dvojí roli, protože je zároveň součástí primárního klíče. V případě entity UCET (ID_uctu, zůstatek, datumZalozeni), BANKA (ID_banky, nazev). V tomto případě ID_banky je cizí klíč v UCET, což odpovídá primárnímu klíči tabulky BANKY, zároveň je to častí primárního klíče tabulky UCTY.
- Mapování M:M

Tyto vztahy zakrývají některé atributy. 
Výchozí situace: Ve škole studuje student více předmětů, a naopak předmět je studován jedním nebo více studenty.

![alt text](/Obrazky/image.png)

Jakmile se ale student zapíše na předmět, poté je nutné evidovat jeho hodnocení, do kterých z těchto entit by bylo ale vhodné hodnocení zařadit? Pokud do „studenta“, potom není jasné, o který předmět se jedná a naopak v entitě „předmět“ není zřejmé, o jakého studenta se jedná.

Řešení? => zavedení mezilehlé, třetí entity, která bývá často označována jako vazební.

![alt text](/Obrazky/image-1.png)


- Mapování relace 1:1
    - Při tomto mapování je vždy vytvořen FK a zároveň je nutné mít unikátní klíč, dále je nutné zohlednit povinnost a nepovinnost tedy omezení NOT NULL.
- Mapování relace 1:M
    - Nejbežnější typ mapování, představuje vazbu PK-FK, kdy FK může být povinný a nepovinný, tedy s omezením NOT NULL či bez.
- Mapování supertyp-subtyp
    - Zde se dle počtu jednotlivých atributů je nutné rozhodnout, zda bude vytvořena jedna velká tabulka zahrnující všechny atributy ze supertypu a dále atributy z podtypů anebo pro každý subtyp bude vytvořena samostatná tabulka, kdy budou v každé tabulce začleněny i společné atributy ze supertypu.

### Implementace pomocí supertypů:
- Tabulka: jenom jedna tabulka je vytvořena, bez ohledu na počet subtypů.
- Sloupce: jedna tabulka obsahuje jeden sloupec pro každý atribut ze supertypů.
- Tabulka také obsahuje sloupec pro každý atribut naležící subtypu, ale všechny sloupce se stávají volitelné.
- Povinný sloupec by měl byt vytvořen, aby odlišoval jednotlivé subtypy entit.
- Hodnota, které by tento sloupec nabýval by byly krátké názvy všech subtypů.
- Unikátní identifikátory se transformují do primárních a unikátních klíčů.
- Relace na úrovni supertypů se transformuji jak je obvyklé, relace subtypu jsou implementovány jako nepovinné cizí klíče.
- Omezení integrity - kontrola je potřebována pro ujištění, že každý z daných subtypů, všechny sloupce se stávají povnnými atributy a nejsou null.

### Impelementace pomocí subtypů:
- Jedna tabulka pro jeden subtyp.
- Každá tabulka obsahuje sloupce pro každý atribut supertypu a navíc s originální volitelností.
- Každá tabulka získává sloupec pro každý atribut náležící subtypu, včetně jeho volitelnosti.
- Primární UID na supertypu vytváří primární klíč pro každou tabulku.
- Sekundární UID supertypu se stává unikátním klíčem v každé tabulce.
- Relace: všechny tabulky získávají cizí klíč pro relaci se supertypem.
- Tato volba přináší jednu tabulku pro jednu entitu.
- Supertyp má cizí klíč pro každou subtyp tabulku.
- Tyto cizí klíče reprezentuji exklusivní relaci.
Jsou volitelné, protože jenom jeden z nich může mít hodnotu pro každý řádek v tabulce.

### Normalizace

1NF vyžaduje, aby neexistoval žádný složený atribut. Relace je v 1. normální formě, když všechny její hodnoty jsou atomické.
Pro kontrolu splnění 1NF je důležité, aby každý atribut obsahoval právě jednu a pouze jednu hodnotu, to znamená pro každou instanci entity jeden kód, jeden název, apod.

Řešení: pokud mám entitu, která není v 1NF tedy obsahuje tzv. složený atribut, pak provedu dekompozici, což znamená, že vytvořím další entitu.

![alt text](/Obrazky/image-7.png)

![alt text](/Obrazky/image-8.png)

### Další příklady:

![alt text](/Obrazky/image-2.png)

Relace je v 2NF, když je v 1. NF a každý neklíčový atribut je plně funkčně závislý na primárním klíči a na každém kandidátním klíči.

Představme si entitu „DODAVATEL PRODUKTŮ“. UID je v tomto případě složeno z čísla dodavatele (ID_dodavatele) a čísla produktů (ID_produktu). Pokud jeden dodavatel bude dodávat 5 různých produktů, potom bude vytvořeno 5 různých instancí. Co se stane potom, pokud se změní název dodavatele? V databázi bude nutné upravovat mnoho záznamů, a co když u některých hodnotu změníme a někde zůstane nezměněna? Jak potom bude uživatel vědět, která hodnota je pravdivá? Např. nesmí být jeho součástí nebo charakteristikou daného UID. Je cena v tomto případě součástí čísla dodavatele, čísla produktu nebo obojího? 2NF vyžaduje odpověď OBOJÍHO na předchozí otázku

![alt text](/Obrazky/image-3.png)

![alt text](/Obrazky/image-4.png)

Relace je v 3NF, když je v 2. NF a všechny neklíčové atributy jsou vzájemně nezávislé.

3NF zakazuje takzvané tranzitivní závislosti - ty existují pokud nějaký atribut v entitě je závislý na některém jiném neklíčovém atributu v této entitě.

Příklad: Zamyslete se, co byste ukládali za informace o vaší kolekci CD. Budou informace o obchodu, kde bylo CD zakoupeno spadat do stejné entity jako informace o CD? Pokud se změní adresa obchodu, potom budeme muset změnit všechny záznamy CD nakoupených v tomto obchodě. Adresa obchodu je závislá na číslu CD, které je jedním z UID dané entity. Díky tomu je entita v 1NF a 2NF. Ale adresa obchodu je také závislá na názvu obchodu, který je neklíčový atribut. Toto je příklad tranzitivní závislosti a porušení 3NF. Správně normalizovaný model je zobrazen níže - vytvoří se druhá entita obchod s relaci k CD.

![alt text](/Obrazky/image-5.png)

![alt text](/Obrazky/image-6.png)

- UNF: Nenormalizovaná databáze.
- 0NF: Alespoň jeden atribut obsahuje více než jednu hodnotu.
- 1NF: Každý atribut obsahuje pouze atomické hodnoty.
- 2NF: Každý neklíčový atribut je plně závislý na každém kandidátním klíči.
- 3NF: Všechny neklíčové atributy musí být vzájemně nezávislé.
- BCNF: Atributy, které jsou součásti primárního klíče, musí být vzájemně nezávislé. 
- 4NF: Relace popisuje pouze příčinnou souvislost mezi klíčem a atributy.
- 5NF: Relace již není možno bezeztrátově rozložit.
