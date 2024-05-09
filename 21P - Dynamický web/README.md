## Skriptovací jazyky server/prohlížeč
* **Client** - javascript, webassembly
* **Server** - cokoliv (nodejs, java, c#, python, PHP)

## PHP a práce s databází
PHP je často využíván pro práci s databázemi, ať už pomocí nativních rozhraní nebo pomocí frameworků jako je například Laravel, který poskytuje jednoduché a elegantní ORM (Object-Relational Mapping) pro manipulaci s databází.


## Formuláře - metody POST/GET
Data můžeme přijímat pouze 2 způsoby: 
* **GET** - nemění stav serveru, lze ho cachovat
* **POST** - citlivá data (např. hesla), velká data, jakákoliv změna stavu serveru

Další metody *NEJSOU WEBOVÉ*

## Validace a sanitizace dat
Data vždy **validujeme**, na obou stranách (klient i server)!

* **Validace** - ověření správnosti a úplnosti dat
* **Sanitizace** - sjednocení formátu v databázi (ořezání mezer, převedení na malá písmena, ...), obrana proti SQL injection

## Webové útoky a ochrana
Typy:
* **SQL injection** - vložení SQL kódu do formuláře, který se spustí na serveru. Obrana sanitizací nebo předkompilovaním dotazu do kterého akorát dosadíme proměnné.
* **XSS** - podstrčení vlasního JS, který se někomu zobrazí a interpretuje. Obrana sanitizací, innerText (jen zobrazení textu, aby se skript nevykonal).
* **CSRF**
* **Brute force**

## Bezstavový protokol (HTTP)
HTTP je protokol, který neuchovává informace o stavu mezi požadavky. To znamená, že každý požadavek je nezávislý a obsahuje všechny potřebné informace pro jeho vyřízení. Tento bezstavový přístup k zajištění komunikace mezi klientem a serverem umožňuje škálovatelnost a jednoduchost implementace.

_"Neříká kdo přistupuje, ale abychom nemuseli stále posílat jméno a heslo, tak si při autentizaci vytváříme **tokeny** (JWT, session cookies). Prakticky každý nový webový projekt (př. Node) ho má."_

## Práce s heslem
* Hesla šifrujeme pomocí **hashů** a **soli** (ne té kuchyňské)

## Frameworky
Frameworky jako je Express pro Node.js, Spring pro Javu, ASP.NET pro C#, Django pro Python nebo Laravel pro PHP poskytují předdefinovanou strukturu a sadu nástrojů, které usnadňují vývoj webových aplikací. Tyto frameworky často obsahují vestavěnou podporu pro práci s databází, routování URL, zabezpečení a mnoho dalších funkcí.

## Architektura MVC
Rozdělení logiky do struktry souborů kódu, kde se každá část specializuje na své specifické úkoly. Toto pomáhá v přehlednosti, organizaci, údržbě a budoucímu rozšíření projektu.

Skládá se ze tří částí:
* **Model** - Zpracování dat
* **View** - Zobrazení dat
* **Controller** - Řízení toku mezi M a V

Dále ještě existuje striktnější MVVM (Model, View, ViewModel) architektura s ještě více oddělenými zodpovědnostmi.

## JavaScript
JavaScript je jedním z nejrozšířenějších programovacích jazyků pro vývoj webových aplikací. Používá se jak na straně klienta (prohlížeč), tak i na straně serveru (Node.js). Je známý svou flexibilitou, interaktivitou a širokou podporou komunitou a nástroji. JavaScript umožňuje dynamické změny na stránce, interakci s uživatelem a asynchronní komunikaci s serverem pomocí AJAX.

## AJAX
AJAX (Asynchronous Javascript And Xml) - Asynchronní načítání dat. Dnes místo xml spíš JSON, protobuf apod. Díky němu nemusím stále data přesměrovávat na nové stránky, ale jen vyměním tu "substránku".

## Objektový model dokumentu
Objektový model dokumentu - DOM (virtuální zrcadlo) - stromová struktura (každý element má children a parenta), která reprezentuje strukturu HTML dokumentu.




