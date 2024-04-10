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