# Datové typy a jejich vlastnosti

## Jednoduché datové typy:

- **celé číslo (int)** - Reprezentuje celé číselné hodnoty v počítačové paměti. V závislosti na programovacím jazyku může být rozsah těchto hodnot omezen (např. 32-bitové integer v C).

- **desetinné číslo (float)** - Používá se pro reprezentaci desetinných čísel. Floating point čísla používají exponent a mantisu k reprezentaci čísel s plovoucí desetinnou čárkou.

- **znak (char)** - Ukládá jeden znak v kódování Unicode, ASCII nebo jiném znakovém kódování.

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

- **pole** - Skupina prvků stejného datového typu uložených za sebou v paměti.

- **řetězec** - Sekvence znaků uložená v paměti, často používaná pro reprezentaci textu.

- **objekt** - Složený datový typ, který může obsahovat různé proměnné a metody.

- **struktura** - Datová struktura, která umožňuje kombinovat různé typy dat pod jedním jménem.

## Stack a heap

- **stack** - Lokální proměnné a funkční volání jsou spravovány na stacku. Stack je obvykle rychlejší než heap, ale má omezenou velikost.

- **heap** - Dynamicky alokované proměnné jsou spravovány v heapu. Heap má pomalejší přístup než stack, ale umožňuje dynamické přidělování a uvolňování paměti a nemá omezenou velikost.

## Garbage collection

- Mechanismus, který automaticky detekuje a uvolňuje nepoužívanou paměť, čímž pomáhá zabránit únikům paměti a paměťovým chybám.

## Přetypování

- Konverze datových typů, která umožňuje převod jednoho typu dat na druhý.

## Silně vs. slabě typované jazyky

- **Silně typované jazyky** - Striktně definují typy a provádějí kontrolu typů při kompilaci.

- **Slabě typované jazyky** - Neprovádějí striktní kontrolu typů a umožňují flexibilní manipulaci s daty.

### Kompilované/interpretované jazyky

- **Kompilované jazyky** - Jsou přeloženy do strojového kódu před spuštěním.

- **Interpretované jazyky** - Jsou interpretovány řádek po řádku za běhu programu.

## Generické datové typy

- Umožňují přijímat různé datové typy a provádět operace s nimi bez ohledu na konkrétní typ, což zvyšuje flexibilitu a znovupoužitelnost kódu. Například List<T> v jazyce C# umožňuje ukládat a manipulovat s kolekcí prvků různých typů.
