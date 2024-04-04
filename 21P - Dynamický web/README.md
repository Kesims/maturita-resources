skript klientský vs serverový

client - javascript, webassembly

na serveru nodejs, java, c#, python, PHP, cokoliv


bezpečnost - formuláře a data

přijetí dat z formulářů - get, post... Další metody NEJSOU WEBOVÉ
(get - nemění stav serveru, lze ho cachovat; post - citlivá data, velká data, jakákoliv změna stavu serveru)


validace dat - vždy!

sanitizace dat - abychom měli jednotný formát v databázi (ořezání mezer, převedení na malá písmena, ...), obrana proti SQL injection


validace na obou stranách, uživatel i server!


útoky - SQL injection, XSS, CSRF, Br
SQL injection - vložení SQL kódu do formuláře, který se spustí na serveru
XSS - podstrčení vlasního JS, který se někomu zobrazí a interpretuje, obrana sanitizací, innerText


Bezstavový protokol - HTTP
po přihlášení uložit formou tokenu -> JWT, session cookies


Nakládání s hesly - hashování, solení - co to je hashovací funkce

MVC - model view controller (model - práce s daty, view - zobrazení, controller - řízení toku mezi MV)
MVVM

AJAX (asynchronous javascript and xml) - asynchronní načítání dat. Dnes místo xml spíš JSON, protobuf apod.

Objektový model dokumentu - DOM (virtuální zrcadlo) - stromová struktura, která reprezentuje strukturu HTML dokumentu

