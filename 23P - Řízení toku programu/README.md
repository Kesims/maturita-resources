# 23 - Řízení toku programu
## Podmíněné výrazy
Podmíněné výrazy jsou základním prvkem pro ovládání toku programu v mnoha programovacích jazycích.
Pomocí nich můžeme definovat různé větve kódu, které budou provedeny v závislosti na splnění určité podmínky.

```C#
if (statement) {
    // Do something cool
} else if (another_statement == 1) {
    return true;
} else return false
```

## Cykly
Cykly slouží k opakování částí kódu, dokud je splněná určitá podmínka.
Existují různé typy cyklů, jako je for, foreach, while a do-while.
```C#
//Declare some iterable variable
//Provide a statement that has to be fulfilled. It's checked at beginning of each iteration.
//Give it an action that will be executed on the end of each iteration.
//This one iterates while i < 5 (5 iterations) and writes out the index of each one.
for (int i = 0; i < 5; i++) {
    Console.WriteLine($"Iteration {i}");
}

//Shorter version of for, without statement,
//just going through all elements in iterable such as 
//array, list, dictionary etc.
foreach (int number in array) {
    Console.WriteLine($"Current number: {number}");
}

//This loop just checks whether the statement is true or not 
//and based on that continues exectuing its code or "closes" itself
while(!statement) {
    if(i<5)
        statement=true
    i++;
}

//Exactly the same, except the statement is being 
//checked on the end of iterations
do {
    if(i<5)
        statement=true
    i++;
} while(!statement)
```

## Výjimky
Vyjímky jsou zvláštní typy událostí, které mohou nastat během běhu programu a které mohou narušit běžný tok kódu. Použití **správného řízení výjimek může zlepšit stabilitu a bezpečnost vašeho programu**.V C# se vyjímky řídí pomocí bloků try, catch a finally. Základní struktura vypadá takto:
````try
{
    // Kód, který může vyvolat výjimku
    // Např. Out of bounds of array nebo špatný parse
}
catch (TypVýjimky1 ex)
{
    // Obsluha konkrétního typu výjimky TypVýjimky1
    Throw new OutOfBoundsException();
}
catch (TypVýjimky2 ex)
{
    // Obsluha konkrétního typu výjimky TypVýjimky2
    Throw new 
}
finally // Kdo kurva používa finally????
{
    // Volitelný blok finally, který se vždy provede bez ohledu na to, zda byla výjimka vyvolána nebo ne
}
````

### Try
**Obsahuje kód, ve kterém může nastat výjimka**. Pokud se v tomto bloku objeví výjimka, program se okamžitě přesune na odpovídající blok catch.
### Catch
Obsahuje kód pro **zpracování výjimky**. Můžete mít více bloků catch pro různé typy výjimek. Pokud se vyskytne výjimka odpovídající danému typu v catch, program provede kód uvnitř tohoto bloku.
### Finally
**Je volitelný** a obsahuje kód, který se vždy provede, bez ohledu na to, zda byla výjimka vyvolána nebo ne. Často se používá k uvolnění prostředků nebo k provedení kódu, který by měl být spuštěn vždy, když se blok try dokončí.
## Řízení událostmi


## Funkcionální programování
