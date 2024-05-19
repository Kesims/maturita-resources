# Skriptovací jazyky pro server a prohlížeč

### Skriptovací jazyky pro prohlížeč (Client-side)
Client-side skriptovací jazyky jsou prováděny v uživatelově prohlížeči. Tyto jazyky umožňují interaktivitu, dynamické aktualizace a manipulaci s obsahem bez nutnosti komunikace se serverem.

- **JavaScript**
  - **Popis**: Nejčastěji používaný client-side jazyk.
  - **Použití**: Manipulace s DOM, validace formulářů, dynamické změny obsahu.
  - **Výhody**: Rychlá odezva, bez potřeby serverových požadavků pro základní interakce.

- **WebAssembly (Wasm)**
  - **Popis**: Binární instrukční formát pro výkonné webové aplikace.
  - **Použití**: Výpočetně náročné úlohy, hry, simulace.
  - **Výhody**: Vyšší výkon než JavaScript, kompatibilita s více jazyky (C, C++, Rust).

### Skriptovací jazyky pro server (Server-side)
Server-side skriptovací jazyky jsou prováděny na serveru. Tyto jazyky umožňují generování dynamického obsahu, komunikaci s databázemi a provádění komplexních operací před odesláním výsledků klientovi.

- **Node.js**
  - **Popis**: JavaScript runtime prostředí pro server-side skriptování.
  - **Použití**: Webové servery, API, real-time aplikace.
  - **Výhody**: Rychlý díky asynchronnímu I/O, využívá JavaScript jak na klientské, tak na serverové straně.

- **Java**
  - **Popis**: Univerzální objektově orientovaný jazyk.
  - **Použití**: Enterprise aplikace, webové servery, backend systémy.
  - **Výhody**: Silná typová kontrola, robustnost, podpora pro multithreading.

- **C#**
  - **Popis**: Objektově orientovaný jazyk vyvinutý firmou Microsoft.
  - **Použití**: Webové aplikace (ASP.NET), desktopové aplikace, herní vývoj.
  - **Výhody**: Silná integrace s Microsoft ekosystémem, podpora pro moderní jazykové prvky.

- **Python**
  - **Popis**: Vysokoúrovňový, interpretovaný jazyk.
  - **Použití**: Webové servery (Django, Flask), datová analýza, strojové učení.
  - **Výhody**: Snadná čitelnost kódu, rozsáhlá knihovna modulů.

- **PHP**
  - **Popis**: Jazyk specificky navržený pro webový vývoj.
  - **Použití**: Webové servery, dynamické webové stránky, API.
  - **Výhody**: Široké využití, snadná integrace s databázemi, velká komunita.

### Klíčové rozdíly
- **Provedení**:
  - **Client-side**: Kód je prováděn v prohlížeči uživatele.
  - **Server-side**: Kód je prováděn na serveru před odesláním výsledků klientovi.

- **Odezva a výkon**:
  - **Client-side**: Rychlá interaktivní odezva, ale omezená výkonem uživatelova zařízení.
  - **Server-side**: Větší výkon, možnost provádět složité operace, ale může mít vyšší latenci kvůli síťovým požadavkům.

- **Bezpečnost**:
  - **Client-side**: Méně bezpečné, protože kód je viditelný uživateli.
  - **Server-side**: Bezpečnější, protože kód je skrytý na serveru a uživatel vidí pouze výsledky.

- **Interakce s databází**:
  - **Client-side**: Nemá přímý přístup k databázím.
  - **Server-side**: Má přímý přístup k databázím, může provádět CRUD operace.

### Kombinace server-side a client-side
Moderní webové aplikace často využívají kombinaci obou přístupů:
- **Server-side**: Pro generování dynamického obsahu, autentizaci a interakci s databázemi.
- **Client-side**: Pro interaktivitu, aktualizace uživatelského rozhraní a zpracování uživatelských akcí bez nutnosti načítání celé stránky.

Příklad:
- **Server**: Node.js, Python, PHP.
- **Client**: JavaScript, WebAssembly.

# PHP a práce s databází
PHP je často využíván pro práci s databázemi, ať už pomocí nativních rozhraní nebo pomocí frameworků jako je například Laravel, který poskytuje jednoduché a elegantní ORM (Object-Relational Mapping) pro manipulaci s databází.

### Práce s databázemi v PHP
PHP nabízí několik způsobů, jak pracovat s databázemi:
- **MySQLi**: Rozhraní pro práci s MySQL databázemi.
- **PDO (PHP Data Objects)**: Flexibilní rozhraní, které podporuje více databázových systémů (např. MySQL, PostgreSQL, SQLite).

#### Příklad použití PDO:
```php
try {
    $dbh = new PDO('mysql:host=localhost;dbname=testdb', $username, $password);
    foreach($dbh->query('SELECT * from users') as $row) {
        print_r($row);
    }
    $dbh = null;
} catch (PDOException $e) {
    echo "Error: " . $e->getMessage();
}
```
### Frameworky a ORM
Frameworky jako Laravel poskytují vyšší úroveň abstrakce pro práci s databázemi, což zjednodušuje operace a zvyšuje bezpečnost kódu.

Příklad použití Eloquent ORM v Laravelu:
```php
$users = App\Models\User::all();
foreach ($users as $user) {
    echo $user->name;
}
```

## Formuláře - metody POST/GET
Data můžeme přijímat pouze dvěma způsoby:

- **GET:** Nemění stav serveru, lze ho cachovat. Používá se pro získávání dat.
- **POST:** Používá se pro odesílání citlivých dat (např. hesla), velkých dat a pro jakoukoliv změnu stavu serveru.

#### Příklad použití metod GET a POST v PHP:
```php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['name'];
} else {
    $name = $_GET['name'];
}
```
Další metody *NEJSOU WEBOVÉ*

## Validace a sanitizace dat
Data vždy validujeme, a to na obou stranách (klient i server)!

### Validace
Ověření správnosti a úplnosti dat. Příklady validace:

- Kontrola, zda je pole vyplněné.
- Kontrola formátu e-mailové adresy.
- Ověření délky řetězce.
### Sanitizace
Sjednocení formátu v databázi a obrana proti SQL injection. Příklady sanitizace:

- Ořezání mezer.
- Převedení na malá písmena.
- Odstranění škodlivých znaků.

#### Příklad sanitizace v PHP:
```php
$name = trim($_POST['name']);
$email = filter_var($_POST['email'], FILTER_SANITIZE_EMAIL);
```

## Webové útoky a ochrana
### SQL Injection
Vložení škodlivého SQL kódu do formuláře, který se spustí na serveru.

- Obrana: Sanitizace vstupů, používání připravených dotazů (prepared statements).

#### Příklad připraveného dotazu v PHP:
```php
$stmt = $dbh->prepare("SELECT * FROM users WHERE email = :email");
$stmt->bindParam(':email', $email);
$stmt->execute();
```

### XSS (Cross-Site Scripting)
Podstrčení vlastního JavaScriptu, který se vykoná na stránce.

- Obrana: Sanitizace vstupů, použití innerText místo innerHTML při zobrazení uživatelských vstupů.
### CSRF (Cross-Site Request Forgery)
Útok, který nutí uživatele vykonat nežádoucí akci na webové aplikaci, kde je autentizován.

- Obrana: Použití CSRF tokenů, které se kontrolují při každém požadavku na změnu stavu serveru.
### Brute Force
Útok, při kterém útočník zkouší různé kombinace hesel, dokud nezjistí správné heslo.

- Obrana: Omezení počtu pokusů o přihlášení, použití CAPTCHA, silné heslové politiky.

#### Příklad CSRF ochrany v Laravelu:
```php
<form method="POST" action="/profile">
    @csrf
    <input type="text" name="name">
    <button type="submit">Submit</button>
</form>
```
## Bezstavový protokol (HTTP)

### Charakteristiky bezstavového protokolu
- **Nezávislost požadavků**: Každý požadavek je zpracováván samostatně a nezávisle na ostatních. Server neuchovává žádné informace o předchozích požadavcích.
- **Škálovatelnost**: Jednoduchost protokolu umožňuje snadné rozšiřování a škálování aplikací, protože server nemusí spravovat stav mezi požadavky.
- **Jednoduchost**: Implementace je jednodušší, protože server se nemusí starat o správu stavu klienta.

### Autentizace a správa stavu
Přestože HTTP je bezstavový, moderní webové aplikace často potřebují uchovávat informace o stavu uživatele (např. přihlášení). K tomu se používají různé techniky, jako jsou:

- **JWT (JSON Web Tokens)**: Tokeny, které obsahují informace o uživateli a jsou podepsané, aby byla zajištěna jejich integrita. Tyto tokeny se posílají s každým požadavkem a server je ověří, aniž by musel uchovávat stav.
- **Session cookies**: Servery mohou vytvořit relace (sessions) a posílat klientům cookies s identifikátorem relace. Tento identifikátor je použit pro vyhledání relace na serveru.

#### Příklad použití JWT:
```javascript
// Vytvoření JWT při přihlášení
const jwt = require('jsonwebtoken');
const token = jwt.sign({ userId: user.id }, 'your-secret-key', { expiresIn: '1h' });

// Ověření JWT při každém požadavku
const decoded = jwt.verify(token, 'your-secret-key');
```
## Práce s heslem
Hesla nikdy neukládáme v čisté podobě. Místo toho používáme hashovací funkce a sůl, aby bylo zajištěno, že stejná hesla budou mít různé hashe.

- **Hashování:** Proces převodu hesla na pevnou délku, která reprezentuje heslo, ale nelze ho zpětně snadno převést.
- **Sůl (Salt):** Náhodná data přidaná k heslu před hashováním, která zajišťují, že stejné heslo má různé hashe při každém použití.

#### Příklad hashování hesla v Node.js pomocí bcrypt:
```javascript
const bcrypt = require('bcrypt');
const saltRounds = 10;

bcrypt.hash('myPlaintextPassword', saltRounds, function(err, hash) {
    // Uložení hashe do databáze
});
```

## Frameworky
Frameworky poskytují předdefinovanou strukturu a sadu nástrojů, které usnadňují vývoj webových aplikací. Tyto frameworky často obsahují vestavěnou podporu pro práci s databází, routování URL, zabezpečení a mnoho dalších funkcí.

Příklady populárních frameworků:
- **Express (pro Node.js):** Minimalistický framework pro vytváření serverových aplikací v JavaScriptu.
- **Spring (pro Javu):** Výkonný framework pro tvorbu podnikových aplikací.
- **ASP.NET (pro C#):** Framework od Microsoftu pro vývoj webových aplikací a služeb.
- **Django (pro Python):** Vysokoproduktivní framework s vestavěnou administrací.
- **Laravel (pro PHP):** Elegantní framework s bohatou sadou nástrojů pro vývoj moderních webových aplikací.

#### Příklad základního použití Express v Node.js:
```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
    res.send('Hello World!');
});

app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
```
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




