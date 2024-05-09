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

## Selektory
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

## Sekvencování
Selektory jde sekvencovat například takto:

.třída1.třída2

•	Vybere všechny tagy, které mají třídu1 a třídu2


html + css + javascript - základ webu

sémantický web - pojem - =web, kde se neřeší vzhled, ale jde o obsah. (žádné css). Tzn jedná se pouze o základní html tagy.
-> tzn jde o strukturu webu která se vztahuje k informačnímu významu

základy html:
zanořování tagů, rozdíl mezi HTML a XML, párové a nepárové tagy

xHTML - html, které splňuje xml normu (všechny tagy jsou vždy uzavřené), jaký je rozdíl mezi html a xhtml

základní formulářové prvky a jejich tagy, jednoduché inputtagy, textarea, a potom ne-input tagy jako label, select, option


doctype




css - pravidla - selector, složené závorky, vlastnost: hodnota
grid, flexbox, apod.


css selektory (mezera, >, ., !)


javascript sem nepatří

bootstrap, tailwind, apod.

eventuelně less, sass apod.

