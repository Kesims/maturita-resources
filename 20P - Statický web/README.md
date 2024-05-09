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
•	Color
•	Date (a další s časem)
•	Text
    o	Email, password
•	Checkbox
•	Radio
## XML
eXtensible Markup Language

Značkovací jazyk

Nemá nepárové značky

Většinou se používají vlastní tagy

XML je case sensitive

## HTML x XML
V HTML se obecně používají předem definované tagy

XML se používá na ukládání dat, HTML na zobrazování

## xHTML

HTML dokument, který dodržuje standardy XML

Především nepoužívá nepárové tagy ```(místo <img> použije <img></img> nebo <img />)```

Atributy musí být v uvozovkách ```<img src=“pomoc“>```

## Doctype
Doctype slouží jako informace pro browser, jak má s dokumentem nakládat
## CSS

Cascading Style Sheets

Aktuálně na verzi 3 z roku 1999

Aplikuje na principu specificity selektoru a kaskádování
	
  Čím níž tím vyšší priorita
	
  Čím specifičtější tím vyšší priorita

### Selektory
•	„.“ – tečka – vybere prvky s třídou

o	.třída

•	„#“ – ne – vybere prvek s ID

o	#ID

•	„*“ – hvězdička – vybere všechny prvky

•	tag.třída

o	Vybere všechny tagy s třídou (funguje i na ID)

•	div img

o	Vybere všechny img tagy uvnitř div tagu

•	div, img 

o	Vybere všechny div a img tagy

•	div > img

o	Vybere všechny img tagy s rodičem div

•	div + img

o	Vybere všechny img tagy, které jsou prvním potomkem divu

•	p ~ img

o	Vybere všechny img tagy, které jsou okamžitě za p

### Sekvencování
Selektory jde sekvencovat například takto:

.třída1.třída2

•	Vybere všechny tagy, které mají třídu1 a třídu2

```
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

### Flexbox:
Vlastnosti: display: flex;

Popis: 

Flexbox je technika uspořádání prvků v jednorozměrném layoutu, která umožňuje flexibilitu v uspořádání prvků ve flexibilním kontejneru. 
Pomocí vlastností jako justify-content, align-items a flex-direction můžete ovládat uspořádání prvků ve směru řádků nebo sloupců.
### Grid Layout:
Vlastnosti: display: grid;

Popis: 
Grid Layout je technika uspořádání prvků v dvourozměrném layoutu pomocí řádků a sloupců. Umí lépe zacházet s komplexnějšími rozloženími než Flexbox.
Pomocí vlastností jako grid-template-columns, grid-template-rows a grid-gap můžete definovat strukturu a vzdálenosti mezi řádky a sloupci.

## Input
### Input (Vstup):
```<input>```: Obecný prvek pro vstup dat. Má různé typy, jako textové pole, tlačítko, zaškrtávací políčko, atd.

Typy: text, password, checkbox, radio, submit, button, file, email, number, date, tel, url, atd.
### Textarea (Textové pole):
```<textarea>```: Prvek pro větší množství textu, kde je možné zadat více řádků textu.
### Label (Popisek):
```<label>```: Popisuje vstupní prvek, pomáhá uživatelům porozumět, co je požadováno.
### Select (Výběrový seznam):
```<select>```: Tvoří roletový seznam, ze kterého lze vybrat jednu nebo více možností.
### Option (Možnost):
```<option>```: Definuje jednu možnost výběru uvnitř prvku <select>.

## javascript sem nepatří

bootstrap, tailwind, apod.

eventuelně less, sass apod.

