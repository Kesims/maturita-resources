// asi by chtelo jeste neco pridat ale vubec nevim vo
# Datové typy a jejich vlastnosti

## Jednoduché datové typy:

- **celé číslo (int)** - Reprezentuje celé číselné hodnoty v počítačové paměti. V závislosti na programovacím jazyku může být rozsah těchto hodnot omezen (např. 32-bitové integer v C).

- **desetinné číslo (float)** - Používá se pro reprezentaci desetinných čísel. Floating point čísla používají exponent a mantisu k reprezentaci čísel s plovoucí desetinnou čárkou.

- **znak (char)** - Ukládá jeden znak v kódování Unicode, ASCII nebo jiném znakovém kódování.

- **dvojnásobné desetinné číslo (double)** - Podobné floatu, ale s větší přesností, často používané pro aplikace vyžadující vyšší přesnost v desetinných číslech.

- **boolean (bool)** - Logická hodnota, která může být buď true (pravda) nebo false (nepravda).

- **datum (date)** - Reprezentuje kalendářní datum a čas v různých formátech, včetně roků, měsíců, dnů, hodin, minut a sekund.

### Integer

- *signed/unsigned*

    - **byte** - unsigned int -> 8 bitů, 0 - 255. Využívá se pro ukládání malých celočíselných hodnot, kde není potřeba znaménka.

    - **signed int** - několik přístupů, např. první bit je znaménkový bit, zbytek je hodnota. Využívá se pro reprezentaci celých čísel se znaménkem.

    - Aktivně se používá **BINÁRNÍ KOMPLEMENT**, kde se bity invertují a přičte se 1 - je to proto, aby když se sečte - a + tak vyšla 0.

### Floating point čísla

- *exponent, mantisa*

    - Příklad: 3.134444 * 10 ^ 10. Floating point čísla jsou reprezentována pomocí exponentu a mantisy, což umožňuje reprezentovat velké rozsahy čísel s různými úrovněmi přesnosti.

    - **Problémy s floating point aritmetikou**: Nelze úplně přesně reprezentovat desetinné hodnoty kvůli konečné přesnosti reprezentace v binární podobě.


## Složené datové typy:

- **pole (array/list)** - Skupina prvků stejného datového typu uložených za sebou v paměti.

- **řetězec (string)** - Sekvence znaků uložená v paměti, často používaná pro reprezentaci textu.

- **objekt** - Složený datový typ, který může obsahovat různé proměnné a metody.

- **struktura (struct)** - Datová struktura, která umožňuje kombinovat různé typy dat pod jedním jménem.

- **slovník (dictionary)** - List který má 2 datové hodnoty Key(většinou int) a Value

## Stack a heap

- **stack** - Lokální proměnné a funkční volání jsou spravovány na stacku. Stack je obvykle rychlejší než heap, ale má omezenou velikost.

- **heap** - Dynamicky alokované proměnné jsou spravovány v heapu. Heap má pomalejší přístup než stack, ale umožňuje dynamické přidělování a uvolňování paměti a nemá omezenou velikost.

## Garbage collection

- Mechanismus, který automaticky detekuje a uvolňuje nepoužívanou paměť, čímž pomáhá zabránit únikům paměti a paměťovým chybám.
### Jazyky které používají garbage collection:

- **Java**: Java používá garbage collection k automatické správě paměti, což zjednodušuje vývoj softwaru a snižuje riziko úniku paměti.

- **C#**: Stejně jako Java, i C# má vestavěný garbage collector.

- **Python**: Python používá garbage collection pro automatické uvolňování paměti a eliminaci objektů, které již nejsou používány.

### Jazyky které nepoužívají garbage collection:

- **C**: C je jazyk, který nepoužívá vestavěný garbage collector. To může být náročné a vyžaduje pečlivé sledování alokace a dealokace paměti.

- **C++**: Stejně jako C, i C++ nepoužívá vestavěný garbage collector.

- **Rust**: Rust je jazyk s důrazem na bezpečnost a výkon a nepoužívá garbage collection. Místo toho používá systém vlastnictví a půjčování, který umožňuje bezpečné a efektivní správu paměti za běhu programu.

## Přetypování

- Konverze datových typů, která umožňuje převod jednoho typu dat na druhý.
### List možných přetypování
- String to int
- Int to string
- Enum to string
- Enum to int

## Silně vs. slabě typované jazyky

- **Silně typované jazyky** - Striktně definují typy a provádějí kontrolu typů při kompilaci.
    - Java
    - C#
    - C++

- **Slabě typované jazyky** - Neprovádějí striktní kontrolu typů a umožňují flexibilní manipulaci s daty.
    - JavaScript
    - Python
    - Ruby

### Kompilované/interpretované jazyky

- **Kompilované jazyky** - Jsou přeloženy do strojového kódu před spuštěním.
    - C
    - C++
    - Rust

- **Interpretované jazyky** - Jsou interpretovány řádek po řádku za běhu programu.
    - Python
    - JavaScript
    - Ruby
## Generické datové typy

- Umožňují přijímat různé datové typy a provádět operace s nimi bez ohledu na konkrétní typ, což zvyšuje flexibilitu a znovupoužitelnost kódu. Například List<T> v jazyce C# umožňuje ukládat a manipulovat s kolekcí prvků různých typů.
