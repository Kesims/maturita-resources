// Tohle mi poslal kamos je to nejakej yap proste
# Počítačová grafika
Je obor informatiky, sloužící k vytvoření, zobrazování a úpravě grafických prací v prostředí výpočetní techniky.
Z hlediska umění se jedná o samostatný obor.
Rozvíjí se velmi dynamicky a rychle (před pár lety se dalo pracovat pouze na „superpočítačích“, dnes už vše díky lepší procesorům, grafikám a celkově železu zvládají i osobní PC).
Softwary pro tvorbu grafiky jsou dostupnější.

**Pojem počítačová grafika pochází z 60. let, společnost Boeing.**

Vesmírná odysea – 2001 - První film, kde se objevila počítačová grafika.

## Programy na počítačovou grafiku


### Tiskoviny: 
časopisy, noviny, knihy -> **InDesign, Illustrátor**

### Reklama: 
propagační materiály -> **InDesign, Illustrátor, Photoshop**

### Média: 
televizní efekty, titulky -> **Premiere, After Effects, DaVinci Resolve**

### Internetové stránky: 
návrhy webových stránek -> **Figma, Adobe XD**

### 3D modelování a CAD (architektura): 
prostorové modelování, projektování -> **Autodesk 3ds Max, Blender, zBrush, Maya**

### Hry: 
3D a 2D grafika -> **Blender, Photoshop**

## 2D grafika 
### Rasterová vs Bitmapová grafika
#### Rasterová
Grafická práce uložena bod po bodu.

Nazýváná jako bitmapová grafika.

Každý bod obsahuhe - barvu, jas a kontrast.

Z jednotlivých bodů se poté složí celkový obrázek.

Příklad programu využívajícího bitmapovou grafiku: **Microsoft Paint**.

Typy souborů
- .jpg
- .gif
- .tiff
- .png
- .BMP
- .psd
- .jfif

#### Vektorová

Grafická práce uložena po vrcholech.

Kapacitní nároky na uložení rastrového obrázku mohou být v případě velkého rozlišení vysoké.

Typy souborů
- .pdf
- .svg

### Hry
Rovnou počítá s různými tvary, body, přímkami, kružnicemi a jinými geometrickými obrazci (vektory).

Obraz je tvořen z vektorů.

Dosahuje maximální kvality i po vytisknutí.

Volná možnost editace (při zmenšení nedochází ke ztrátě kvality).

Ukládání pomocí matematického zápisu, definice tvaru, barvu, výplň + další parametry křivky.

Typy souborů
.ai - Adobe Illustrator
.svg
.svf - animovaný vektorový obrázek

Při zmenšení nedochází ke ztrátě kvality.

Pracuje se rovnou s geometrickými tvary.

Práce s každým objektem zvlášť.

Vhodná pro tisk

Nelze upravovat fotografie.

Reklamní materiály

Počítačové efekty (2D)

Ilustrace

Tvorba fontů

Tvorba diagramů

Grafika v 3D prostoru.

Příbuzná 2D vektorové grafice.

Pracuje se souřadnicemi bodů -> X, Y a Z.

Výstup je většinou ve formě **renderu**.

Umění
Reklamní materiály
VFX
Animace
Aditivní míchání barev
Způsob míchání, kdy se jednotlivé složky sčítájí.
Často demonstováno za pomocí červené, zelené a modré barvy.
Tvoří trojúhelník a tam kde se překrývají dvě vzniká doplňková barva.
Na místě, kde se překrývají všechny je bílá barva.
Dále platí, že aditivním smícháním barvy a barvy k ní doplňkové, dostaneme barvu bílou.
Subtraktivní míchání barev
Jedná se o úplný opak aditivního míchání.
Způsob míchání, kdy se jednotlivé složky odčítají.
Pro subtraktivní míchání barev se používají barvy doplňkové k základním barvám aditivního míchání, tj. barvy azurová, purpurová a žlutá.
Tam kde se překrývají dvě vzniká doplňková barva.
Na místě, kde se překrývají všechny je černá barva.
aditivní model (sčítání).
Je založen na přirozených vlastnostech lidského oka.
Je složen ze 3 barev a jejich základních kombinací.
Tento model využívá dataprojektory a monitory.
Tvořen třemi základními barvami: červená, zelená a modrá. (RGB == ČZM).
Základní barvy (RGB) leží na osách souřadného systému (X, Y a Z).
V počátku souřadného systému je barva černá.
V protilehlém vrcholu k černé je barva bílá.
Barva a její barva doplňková jsou v protilehlých vrcholech krychle.
Směrem k černému vrcholu klesá jas barev.
Směrem k bílému vrcholu klesá nasycení barev.
Barvy se kódují pomocí hexadecimálních čísel.
Rozsah: 0-255.
Každé číslo představuje podíl barevné složky ve výsledné barvě, v pořadí červená, zelená, modrá.
subtraktivní model (odčítání)
Tvořen třemi základními barvami – azurová, purpurová, žlutá.
Použití: barevný tisk.
Překlad: Hue, Saturation a Brightness (někdy místo Brightness - Value).
Slouží pro lepší míchání barev.
HSV model více odráží vnímání barev člověkem.
Definuje odstín, nasycení a jas.
Jeden ze základních parametrů RGB barevného modelu.
Určuje kolik odstínů barev může mít obrázek.
Všeobecně platí, čím větší barevná hloubka, tím kvalitnější obrázek, tím větší velikost obrázku.
V případě nízkých barevných hloubek je hodnota většinou indexována v určité barevné mapě nebo paletě.
Barvy použitelné v paletě mohou být dány hardwarem nebo modifikovatelné.
Příklad
1bitová barva (2^1 = 2 barvy) monochromatické, často černobílé.
2bitová barva (2^2 = 4 barvy) CGA.
4bitová barva (2^4 = 16 barev) bylo použito např. EGA a u nejnižšího používaného standartu VGA ve vyšším rozlišení.
8bitová barva (2^8 = 256 barev) VGA v nízkém rozlišení, SVGA.
Příklad z praxe
Pomocí 8bitové indexované barvy lze realizovat paletu 3-3-2, u které se 8 bitů indexu palety rozdělí na díly 3-3-2 bity, kterým se přidělí hodnoty barev červené, zelené a modré (RGB)
Důvodem proč 2 bity se přidělí právě modré složce je ten, že lidské oko je na modrou složku nejméně citlivé.
Vlastnost obrázku, která umožňuje zobrazit pozadí pod obrázkem
U monitorů
Myšleno rozměr obrazovky měřený počtem zobrazovaných pixelů.
U tiskáren
Hustota bodů pro tisk.
Jednotka DPI.
U Skenerů
Rozlišení v dpi říká, kolik bodů je vytvořeno ve vznikajícím souboru z obrázku dané velikosti.
Při rozlišení 300 dpi bude obrázek o velikosti 2,54 x 2,54 cm převeden na bitmapu o rozměrech 300 x 300 px.
U digitálních fotoaparátů
Říká kolik bodů má výsledná fotografie.
Body na palec (dots per inch).
Díky DPI poznáme kvalitu obrázku.
Kolik tiskových bodů (pixelů) jsme schopny reprezentovat na jednotce délky.
Monitor (72dpi), tiskárna (minimálně 300dpi, doporučená 600dpi).
Velikostí se rozumí šířka a délka obrázku udávaná v bodech
Šířka X výška.
Při úpravě rozlišení se změní počet bodů v obrázku.
Fotografie 10x15cm, DPI 300, 24bitová hloubka barev -> (10/2,5) x 300 x (15/2,5) x 300 x (24/8) = 6,48 MB).
K zmenšování fotofrafií se používá tzv. "komprese".
Bezztrátová komprese
Dekomprese: "Bílá, bílá, světle šedá, bílá, bílá, bílá, další řádek, bílá, šedá, tmavě šedá, tmavě šedá, šedá, bílá, další řádek ...".
Komprese: "2 bílá, světle šedá, 3 bílá, další, bílá, šedá, 2 tmavě šedá, šedá, bílá, další ...".
Při dekompresi nedochází ke změně...
Ztrátová komprese
Zakóduje rastr například takto: "6 bílá, další, bílá, 4 šedá, bílá, další ...".
Dekomprimovaný obraz je zřejmě odlišný od původního.
Za tuto cenu získáme velmi malý komprimovaný soubor.
### JPEG
Rastrový formát s rekordní ztrátovou kompresí.

Je nevhodný pro ukládání obrázků s jednobarevnými plochami, u nichž dochází k nedokonalé reprodukci.

Nemá rád opakované ukládání.
###  GIF
Výhoda - bezztrátová komprese -> při komprimaci (4:1) nesnižuje kvalita obrázku.

Možnost opakovaného ukládání bez degradace.
###  PNG
Silná beztrátová komprese.

Optimální výsledná velikost.

Transparentnost.
###  BMP
Rastrový formát.

Velká velikost souboru.

Využívají některé apliakce Windows.
###  AI
Vektorový grafický formát.

Adobe Illustrator.

Kvalitní formát.
### PDF
Kombinace rastrové a bitmapové grafiky.

Obsahuje balíčky (pouzdra), 1. pouzdro - vektorové objekty; 2. pouzdro - rastrové obrázky; 3. pouzdro - fonty.

Univerzální formát.

Obrázky už poté nelze znovu zpracovat po uložení do tohoto formátu.

Originální PDF
