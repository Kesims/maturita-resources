# 14 - Počítačová grafika (Vc)
*(rastrová/vektorová grafika, barevná hloubka, indexovaná barva, barevné modely, souborové formáty, výpočet velikosti uloženého souboru)*

- **Definice:** Je to obor informatiky, který zahrnuje zobrazování a úpravu prostorových informací a odrazu reálného světa v prostředí výpočetní techniky. Z hlediska umění je počítačová grafika samostatným oborem
- **Historie:** Dříve byla editace grafiky výsadou grafických a reklamních studií s "superpočítači". Dnešní výkonné počítače umožňují každému uživateli editovat grafiku pomocí přístupného softwaru
- **Dostupnost:** Programy pro zpracování grafiky jsou stále dostupnější. I poloprofesionální software je pro domácí použití cenově dostupný
- **První využití:** Pojem "počítačová grafika" se objevil v 60. letech u společnosti Boeing. Prvním filmem, kde byla skutečně využita, byl The Andromeda Strain z roku 1971


## Využití počítačové grafiky

- **Tiskoviny:** Všechny tiskoviny, jako časopisy, noviny, knihy, jsou vytvářeny grafiky na počítači
- **Reklama:** Reklamní materiály a televizní spoty procházejí rukama specializovaných grafiků
- **Média a multimédia:** Efekty v televizi, multimediální CD, televizní efekty a titulky
- **Internetové stránky:** Grafika pro internet klade důraz na velikost dat, názornost a přehlednost
- **3D modelování:** Vytváření nových světů a objektů, modelování automobilů, interiérů apod
- **CAD a CAM projektování:** Konstruování budov, vytváření nových návrhů a konstrukcí
- **Hry:** Grafika hraje významnou roli v zábavním průmyslu, současné hry jsou nabité kvalitní grafikou

![alt text](/Obrazky/raster.png)

## Rastrová grafika

- **Definice:** Obrázek v rastrové grafice je uložen bod po bodu. Každý bod má uloženou barvu, jas a kontrast. Z těchto bodů se skládá celkový obraz
- **Kapacitní nároky:** Při velkém rozlišení mohou být nároky na uložení vysoké. Rastrová grafika umožňuje vytvářet prakticky libovolné obrazy pomocí tisíců malých bodů
- **Upravování:** Rastrový obrázek je možné upravovat bod po bodu. Nová barva přemaže původní barvu, což umožňuje vytvářet různé efekty
- **Charakteristika:**
  - Často nazývána bitmapová grafika
  - Pracuje s obrázkem, který je složen z malých bodů (pixelů)
  - Každý bod má přesnou pozici a barvu
  - Čím více bodů v obrázku, tím je více detailnější, kvalitnější ale zároveň zabere více místa na disku
  - **Formáty:** .jpg, .gif, .tiff, .png, .BMP, .psd
- **Výhody:**
  - Opticky věrné uchování snímku, možnost provádění různých grafických efektů
  - Archivace a zpracování klasických "papírových" obrázků
- **Nevýhody:**
  - Vyšší kapacitní nároky, ztráta kvality při změnách rozlišení
- **Použití:**
    - reklama, propagace, WEB
    - hry..

## Vektorová grafika

- **Definice:** Vektorová grafika pracuje s různými tvary, body, přímkami, kružnicemi a jinými geometrickými obrazci (vektory)Obrázky dosahují maximální kvality i po vytisknutí
- **Charakteristika:**
    - Programy ukládají grafickou informaci pomocí matematického zápisu, ten definuje tvar, barvu, výplň plus další parametry křivky
    - Většina vektorových graf. systémů umožňuje použít standardní tvary jako kružnice, čtverce, atd.
    - Jeden ze dvou základních způsobů reprezentace obrazových informací v počítačové grafice. Zatímco v rastrové grafice je celý obrázek popsán pomocí hodnot jednotlivých barevných bodů (pixelů) uspořádaných do pravoúhlé mřížky, vektorový obrázek je složen ze základních geometrických útvarů jako jsou body, přímky, křivky a mnohoúhelníky
  - **Formáty:** AI, CDR, ZMF, PDF, SVG, SVF
- **Výhody:**
  - Možnost libovolného zvětšování nebo zmenšování obrázku bez ztráty kvality
  - Práce s každým objektem v obrázku odděleně
  - Výsledná paměťová náročnost obrázku je obvykle mnohem menší než u rastrové grafiky
  - Následná oprava křivek v obrázku
- **Nevýhody:**
  - Složitější pořízení obrázků oproti rastrové grafice
  - Náročnější na operační paměť a procesor při složitějších objektech
  - Neschopnost pořízení fotografie
- **Použití:**
    - tvorba fontů
    - tvorba diagramů, schémat, animací
    - počítačové modelování

## Barevná hloubka
- Jeden ze základních parametrů RGB barevného modelu
- Určuje kolik odstínů barev může mít obrázek resp. z kolika barev se skládá daný bod
- Všeobecně platí, čím větší barevná hloubka, tím kvalitnější obrázek, tím větší velikost daného obrázku

| Barevná hloubka | Označení          | Počet barev         |
|-----------------|-------------------|---------------------|
| 1 bit           | Mono Color        | 2^1 = 2             |
| 4 bit           | Low Color         | 2^4 = 16            |
| 8 bit           | High Color        | 2^8 = 256           |
| 15 bit          |                   | 2^15 = 32,768       |
| 16 bit          | True Color        | 2^16 = 65,536       |
| 24 bit          | Super True Color  | 2^24 = 16,777,216   |
| 32 bit          | Deep Color        | 2^32 = 4,294,967,296|
| 48 bit          |                   | 2^48 = 281.5 bilionů|


| B. H. | R   | G   | B   | Alfa |
|-------|-----|-----|-----|------|
| 8     | 3   | 3   | 2   | -    |
| 16    | 5   | 6   | 5   | -    |
| 18    | 6   | 6   | 6   | -    |
| 24    | 8   | 8   | 8   | -    |
| 32    | 8   | 8   | 8   | 8    |

B.H. => barevná hloubka
Alfa kanál => průhlednost

![alt text](/Obrazky/ptak.png)

## Indexovaná barva

> V případě nízkých barevných hloubek je hodnota většinou indexována v určité barevné mapě nebo paletě, používané pro zobrazení a archivaci obrázků počítačové rastrové grafiky. Barvy v paletě mohou být dány hardwarem nebo modifikovatelné. Pro modifikovatelné položky palety lze zvolit barvu z definované množiny barev.

- **1bitová barva** (2 barvy): monochromatické, často černobílé
- **2bitová barva** (4 barvy): CGA
- **4bitová barva** (16 barev): např. EGA, VGA ve vyšším rozlišení
- **8bitová barva** (256 barev): VGA v nízkém rozlišení, SVGA

> V případě nízkých barevných hloubek je hodnota většinou indexovaná v určité barevné mapě nebo paletě. Barvy použitelné v paletě mohou být dány hardwarem nebo mohou být modifikovatelné. Pro modifikovatelné položky palety lze zvolit barvu z definované množiny barev, obvykle 2^18.

**Poznámka:**
- Pomocí 8bitové indexované barvy lze realizovat paletu 3-3-2, kde se 8 bitů indexu palety rozdělí na díly 3-3-2 bity, kterým se přidělí hodnoty barev červené, zelené a modré (RGB).
- Důvodem, proč se 2 bity přidělují právě modré složce, je ten, že lidské oko je na modrou složku nejméně citlivé.
- Pomocí této palety lze realizovat pseudo-pravé (pseudo-truecolor) barvy v indexovaném obrázku.

## Průhlednost
- Vlastnost obrázku, která umožňuje zobrazit pozadí pod obrázkem
- Zařízeno díky dalším 8 bitům nazývaným alfakanál (8 bitů na pixel)
- Díky průhlednosti je např. možné, aby byl obrázek oříznut tak, že když se umístí na internetovou stránku, je vidět i pozadí této stránky pod obrázkem

## Rozlišení
- Pojem s několika významy:
  - U monitorů se rozumí rozměr obrazovky měřený počtem zobrazených bodů (pixel, px)
  - U tiskáren znamená hustota bodů při tisku, měří se v dpi (dots per inch)
  - Optimalizované rozlišení pro fotografii je 300 dpi, pro text stačí 75 dpi
  - U skenerů říká rozlišení v dpi, kolik bodů je vytvořeno ve vznikajícím souboru z obrázku dané velikosti
  - Rozlišení digitálních fotoaparátů se udává v megapixelech (Mpx), velikost fotografie je 4d x 3d, kde d je odmocnina z výrazu (rozlišení v px) / 12

## DPI
- Body na palec (dots per inch)
- Rozlišení určuje kvalitu obrázku – čím větší rozlišení, tím detailnější obrázek
- Kolik tiskových bodů jsme schopni reprezentovat na jednotce délky<br>
<br>

## Barevné modely

### Aditivní míchání barev
- Jednotlivé složky barev se sčítájí
- Obvykle se demonstruje pomocí červené, zelené a modré

![alt text](/Obrazky/barvicky.png)

### Subtraktivní míchání barev
- Barevné složky se odčítají
- Používá se azurová, pupurová a žlutá

![alt text](/Obrazky/barvicky2.png)

### RGB
- Aditivní barevný model
- Založen na přirozených vlastnostech lidského oka
- Složen ze 3 barev a jejich základních kombinací
- Využívá dataprojektory a monitory

![alt text](/Obrazky/barvicky3.png)

Co vyplývá z modelu:
- Základní barvy (RGB) leží na osách souřadného systému
- V počátku souřadného systému je barva černá
- V protilehlém vrcholu k černé je barva bílá
- Barva a její doplňková barva jsou v protilehlých vrcholech krychle
- Směrem k černému vrcholu klesá jas barev
- Směrem k bílému vrcholu klesá nasycení barev

### CMY model
- Subtraktivní barevný model
- Založen na azurové, purpurové a žluté
- Používá se pro barevný tisk
- Pro lepší zobrazení černé se model doplňuje o černou barvu => cmyk

![alt text](/Obrazky/barvicky5.png)

### HSV [HSB] model
- RGB model je vhodný pro míchání barev. HSV model více odráží vnímání barev člověkem. Definuje totiž její odstín, nasycení a jas.

- Odstín (hue) – popisuje čistou nasycenou barvu
- Sytost (saturation) – popisuje, jak moc je v barvě přimícháno bílého světla, zmenšujeme-li nasycení barvy, dostaneme až barvu bílou
- Jas (brightness) – popisuje absenci světla, tj. jak moc je barva tmavá. Zmenšujeme-li jas, dostaneme barvu černou Někdy se místo brightness používá value.

![alt text](/Obrazky/kuzel.png)

<br>
<br>

## Souborové formáty

### Rastrové
| Formát souboru | Popis | Barevná hloubka |
|----------------|-------|-----------------|
| bmp            | Bitmapa – nekomprimovaný formát souboru, každý bod nese informaci o tom, jaká je zde použitá barva. Soubory formátu bmp jsou poměrně velké. | 1, 4, 8, 24 bit/px |
| jpg (JPEG)     | Základní formát pro ukládání obrázků ve ztrátové kvalitě. Výhodou je menší velikost obrázku. Do formátu jpg se běžně ukládají fotografie pořízené digitálním fotoaparátem či mobilem. | max 24 bit/px |
| raw            | Bezztrátový formát souboru ukládající všechny informace pořízené digitálním fotoaparátem. Soubory v RAWu umožňují i velmi pokročilé úpravy fotografií. | - |
| gif            | Grafický formát určený pro rastrovou grafiku. Umožňuje zobrazení pouhých 256 barev a jednoduchou animaci. Používá bezztrátovou kompresi, proto je vhodný i pro zobrazení vektorové grafiky. | 1-8 bit/px |
| tif            | Bezztrátový formát souboru. Soubory bývají často velmi velké. Považován za zastaralý a dnes se příliš nepoužívá. Dříve byl standardem pro tisk. | 1-24 bit/px |
| png            | Grafický formát určený pro bezeztrátovou kompresi rastrové grafiky. Neumožňuje jednoduchou animaci, ale umožňuje osmi bitovou průhlednost, což umožňuje různé úrovně průhlednosti částí obrázku. **Dovoluje uložit až 48 bitovou barevnou hloubku a má samostatný alfa kanál (8 nebo 16 bit)**, který uzmožňuje uložit průhlednost a průsvitnost. | 1-48 bit/px |

### Vektorové
| Formát souboru | Popis |
|----------------|----------------------------------------------------------------------------------------------------------------------------|
| svg            | Základní otevřený formát souboru pro vektorovou grafiku. Umožňuje vkládání přímo do kódu HTML webové stránky. Jako výchozí formát jej používá například volně šiřitelný SW Inkscape. |
| dwg            | Formát souborů používaný Autocadem. Standard pro předávání technických výkresů.                                           |
| pdf            | Souborový formát vyvinutý firmou Adobe pro ukládání dokumentů nezávisle na softwaru i hardwaru, na kterém byly pořízeny. Soubor typu PDF může obsahovat text i obrázky, přičemž tento formát zajišťuje, že se libovolný dokument na všech zařízeních zobrazí stejně. |



## Komprese
- Velikost obrázků může být značná, například fotografie 10x15 cm skenovaná při rozlišení 300 dpi a 24 bitové barevné hloubce má datovou velikost asi 6,48 MB
    - (10/2,5) x 300 x (15/2,5) x 300 x (24/8) = 6,48 MB
- Běžná tapeta na plochu s rozlišením 1024x768 má datovou velikost asi 2,4 MB
- Sto fotografií z 8 Mpx fotoaparátu má datovou velikost zhruba 2,5 GB
- Pro zmenšení velikosti se používá metoda komprese
- Existují dva základní druhy komprese: bezztrátová a ztrátová
- Bezztrátová komprese opakuje části souboru, což vede k úsporám
- Ztrátová komprese zjednodušuje obraz, čímž dosahuje výrazně menší velikosti souboru

> Představme si následující rastr: "Bílá, bílá, světle šedá, bílá, bílá, bílá, další řádek, bílá, šedá,
tmavě šedá, tmavě šedá, šedá, bílá, další řádek ..." 

> Bezztrátová komprese:
"2 bílá, světle šedá, 3 bílá, další, bílá, šedá, 2 tmavě šedá, šedá, bílá, další ..."

> Ztrátová komprese: "6 bílá, další, bílá, 4 šedá, bílá, další ..." Tento velmi
zjednodušený příklad vychází z předpokladu, že oko nerozliší zanedbaný světle šedý bod v dlouhé řadě bílé

## Výpočet velikosti uloženého souboru 
> 1 B = 8 b (1 bajt rovná se 8 bitů)

> 1 kB = 1 024 B (1 kilobajt rovná se 1 024 bajtů)

### **Zadání: Kolik megabajtů (MB) v paměti počítače zabere fotografie o velikosti 15 x 10 cm nasnímaná skenerem s barevnou hloubkou 16,7 milionů barev na 100 DPI?**

### **Krok 1: převod rozměrů na palce**

jeden palec je cca 2,54 cm

15 cm je proto asi 6 palců

10 cm pak 4 palce

### **Krok 2: výpočet počtu bodů obrázku**

fotografie má na šířku 6 palců a na každý palec 100 bodů (100 DPI)

celkem má tedy na šířku 600 bodů, na výšku pak 400 bodů

celkem obsahuje 600 · 400 bodů, tj. 240 000 bodů
 

### **Krok 3: výpočet velikosti obrázku v paměti počítače**

obrázek má 240 000 bodů a každý bod „spotřebuje“ ke svému popisu 3 B 
*(tři bajty na bod → 24 bitů /tj. 16,7 mil. barev/ ÷ 8 bitů)*

obrázek proto zabere 240 000 bodů · 3 B = 720 000 B, tj. cca 703 kB, tj. cca 0,7 MB

---

> Pro uložení nekomprimovaného obrázku o velikosti 2 048 x 1 536 pixelů v barevné hloubce 24 bitů do paměti počítače je třeba (2 048 · 1 536) · (24 ÷ 8) = 9 437 184 B = 9 216 kB = 9 MB. <br>

<br>

## 3D grafika
- Odvozena z vektorové grafiky
- Umožňuje pracovat v 3D prostoru
- V 3D modelu (kvádr, krychle) se mohou vytvářet libovolné objekty trojrozměrného charakteru – objekt může grafik vylepšit texturou
- Využití: - 3D modeling
    - Filmové triky a animace
    - Reklamní propagace
    - Umění
    - Hry