# 24P Základy OOP (Object-Oriented Programming - 
Objektově orientované programování) **představují koncepty, 
které tvoří základní stavební kameny** objektově orientovaného programování. 
Tento programovací paradigma se zaměřuje na práci s objekty a jejich vzájemné interakce. 
Zde je stručný přehled některých základních prvků OOP:

## Třídy a objekty: 
**Třída je abstraktní popis datové struktury, 
která definuje atributy (data) a metody (funkce),** které s těmito daty pracují. 
Objekt je konkrétní instance třídy, která vytváří konkrétní výskyty daného typu dat.

## Zapouzdření (Encapsulation): 
Zapouzdření je mechanismus, 
který umožňuje **skrýt interní stav objektu a umožňuje přístup k 
němu pouze prostřednictvím definovaných metod třídy**. To zajišťuje, 
že data objektu nejsou přímo přístupná zvenčí a že se mohou chránit 
před neoprávněnými změnami.

## Dědičnost (Inheritance): 
**Dědičnost umožňuje vytvářet nové třídy (potomky) 
na základě existujících tříd (rodičů)**. Potomci zdědí vlastnosti a metody svých 
rodičů a mohou je dále rozšiřovat nebo upravovat. Tímto způsobem může být kód 
znovupoužitelný a hierarchicky organizován.

## Polymorfismus (Polymorphism): 
**Polymorfismus umožňuje jedné metodě pracovat s 
různými typy objektů,** aniž by musela znát konkrétní typ objektu za běhu programu. 
To zlepšuje flexibilitu a modularitu kódu a umožňuje vytvářet univerzální metody.

## Abstrakce (Abstraction): 
**Abstrakce je proces oddělení důležitých informací od 
nevýznamných detailů.** Třídy poskytují abstrakci tím, že definují rozhraní, 
které skrývá interní implementaci a umožňuje programátorům pracovat s objekty na 
vyšší úrovni abstrakce.

**Základy OOP poskytují programátorům mocný nástroj pro vytváření strukturovaného a 
modulárního kódu**, který je snadněji udržovatelný, rozšiřitelný a znovupoužitelný. 
OOP je široce **používaným paradigmatem v mnoha programovacích jazycích, včetně Java, 
C++, Python, C# a mnoha dalších.**





Seznam věcí, které by měla tato otázka obsahovat


abstrakce
zapouzdření
dědičnost
polymorfismus



Objekt
datové položky
properties (vlastnosti - getter+setter+...) = sada obalujících metod, pracujících nad jedněmi daty


Abstrakce = zjednodušování problému (neřeším jak něco dělám, ale co chci navenek)
-> uvnitř mám složitou logiku, která ale navenek je vidět pouze skrze jednoduché API
-> správné pojmenování metod
-> "objektům se nešahá do střívek" - nevidím vnitřní stav objektu


Zapouzdření
-> objekt je zodpovědný za to, hlídal data na vstupu a zaručil tak vnitřní stav
ne "nastavuju hodnotu", ale "nastav si hodnotu"


Dědičnost
-> znovupoužitelnost
-> interface, abstraktní třída
-> pokud dva objekty sdílí kód, udělá se abstraktní typ a z něj se odvodí dva konkrétní

Polymorfismus - interfacy
-> schopnost objektu reagovat na stejný příkaz různým způsobem
-> např. třída Auto, třída Motorka, obě mají metodu "Jede", ale každá se chová jinak



Konstruktor - metoda, která se volá při vytvoření objektu
-> inicializace objektu, otevření spojení s databází apod

Destruktor - metoda, která se volá při zrušení objektu


Statická proměnná - proměnná, která je společná pro všechny instance třídy
Instanční - každá instance má svou vlastní kopii proměnné

Statická metoda - metoda volatelná přes název třídy, ne přes objekt
Instanční - metoda volatelná pouze přes objekt


Overridning - přepsání metody v odvozené třídě


Přetěžování metod - metoda se stejným názvem, ale jinými parametry
Přetěžování operátorů - např. sčítání dvou objektů