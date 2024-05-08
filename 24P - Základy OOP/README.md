# 24P Základy OOP (Object-Oriented Programming - 
Objektově orientované programování) **představují koncepty, 
které tvoří základní stavební kameny** objektově orientovaného programování. 
Tento programovací paradigma se zaměřuje na práci s objekty a jejich vzájemné interakce. 
Zde je stručný přehled některých základních prvků OOP:

## Proč OOP:
- Lepší čitelnost kódu
- Znovupoužitelnost
- Snazší Debugování:
    - Lepší struktura a organizace kódu v OOP usnadňuje ladění a hledání chyb. Když každá třída má jasně definovanou odpovědnost - může být snazší identifikovat, kde se problémy vyskytují.
- Komentáře a Dokumentace:
    -  OOP umožňuje lépe organizovat kód, což může snížit potřebu nadměrných komentářů. Díky jasným třídám a metodám může být kód samo o sobě snadno pochopitelný
- Rozšiřitelnost:
    - Díky principům OOP lze software snadno rozšířit

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

```
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
``` 
<br>
<br>

# Kecy

## Override vs. Abstraktní
Virtuální metody mají implementaci a poskytují odvozeným třídám možnost **přepsat** ji. Abstraktní metody neobsahují implementaci a nutí odvozené třídy **přepsat** metodu. Takže abstraktní metody v sobě nemají žádný skutečný kód, a (neabstraktní) podtřídy **MUSÍ** **přepsat** metodu. Virtuální metody mohou obsahovat kód, který obvykle představuje výchozí implementaci něčeho, a libovolné podtřídy **MOHOU** **přepsat** metodu pomocí modifikátoru `override` a poskytnout vlastní implementaci.

## Rozhraní vs. Abstraktní
- Rozhraní nemohou mít stav nebo implementaci
- Třída, která implementuje rozhraní, musí poskytnout implementaci všech metod tohoto rozhraní
- Abstraktní třídy mohou obsahovat stav (datové členy) a/nebo implementaci (metody)
- Abstraktní třídy mohou být děděny bez implementace abstraktních metod (i když taková odvozená třída je sama abstraktní)
- Rozhraní mohou být vícezděděny, abstraktní třídy nemohou (to je pravděpodobně hlavním důvodem, proč jsou rozhraní oddělena od abstraktních tříd - umožňují implementaci vícezdědění, která odstraňuje mnoho problémů obecného vícezdědění).

Abstract classes are used for Modelling a class hierarchy of similar looking classes (For example Animal can be abstract class and Human , Lion, Tiger can be concrete derived classes)
AND
Interface is used for Communication between 2 similar / non similar classes which does not care about type of the class implementing Interface(e.g. Height can be interface property and it can be implemented by Human , Building , Tree. It does not matter if you can eat , you can swim you can die or anything.. it matters only a thing that you need to have Height (implementation in you class) )

## DRY:
    • DRY je zkratka pro "Don't Repeat Yourself". Tato zásada zdůrazňuje snahu minimalizovat opakování kódu v projektu. Místo toho, abychom stejný kód psali opakovaně, měli bychom ho extrahovat do jednoho místa a znovu používat toto místo.
    • Proč:
        ◦ Snížení chyb: Když měníme kód, který je napsán pouze jednou, nemusíme se starat o to, že zapomeneme aktualizovat všechny kopie kódu.
        ◦ Údržba: Změny v chování můžeme provádět na jednom místě, což zjednodušuje údržbu.
## SOLID:
Principy SOLID je pět zásad objektově orientovaného návrhu tříd. Jedná se o soubor pravidel a osvědčených postupů, které je třeba dodržovat při návrhu struktury tříd.

**SRP** - Jednotná odpovědnost (Single Responsibility Principle):
    • Třída by měla mít pouze jednu odpovědnost a měla by mít jen jediný důvod ke změně. To zajišťuje jednotnost a snižuje riziko chyb.

**OCP** - Otevřené/zavřené (Open/Closed Principle):
    • Software by měl být otevřen pro rozšíření, ale zavřen pro modifikaci. Měli bychom moci přidat novou funkcionalitu bez změny existujícího kódu.

**LSP** - Liskov substituce (Liskov Substitution Principle):
    • Objekty odvozené od dané třídy by měly být schopny být nahrazeny instancemi této třídy bez ovlivnění správnosti programu.

**ISP** - Rozhraní segregation (Interface Segregation Principle):
    • Mnoho rozhraní specifických pro klienta je lepší než jedno univerzální rozhraní. Klienti by neměli být nuceni implementovat funkci, kterou nepotřebují.

**DIP** - Závislosti inversion (Dependency Inversion Principle):
    • Vyšší úrověň modulů by neměla záviset na nižší úrovni. Závislosti by měly být zaměřeny na abstrakce, ne na konkrétní implementace.
