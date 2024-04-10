Jednoduché datové typy:
- celé číslo (int)
- desetinné číslo (float)
- znak (char)

Integer
- signed/unsigned

byte - unsigned int -> 8 bitů, 0 - 255

signed int - několik přístupů, např. první bit je znaménkový bit, zbytek je hodnota
Aktivně se používá BINÁRNÍ KOMPLEMENT, kde se bity invertují a přičte se 1 - je to proto, aby když se sečte - a + tak vyšla 0

floaty, doubly
exponent, mantisa
3.134444 * 10 ^ 10
mantisa  * 10 ^ exponent
->> problémy s floating point aritmetikou, nelze úplně přesně reprezentovat desetinné hodnoty

Složené datové typy:
- pole
- řetězec
- objekt
- struktura

Stack, heap
- stack - lokální proměnné, rychlejší přístup, omezená velikost
- heap - dynamicky alokované proměnné, pomalejší přístup, neomezená velikost (např. objekty apod., ve stacku na ně je jen reference)

Garbage collection

Přetypování - konverze datových typů

Silně, slabě typované jazyky
silně -> striktně definujeme typy, např. C, C++, Java, C# - typy se kontrolují při kompilaci
slabě -> nejsou striktně definovány typy, např. Python, JavaScript

Tzn také Kompilované/interpretované jazyky

Generické datové typy - umožňují přijímat různé datové typy, např. List<T> v C#

