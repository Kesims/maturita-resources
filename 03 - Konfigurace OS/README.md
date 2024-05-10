# 3 - Konfigurace a základní správa OS (Linux)
## Pojmy
- **Archivace** - Zabývá se ukládáním a organizováním dat či informací pro dlouhodobé uchování. Cílem archivace je udržovat data dostupná, ale mimo běžný provoz systému. Archivace často zahrnuje selektivní sběr dat, třídění a ukládání do archivních formátů (jako jsou ZIP, TAR, nebo speciální formáty pro archivaci). Hlavním cílem je uchování dat pro budoucí použití nebo referenci, přičemž se minimalizuje prostor a zároveň se zajišťuje jejich integrita.
- **Komprimace** - Nebo také **komprese**, se zaměřuje na redukci velikosti souborů nebo dat, často za účelem úspory místa na disku nebo rychlejšího přenosu přes síť. Existují různé metody komprese, jako je bezeztrátová komprese (která snižuje velikost souboru bez ztráty dat) a ztrátová komprese (která umožňuje větší kompresi, ale může vést ke ztrátě některých informací). Příklady algoritmů pro kompresi zahrnují ZIP, RAR, gzip (pro bezpečné komprese) nebo JPEG, MP3 (pro kompresi s určitou ztrátou kvality).
> Oba tyto procesy mohou být v informatice využívány samostatně, ale často se kombinují. Archivace může využívat kompresi pro snížení velikosti archivovaných dat a usnadnění jejich správy.
- **Pevný odkaz** - Je alternativním jménem pro konkrétní soubor nebo adresář v souborovém systému. Vytvoření pevného odkazu vytváří další jméno, které ukazuje přímo na stejná data (inode) jako původní soubor nebo adresář. Tento typ odkazu zachovává spojení s původním souborem, takže i když smažete původní soubor, data zůstanou dostupná prostřednictvím pevného odkazu. Každý soubor nebo adresář může mít více pevných odkazů.
- **Symbolický odkaz** - Je zvláštní typ souboru, který obsahuje cestu nebo relativní odkaz k jinému souboru nebo adresáři. Na rozdíl od pevného odkazu, který ukazuje přímo na data, symbolický odkaz pouze odkazuje na cíl prostřednictvím jeho cesty. Pokud je cílový soubor nebo adresář smazán, symbolický odkaz zůstane, ale bude neplatný, protože cíl již neexistuje. Výhodou symbolického odkazu (na rozdíl od pevného odkazu) je zejména jeho univerzálnost. Může překročit hranice souborového systému, může ukazovat i na adresář, nezpůsobuje problémy při aktualizaci.
> Pevné odkazy jsou spjaty s konkrétními daty, zatímco symbolické odkazy slouží k vytvoření odkazu na cíl pomocí cesty nebo relativního odkazu.

## Soubory passwd a shadow a jejich význam při správě OS
### /etc/passwd 
Soubor obsahuje informace o uživatelích, kteří mají přístup do systému. Každý řádek souboru obsahuje informace o jednom uživateli. Jednotlivé položky jsou odděleny dvojtečkou. První položka je uživatelské jméno, druhá položka je zašifrované heslo, třetí položka je identifikační číslo uživatele (UID), čtvrtá položka je identifikační číslo skupiny (GID), pátá položka je komentář, šestá položka je cesta k domovskému adresáři uživatele a poslední položka je cesta k uživatelskému shellu.
> Příklad řádku souboru passwd:
> ```root:x:0:0:root:/root:/bin/ash```
> - root - uživatelské jméno
> - x - zašifrované heslo
> - 0 - UID
> - 0 - GID
> - root - komentář
> - /root - cesta k domovskému adresáři uživatele
> - /bin/ash - cesta k uživatelskému shellu

### /etc/shadow
Soubor obsahuje zašifrovaná hesla uživatelů. Každý řádek souboru obsahuje informace o jednom uživateli. Jednotlivé položky jsou odděleny dvojtečkou. První položka je uživatelské jméno, druhá položka je zašifrované heslo, třetí položka je datum poslední změny hesla, čtvrtá položka je minimální počet dní, po které je možné heslo změnit, pátá položka je maximální počet dní, po které je možné heslo změnit, šestá položka je počet dní před upozorněním na změnu hesla, sedmá položka je počet dní po vypršení hesla, kdy je účet deaktivován, osmá položka je datum, kdy je účet deaktivován, devátá položka je rezervovaná pro budoucí použití.
> Příklad řádku souboru shadow:
> ```root:$1$5QJ8X1Q2$0Z1Z1Z1Z1Z1Z1Z1Z1Z1Z1:0:0:99999:7:::```
> - root - uživatelské jméno
> - $1$5QJ8X1Q2$0Z1Z1Z1Z1Z1Z1Z1Z1Z1Z1 - zašifrované heslo
> - 0 - datum poslední změny hesla
> - 0 - minimální počet dní, po které je možné heslo změnit
> - 99999 - maximální počet dní, po které je možné heslo změnit
> - 7 - počet dní před upozorněním na změnu hesla
> - \- - počet dní po vypršení hesla, kdy je účet deaktivován
> - \- - datum, kdy je účet deaktivován

## Příkaz `ls`, jeho parametry a význam výpisu
Příkaz `ls` slouží k výpisu obsahu adresáře. Jeho parametry mohou měnit význam výpisu. Některé z parametrů jsou:
- `-a` - zobrazí i skryté soubory
- `-l` - zobrazí detailní informace o souborech
- `-h` - zobrazí velikost souborů v lidsky čitelné formě
- `-R` - zobrazí obsah adresáře rekurzivně

... a další

Kromě seznamu souborů a adresářů může příkaz `ls` zobrazit i další informace o souboru, jako je například oprávnění, vlastník, velikost, datum poslední úpravy, atd.
> Zde je příklad výpisu příkazu `ls -l`:
> ```-rwxr-xr-x 1 root root   68 Dec 14  2022 script.sh```
> - `-rwxr-xr-x` - oprávnění
> - `1` - počet odkazů
> - `root` - vlastník
> - `root` - skupina
> - `68` - velikost v bajtech
> - `Dec 14  2022` - datum poslední úpravy
> - `script.sh` - název souboru

> Význam jednotlivých znaků v oprávnění v příkladu `-rwxr-xr-x`:
> - `-` - v tomto případě se jedná o soubor (`d` - adresář, `l` - symbolický odkaz)
> - `rwx` - oprávnění vlastníka (vlastník má právo číst, zapisovat a spouštět soubor)
> - `r-x` - oprávnění skupiny (skupina má právo číst a spouštět soubor)
> - `r-x` - oprávnění ostatních (ostatní mají právo číst a spouštět soubor)

## Správa uživatelů a skupin
### Přidání uživatele - příkaz `useradd`
Příkaz `useradd` slouží k přidání uživatele. Jeho parametry mohou měnit význam příkazu. Některé z parametrů jsou:
- `-m` - vytvoří domovský adresář uživatele
- `-s` - nastaví uživatelský shell
- `-G` - přidá uživatele do skupiny
- `-p` - nastaví heslo uživatele

... a další

> Příklad příkazu `useradd -m -s /bin/bash -G sudo -p password username`:
> - `-m` - vytvoří domovský adresář uživatele
> - `-s /bin/bash` - nastaví uživatelský shell na `/bin/bash`
> - `-G sudo` - přidá uživatele do skupiny `sudo`
> - `-p password` - nastaví heslo uživatele na `password`
> - `username` - uživatelské jméno
> 
> Poznámka: tento uživatel pojmenovaný `username` bude v základu také členem skupiny `username`. Parametr `-G` přidá uživatele do další skupiny, ale neodebere ho ze skupiny, do které je přidán v základu. Výchozí skupina uživatele je pojmenována stejně jako uživatel.

### Přidání skupiny - příkaz `groupadd`
Příkaz `groupadd` slouží k přidání skupiny. Některé z parametrů jsou:
- `-g` - nastaví GID skupiny
- `-r` - vytvoří systémovou skupinu

... a další

> Příklad příkazu `groupadd -g 1000 groupname`:
> - `-g 1000` - nastaví GID skupiny na `1000`
> - `groupname` - název skupiny

### Modifikace uživatele, přidání uživatele do skupiny - příkaz `usermod`
Příkaz `usermod` slouží k modifikaci uživatele. Některé z parametrů jsou:
- `-aG` - přidá uživatele do skupiny
- `-l` - změní uživatelské jméno
- `-L` - zablokuje uživatele
- `-U` - odblokuje uživatele
- `-p` - nastaví heslo uživatele

... a další

> Příklad příkazu `usermod -aG sudo -p password username`:
> - `-aG sudo` - přidá uživatele do skupiny `sudo`
> - `-p password` - nastaví heslo uživatele na `password`
> - `username` - uživatelské jméno

### Modifikace skupiny - příkaz `groupmod`
Příkaz `groupmod` slouží k modifikaci skupiny. Některé z parametrů jsou:
- `-g` - změní GID skupiny
- `-n` - změní název skupiny

... a další

> Příklad příkazu `groupmod -g 1000 groupname`:
> - `-g 1000` - změní GID skupiny na `1000`
> - `groupname` - název skupiny

### Smazání uživatele - příkaz `userdel`
Příkaz `userdel` slouží k smazání uživatele. Některé z parametrů jsou:
- `-r` - smaže i domovský adresář uživatele
- `-f` - smaže uživatele i v případě, že je přihlášen

... a další

> Příklad příkazu `userdel -r -f username`:
> - `-r` - smaže i domovský adresář uživatele
> - `-f` - smaže uživatele i v případě, že je přihlášen
> - `username` - uživatelské jméno


### Smazání skupiny - příkaz `groupdel`
Příkaz `groupdel` slouží k smazání skupiny. Některé z parametrů jsou:
- `-f` - smaže skupinu i v případě, že je používána

... a další

> Příklad příkazu `groupdel -f groupname`:
> - `-f` - smaže skupinu i v případě, že je používána
> - `groupname` - název skupiny

## Příkaz chmod
Příkaz `chmod` slouží k změně oprávnění pro daný soubor | adresář

> `chmod WhoWhatWhich file | directory`
> - Who - představuje identity: u,g,o,a (user, group, other, all)
> - What - představuje akce: +, -, = (add, remove, set exact)
> - Which - představuje úrovně přístupu: r, w, x (read, write, execute)

Ukázky:
> `chmod ug+rw test.txt` <- symbolický odkaz

> `chmod 650 test.txt` <- numerický odkaz
> - `6` - user
> - `5` - group
> - `0` - others

Jak určit čísla?
> - `read` => 4
> - `write` => 2
> - `execute` => 1

Tudíž `rw-` bude  4+2 = 6


### Sticky bit (relativně navíc, ale pan Horálek říkal, že nás nevyhodí od zkoušky, když to zmíníme)
Toto oprávnění nemá vliv na jednotlivé soubory. Na úrovni adresáře však omezuje mazání souborů. Pouze vlastník (a root) souboru může soubor v rámci daného adresáře odstranit

> - `drwxrwxrwt. 15 root root 4096 Sep 22 15:28 /tmp/`

## Principy tvorby skriptů v shellu
Skripty v shellu jsou psány v textovém editoru a uloženy s příponou `.sh`. Skript je poté spuštěn v terminálu příkazem `sh nazev_skriptu.sh`. Skript může být spuštěn i přímo, pokud je nastaveno oprávnění pro spuštění. V tomto případě je skript spuštěn příkazem `./nazev_skriptu.sh`. Skript může být spuštěn i v jiném skriptu.

### Proměnné
Proměnné v shellu se deklarují bez typu. Proměnné mohou obsahovat pouze písmena, číslice a podtržítka. Proměnné se deklarují pomocí `nazev_promenne=hodnota` a volají se pomocí `$nazev_promenne`. Proměnné mohou být i globální, pokud jsou deklarovány mimo skript.

### Podmínky
Podmínky v shellu se zapisují pomocí `if` a `then`. Podmínky mohou být i vnořené. Podmínky se ukončují pomocí `fi`.

### Cykly
Cykly v shellu se zapisují pomocí `for` a `do`. Cykly se ukončují pomocí `done`.

### Funkce
Funkce v shellu se zapisují pomocí `function nazev_funkce() { prikazy }`. Funkce se volají pomocí `nazev_funkce`.

### Vstup a výstup
Vstup a výstup v shellu se zapisují pomocí `echo` a `read`. Vstup a výstup mohou být i vnořené.

### Příklad skriptu
```bash
#!/bin/bash

# Funkce pro výpis zprávy
vypis_zpravu() {
    echo "Toto je zpráva z funkce: $1"
}

# Načtení vstupu od uživatele
echo "Zadej své jméno:"
read jmeno

# Výpis uvítací zprávy
echo "Ahoj, $jmeno! Vítej ve skriptu."

# Použití podmínky pro ověření věku
echo "Kolik je ti let?"
read vek

if [ "$vek" -ge 18 ]; then
    echo "Jsi dospělý."
else
    echo "Jsi nezletilý."
fi

# Cyklus pro výpis čísel 1 až 5
echo "Vypíšeme čísla od 1 do 5:"
for i in {1..5}; do
    echo "$i"
done

# Volání funkce pro výpis zprávy
vypis_zpravu "$jmeno"

# Ukončení skriptu s návratovým kódem 0
exit 0
```


