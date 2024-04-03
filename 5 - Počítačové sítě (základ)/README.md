# 05 - Počítačové sítě, hierarchie, topologie, komunikace v síti – referenční modely a standardy

## Základní pojmy
•	Symetrický vs asymetrický přenos dat: Při symetrickém přenosu dat je stejná rychlost upload/download, naopak při asymetrickém se liší.
•	Redundance: Nadbytečnost (označení situace, kdy je použito více prvků, než je nutné).
•	P2P (Peer-to-Peer): Označení typu počítačových sítí, kde komunikují spolu přímo, rovnocenně jednotliví klienti.
•	Topologie sítí: Zabývá se zapojením různých prvků do počítačové sítě, zachycením jejich skutečné a logické podoby. Fyzická topologie zahrnuje rozdělení prvků do místností, zatímco logická topologie zahrnuje rozdělení prvků do sítí, do VLAN atd.
•	ISP (Internet Service Provider): Poskytovatel připojení k internetu a služeb s tím spojených.
•	Server: Označení pro počítač, který poskytuje služby.

## Klient: 
•	Označení pro počítač, který využívá služby.
•	Tlustý klient (Obsáhlý klient): Provádí všechny operace sám, nemusí spoléhat na server. Nejčastěji v podobě osobního počítače, laptopu.
•	Tenký klient: Využívá zdrojů hlavně z hostitelského počítače, víceméně jen zobrazuje grafická data poskytované aplikačním serverem. Výhodou je ovladatelnost a pružnost.
•	Hybridní klient: Směs modelů klienta. Sám zpracovává operace, ale spoléhá i na server.
## Služba: Realizuje spojení a výměnu informací mezi počítači, komunikuje podle určitých pravidel, za účelem sdílení společných zdrojů nebo výměny zpráv.
## Agregace: Spojování, seskupování, shlukování (udává se x: y–x → minimální podíl; y → maximální podíl z rychlosti).
## Bezstavovost: Vztahuje se k implementaci protokolů, kde protokol je jednoduché implementovat a představuje malou zátěž pro server. Jednotlivé požadavky na server položené spolu nejsou nijak svázány, server neví, zda jsou od téhož uživatele, zda spolu nějak souvisejí.
## Síťová karta: Hardware k vzájemné komunikaci v PC síti.
## Firewall: Kontrola a omezení komunikace počítače po síti.


## Počítačové sítě: Souhrnné označení pro technické prostředky (např. PC, switch, router, kabely), které realizují spojení a výměnu informací mezi počítači, umožňující komunikaci podle určitých pravidel – sdílení prostředků, výpočetního výkonu, výměny zpráv.
### Součásti sítě:
•	Síťové uzly: Každý uzel musí mít svoji MAC adresu nebo adresu řízení datového spoje (např. IP).
•	Výkonná zařízení (servery, stanice):
•	Propojovací zařízení (aktivní, pasivní):
## Síťová propojení:
•	Drátově (fyzicky):
•	Metalický kabel
•	Optický kabel
•	Bezdrátově:
•	Rádiové vlny
•	Satelitní/optický přenos

## Síťové služby (příklady):

•	Webové
•	Poštovní
•	Tiskové
•	Souborové
•	Pro vzdálenou práci s počítačem
•	Servisní

## Síťový software:

•	Prohlížeče internetových stránek
•	Poštovní programy
•	Chat
•	Torrent klienty
•	Firewall
•	Vzdálená plocha
## Zabezpečení sítě:
•	Skrytí SSID
•	Firewall
•	Filtrování MAC adres
•	Statické IP adresy
•	Šifrování komunikace pomocí min. WPA2 nebo WPA3
•	Rozdělení sítě na VLANy

## Sledované vlastnosti sítě:

•	Způsob přenosu signálu
•	Bezpečnost
•	Instalační požadavky
•	Šířka pásma
•	Útlum
•	Vzájemné ovlivňování a rušení (EMI)
•	Aktivní síťové prvky:
•	Cena

## Typy vzájemných vztahů stanic v síti:
Client-Server: Odděluje klienta a server, které komunikují přes počítačovou síť. Při vyšším počtu klientů klesá průměrná přenosová rychlost. Nejčastějšími klienty jsou dnes webové prohlížeče (Chrome, Brave, Firefox). Klient (aktivní, posílá žádosti serveru, čeká a dostává odpovědi) X server (pasivní, naslouchá síti/reaguje na žádosti, při přijetí požadavku jej obslouží).
P2P: Například sdílení složek v místnosti se vzájemně propojenými počítači. Patří sem také technologie jako Torrent a blockchain. Při vyšším počtu stanic roste přenosová kapacita.
 
Hierarchický model sítě: Propojení zařízení v menší nebo střední firmě. Zajišťuje přehledný chod sítě, rychlejší opravy a snadnější správu. Dovoluje efektivně přidělovat adresy a lehce je sumarizovat, což zpřehledňuje toky dat. Spočívá v rozdělení sítě na samostatné vrstvy.
•	Přístupová vrstva: Obsahuje koncová zařízení (PC, tiskárny, IP telefony) a poskytuje přístup do zbytku sítě. Hlavním účelem je připojit koncová zařízení k síti a kontrolovat, která zařízení mají povoleno v síti komunikovat.
•	Distribuční vrstva: Agreguje datový provoz a kontroluje síťový provoz lokální sítě. Zahrnuje obvykle velmi výkonná zařízení s vysokou dostupností a redundancí k zaručení bezporuchovosti.
•	Jádro: Představuje vysokorychlostní páteř sítě, která musí být velmi spolehlivá a připojena k internetu často více linkami pro rychlý přenos velkého objemu dat.


##Základní topologie sítě:
•	Sběrnicová topologie (BUS): Nejjednodušší způsob zapojení počítačů do sítě, kde se všechny stanice propojují jediným kabelem (hlavní kabel/segment/páteř), který spojuje všechny PC.
•	Kruhová topologie (RING): Počítače jsou propojeny kabelem do jediného okruhu, kde neexistují zakončené konce. Signál putuje po smyčce v jednom směru a prochází všemi PC.
•	Hvězdicová topologie (STAR): Každý počítač je připojený pomocí kabelu k centrálnímu prvku. Mezi dvěma stanicemi existuje vždy jen jedna cesta.
•	Stromová topologie (TREE): Vychází z hvězdicové topologie spojením aktivních síťových prvků do stromové struktury.
•	Smíšená topologie: Spojuje více topologií do jednoho funkčního celku, například kombinaci TREE a STAR.
 
## Logické topologie sítě:
•	Token Ring: Používá token, kterým se řídí přenos dat. Kdo má token, může komunikovat, a když token nepotřebuje, posílá ho dál. V síti musí být řídící prvek, který může být označován jako "klasická máma".
•	Ethernet: Dva prvky sítě komunikují spolu, ale pokud dojde k chybě (například rušení jiným prvkem), je komunikace na dobu přerušena, dokud se neuvolní pásmo. Inspirace pro názvy pochází z literárních postav jako Vinnetou, Old Shatterhand a ukecaná Ribana.
## Síťové modely:
Souhrn pravidel a úmluv standardizujících prvky sítě, jako jsou:
•	Standardy pro podobu a tvorbu kabelů a konektorů.
•	Standardy pro stanovení napěťové úrovně logické 0 a logické 1.
•	Protokoly pro opravu chyb, zasílání požadavků a příjem souborů ze serveru, přenos dat mezi klientem a serverem a pro internetové telefony. Příkladem jsou například modely ISO/OSI (spíše teoretický) a TCP/IP (praktický).
 

## ISO/OSI a TCP/IP model

 
 
