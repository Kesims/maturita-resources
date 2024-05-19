# Statický web
## html5
Hyper Text Markup Language

Značkovací jazyk

Nadstavba XML

Aktuálně na verzi 5, která vyšla v roce 2014

## Dva druhy tagů (značky)
•	Párové ```<div>   </div>```

•	Nepárové ```<img>```

•	Samo zavírací ```<br/>```
## HTML Formuláře

### Inputy:
1. **`<input type="text">`** - Univerzální textové pole pro libovolný textový vstup.
2. **`<input type="password">`** - Textové pole pro hesla, vstup je skrytý.
3. **`<input type="email">`** - Pole pro zadání e-mailové adresy. Na mobilních zařízeních může zobrazit klávesnici přizpůsobenou pro e-maily.
4. **`<input type="url">`** - Pole pro zadání URL adresy.
5. **`<input type="tel">`** - Pole pro zadání telefonního čísla.
6. **`<input type="number">`** - Pole pro zadání čísel, umožňuje nastavit minimální a maximální hodnoty, krokování apod.
7. **`<input type="range">`** - Posuvník pro výběr hodnoty z daného rozsahu.
8. **`<input type="date">`** - Pole pro výběr data. Poskytuje kalendářní rozhraní.
9. **`<input type="time">`** - Pole pro výběr času.
10. **`<input type="datetime-local">`** - Pole pro zadání data a času bez časového pásma.
11. **`<input type="color">`** - Pole pro výběr barvy. Zobrazí barevnou paletu.
12. **`<input type="search">`** - Pole pro zadání vyhledávacího dotazu.
13. **`<input type="checkbox">`** - Zaškrtávací políčko umožňující výběr více možností.
14. **`<input type="radio">`** - Tlačítko umožňující výběr jedné možnosti z více.
15. **`<input type="file">`** - Pole pro nahrání souboru.
16. **`<input type="hidden">`** - Skryté pole pro předání dat bez zobrazení uživateli.
17. **`<input type="submit">`** - Tlačítko pro odeslání formuláře.
18. **`<input type="reset">`** - Tlačítko pro resetování formuláře do výchozího stavu.
19. **`<input type="button">`** - Tlačítko, které lze naprogramovat pomocí JavaScriptu.

## XML
eXtensible Markup Language

Značkovací jazyk, který je flexibilní a umožňuje definování vlastních značek.

### Hlavní vlastnosti XML:
- **Strukturovaný**: XML umožňuje definovat strukturu dat pomocí tagů a atributů.
- **Samopopisný**: Data v XML jsou popsaná svými tagy, což usnadňuje jejich interpretaci.
- **Rozšiřitelný**: Uživatelé mohou vytvářet vlastní tagy, které jsou vhodné pro jejich specifické potřeby.
- **Case-sensitive**: XML rozlišuje mezi velkými a malými písmeny, což znamená, že `<Tag>` a `<tag>` jsou dva různé tagy.
- **Bez nepárových značek**: Všechny tagy musí být řádně uzavřeny.
- **Podpora pro validaci**: Pomocí DTD (Document Type Definition) nebo XSD (XML Schema Definition) lze definovat pravidla, která musí XML dokumenty dodržovat.

### Použití XML:
- **Ukládání dat**: XML se často používá pro přenos a ukládání dat mezi různými systémy.
- **Konfigurační soubory**: Mnoho aplikací používá XML pro ukládání svých konfiguračních souborů.
- **Webové služby**: XML je základním formátem pro SOAP webové služby.
- **Dokumenty**: XML může být použito i pro tvorbu složitých dokumentů s bohatou strukturou.

## HTML x XML
- **HTML**: HyperText Markup Language, používá se pro vytváření webových stránek a jejich struktury. V HTML se obecně používají předem definované tagy, jako `<div>`, `<span>`, `<p>`, apod.
- **XML**: Používá se hlavně pro ukládání a přenos dat. Na rozdíl od HTML, XML neobsahuje žádné předem definované tagy; uživatelé si mohou definovat své vlastní značky podle potřeby.
- **HTML**: Zaměřuje se na zobrazení dat.
- **XML**: Zaměřuje se na strukturu a přenos dat.

## xHTML
eXtensible HyperText Markup Language

HTML dokument, který dodržuje standardy XML. xHTML je přísnější verze HTML, která zajišťuje, že dokumenty jsou dobře formátované a kompatibilní s XML.

### Hlavní rozdíly mezi HTML a xHTML:
- **Striktní dodržování pravidel XML**: Všechny tagy musí být uzavřeny, atributy musí být v uvozovkách.
- **Nepoužívá nepárové tagy**: Tagy jako `<img>` musí být uzavřeny, tedy `<img></img>` nebo `<img />`.
- **Atributy musí být v uvozovkách**: Například `<img src="pomoc" />`.

### Příklad xHTML kódu:
```xhtml
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title>Titulní stránka</title>
</head>
<body>
    <h1>Vítejte na mé stránce!</h1>
    <p>Toto je příklad xHTML dokumentu.</p>
    <img src="obrazek.jpg" alt="Popis obrázku" />
</body>
</html>
```
### Výhody xHTML:
- **Kompatibilita**: xHTML dokumenty jsou kompatibilní s XML nástroji a technologiemi.
- **Standardizace**: Dodržování přísných pravidel zajišťuje konzistentní a předvídatelné zobrazení v prohlížečích.
Rozšiřitelnost: Lze snadno rozšiřovat a integrovat s dalšími XML aplikacemi.
### Nevýhody xHTML:
-  **Složitější syntaxe**: Přísná pravidla mohou být pro některé uživatele obtížnější na dodržování.
-  **Kompatibilita**: Některé starší prohlížeče nemusí plně podporovat všechny aspekty xHTML.

## Doctype
Doctype slouží jako informace pro browser, jak má s dokumentem nakládat.

## CSS
**Cascading Style Sheets**

Aktuálně na verzi 3 z roku 1999.

Aplikuje se na principu specificity selektoru a kaskádování:

- Čím níž, tím vyšší priorita.
- Čím specifičtější, tím vyšší priorita.

### Selektory
- `.` – tečka – vybere prvky s třídou:
  - `.třída`

- `#` – mřížka – vybere prvek s ID:
  - `#ID`

- `*` – hvězdička – vybere všechny prvky.

- `tag.třída` – vybere všechny tagy s třídou (funguje i na ID).

- `div img` – vybere všechny img tagy uvnitř div tagu.

- `div, img` – vybere všechny div a img tagy.

- `div > img` – vybere všechny img tagy s rodičem div.

- `div + img` – vybere všechny img tagy, které jsou prvním potomkem divu.

- `p ~ img` – vybere všechny img tagy, které jsou okamžitě za p.

### Sekvencování
Selektory lze sekvencovat například takto:

- `.třída1.třída2` – vybere všechny tagy, které mají třídu1 a třídu2.

### Příklad CSS kódu:
```css
/* Styl pro všechny prvky <div> */
div {
    background-color: lightblue;
    color: white;
}

/* Styl pro prvky s třídou .container, které jsou přímými potomky <body> */
body > .container {
    border: 2px solid black;
}

/* Styl pro prvky s třídou .flex-container používající Flexbox */
.flex-container {
    display: flex;
    justify-content: space-around;
}

/* Styl pro prvky s třídou .grid-container používající Grid */
.grid-container {
    display: grid;
    grid-template-columns: auto auto auto;
}
```

## Flexbox
**Vlastnost:** `display: flex;`

**Popis:**
Flexbox je technika uspořádání prvků v jednorozměrném layoutu, která umožňuje flexibilitu v uspořádání prvků ve flexibilním kontejneru. Flexbox je ideální pro rozvržení v jedné dimenzi, buď v řadě, nebo ve sloupci. Pomocí různých vlastností můžete přesně určit, jak se prvky budou chovat a uspořádávat.

**Klíčové vlastnosti Flexboxu:**

- `flex-direction`: Definuje směr hlavní osy (řádek nebo sloupec).
  - `row` (výchozí) – prvky jsou uspořádány v řádku.
  - `column` – prvky jsou uspořádány ve sloupci.

- `justify-content`: Určuje zarovnání prvků podél hlavní osy.
  - `flex-start` – prvky jsou zarovnány k začátku kontejneru.
  - `center` – prvky jsou zarovnány do středu.
  - `space-between` – prvky jsou rovnoměrně rozděleny s mezerami mezi nimi.
  - `space-around` – prvky mají rovnoměrné mezery kolem sebe.

- `align-items`: Určuje zarovnání prvků podél vedlejší osy.
  - `flex-start` – prvky jsou zarovnány k začátku vedlejší osy.
  - `center` – prvky jsou zarovnány do středu vedlejší osy.
  - `stretch` – prvky se natáhnou, aby vyplnily kontejner.

- `flex-wrap`: Určuje, zda se prvky mohou přesouvat na další řádky nebo sloupce.
  - `nowrap` (výchozí) – prvky zůstanou na jednom řádku nebo sloupci.
  - `wrap` – prvky se zabalí na další řádek nebo sloupec.

**Příklad použití Flexboxu:**
```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}

.item {
    flex: 1;
    margin: 10px;
}
```
## Bootstrap

**Popis:**
Bootstrap je populární front-endový framework pro vývoj responzivních a mobilně přívětivých webových stránek. Byl vytvořen vývojáři z Twitteru a je navržen tak, aby usnadnil vývoj webových aplikací a stránek díky předpřipraveným stylům a komponentám.

**Klíčové vlastnosti:**
- **Responsivní design:** Bootstrap využívá mřížkový systém, který umožňuje snadno vytvářet responzivní rozložení.
- **Předpřipravené komponenty:** Obsahuje množství komponent jako tlačítka, navigace, modály, formuláře atd.
- **Podpora JavaScriptu:** Nabízí integrované JavaScriptové komponenty pro dynamické funkce, jako jsou modální okna nebo karusely.
- **Snadná integrace:** Jednoduchá integrace s existujícími projekty pomocí CSS a JavaScriptových knihoven.

**Příklad použití:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <title>Bootstrap Example</title>
</head>
<body>
    <div class="container">
        <h1 class="text-center">Hello, Bootstrap!</h1>
        <button class="btn btn-primary">Click me</button>
    </div>
</body>
</html>
```
## Tailwind CSS

**Popis:**
Tailwind CSS je utility-first CSS framework, který umožňuje rychlé vytváření uživatelských rozhraní přímo v HTML souborech pomocí utility tříd. Na rozdíl od tradičních CSS frameworků, Tailwind neobsahuje předdefinované komponenty, ale poskytuje základní stylové třídy, které lze kombinovat pro tvorbu unikátních designů.

**Klíčové vlastnosti:**
- **Utility-first přístup:** Poskytuje sadu utility tříd, které umožňují rychlé prototypování a vytváření vlastních komponent.
- **Vysoká konfigurovatelnost:** Umožňuje snadné přizpůsobení pomocí konfiguračního souboru.
- **Reusability:** Stylové třídy jsou modulární a opakovaně použitelné, což vede k čistšímu a udržovatelnějšímu kódu.
- **Responsive design:** Podporuje responzivní návrh pomocí utility tříd pro různé velikosti obrazovek.

**Příklad použití:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.0.1/dist/tailwind.min.css" rel="stylesheet">
    <title>Tailwind CSS Example</title>
</head>
<body>
    <div class="container mx-auto p-4">
        <h1 class="text-4xl text-center text-blue-500">Hello, Tailwind CSS!</h1>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Click me</button>
    </div>
</body>
</html>
```
## Rozdíly mezi Tailwind CSS a Bootstrap

**Přístup:**
- Tailwind CSS je utility-first CSS framework, který umožňuje rychlé vytváření uživatelských rozhraní přímo v HTML souborech pomocí utility tříd.
- Bootstrap nabízí sady předdefinovaných komponent a tříd pro rychlé vytváření responsivních webových stránek.

**Komponenty:**
- Tailwind CSS neobsahuje předdefinované komponenty, ale poskytuje základní stylové třídy, které lze kombinovat pro tvorbu unikátních designů.
- Bootstrap poskytuje více hotových komponent, což usnadňuje vývoj webových stránek, zejména pro začátečníky.

**Velikost:**
- Tailwind CSS generuje obvykle menší výstupní soubory, protože se používají pouze ty styly, které jsou skutečně potřeba.
- Bootstrap může mít větší výstupní soubory, protože obsahuje více předdefinovaných stylů a komponent.

## LESS

**Popis:**
LESS (Leaner Style Sheets) je CSS preprocessor, který rozšiřuje možnosti standardního CSS pomocí funkcí jako proměnné, zanořování, mixiny a další. LESS je zpětně kompatibilní s CSS, což znamená, že platné CSS je platné i v LESS.

**Klíčové vlastnosti:**
- **Proměnné:** Umožňují ukládat hodnoty, které lze použít na více místech.
- **Zanořování:** Umožňuje zanořovat selektory, což vede k čitelnějšímu kódu.
- **Mixiny:** Umožňují opakovaně používat skupiny CSS vlastností.
- **Funkce a operace:** Poskytuje funkce pro manipulaci s hodnotami a operace pro aritmetické výpočty.

**Příklad použití:**
```less
@primary-color: #4D926F;

body {
  color: @primary-color;
}

.container {
  width: 80%;
  margin: 0 auto;
  
  .header {
    background: @primary-color;
    padding: 10px;
    
    h1 {
      font-size: 2em;
    }
  }
}
```

## Sass

**Popis:**
Sass (Syntactically Awesome Stylesheets) je CSS preprocessor, který nabízí pokročilé funkce pro psaní CSS, jako jsou proměnné, zanořování, dědičnost, mixiny a další. Sass má dvě syntaxe: tradiční Sass a SCSS, což je syntaxe více podobná CSS.

**Klíčové vlastnosti:**
- **Proměnné:** Umožňují ukládat hodnoty pro opakované použití.
- **Zanořování:** Umožňuje zanořovat selektory podobně jako v LESS.
- **Mixiny:** Umožňují opakovaně používat skupiny CSS vlastností.
- **Dědičnost:** Umožňuje selektorům dědit vlastnosti jiných selektorů.
- **Funkce a operace:** Nabízí množství funkcí pro manipulaci s hodnotami a operace pro výpočty.

**Příklad použití:**

```scss
$primary-color: #333;

body {
  color: $primary-color;
}

.container {
  width: 80%;
  margin: 0 auto;
  
  .header {
    background: $primary-color;
    padding: 10px;
    
    h1 {
      font-size: 2em;
    }
  }
}
```
## Rozdíly mezi Sass a LESS

**Syntaxe:**
- Sass nabízí dvě syntaxe - tradiční Sass a SCSS (Syntaxe nadmnožiny CSS), zatímco LESS má jednodušší syntaxi.

**Funkce:**
- Sass poskytuje pokročilé funkce pro psaní CSS, jako jsou proměnné, zanořování, dědičnost, mixiny a další.
- LESS obsahuje funkce jako proměnné, zanořování, mixiny a další, ale je méně bohatý na funkce než Sass.

**Dědičnost:**
- Sass umožňuje selektorům dědit vlastnosti jiných selektorů.
- Dědičnost v LESS je podobná jako v Sass, ale způsob zápisu může být odlišný.

**Kompatibilita:**
- Sass je kompatibilní s CSS a zároveň přináší nové funkce, což může být užitečné pro velké projekty.
- LESS je zpětně kompatibilní s CSS, což znamená, že platné CSS je platné i v LESS, což usnadňuje přechod ze standardního CSS.
