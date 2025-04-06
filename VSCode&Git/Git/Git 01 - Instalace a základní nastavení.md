# Instalace Git

## 1. Stáhněte Git 
- odkaz [zde](https://git-scm.com/download/win) - stahujte verzi 64-bit Git for Windows Setup
## 2. Nainstalujte stáhnutý Git

- klikáme na Next, Next, než narazíme na tabulku Choosing the default editor used by Git


![image](https://user-images.githubusercontent.com/84028625/284706440-f75f5c9f-9429-4541-9ade-c890a1aaf952.png)
- zde zvolíme VScode nebo Notepad (defaultní nastavení VIM není příjemný editor)

- a hned v následující části

![image](https://user-images.githubusercontent.com/84028625/284706720-db1e576a-bc76-4f77-b553-b0ea3b22f6a1.png)

- zvolíme druhou možnost Override the default branch name for new repositories (při git init se bude jmenovat hlavní větev main a nemusíme jí tak přejmenovat z master na main)

- Zbylé nastavení nechte defaultně nastavené a jen klikejte na Next, Next, ... a Install

## 3. Otevřete VScode a ve VScode otevřete terminal

- Terminal -> New Terminal, popř. jednoduše ctrl + ;

*Pozn. defaultní terminal je Windows Powershell (příkazy jako v DOS, git příkazy jsou ale všude stejné)*
*Alternativně si v nastavení VScode můžete zvolit Git-bash (linuxový terminál, linuxové příkazy) => Settings (ctrl + ,) -> do vyhledávacího pole "windows terminal integrated" -> zvolit Git bash*

![image](https://user-images.githubusercontent.com/84028625/284709943-141fb205-b4f3-4779-ae58-3eaf95dcb4fc.png)

## 4. Základní nastavení

[příkazy](https://gist.github.com/JS-Trebesin/40aa934b8f30641345c17d3b67744883)

Toto nastavení je potřeba provést pouze jednou
- `git config --global user.name "jméno"`
- `git config --global user.email "email@trebesin.cz”`

## 5a. Práce s existujícím repozitářem

Pokud pracuji s existujícím repozitářem, nejprve chci naklonovat tento repozitář do svého počítače

- na Githubu kliněte na Code -> HTTPS -> zkopírovat odkaz

![image](https://user-images.githubusercontent.com/84028625/284712229-f573f7b8-4acf-4521-9f36-db0aa6e222cb.png)

- v terminálu navigujeme do složky, kam chci, aby se mi námi zvolený kód uložil (pomocí cd název_složky atd.)
- použijeme příkaz `git clone zkopírovaný_odkaz
- máme vytvořený repozitář a mohu jej upravovat, změny uložit pomocí příkazu `git commit -am "informace o změnách"` 
- a poslat na Github pomocí `git push origin main`

## 5b. Nemám existující Github repozitář

- v terminálu navigujeme do složky, kam chci vytvořit repozitář
- použijeme příkaz `git init`
- pokud se naše branch jmenuje *master* (můžeme ověřit pomocí `git status`, popř. git-bash ukazuje název přímo v konzoli), přejmenujeme ji na *main* pomocí příkazu `git branch -m master main` (protože Github používá main)
- vytvoříme nový repozitář příkazem `git init`
Připojení k Githubu
- vytvoříme nový prázdný repozitář na Githubu
- zkopríujeme cestu (viz 5a), cestu tentokrát zadám `git remote add origin zkopírovaný_odkaz`
- `git add .` (pokud mám nové soubory, jinak můžeme sloučit git add a git commit do git commit -am)
- `git commit -m "informace o změnách"`
- `git push origin main`

## 6. Stáhnutí změn z Githubu (aktualizace repozitáře)

Pokud jsme něco upravili na Githubu přes web nebo jsme pushnuli změnu na jiném počítači a na Githubu je nyní aktuálnější kód, než máme lokálně na PC, je potřeba nejprve stáhnout změny do našeho počítače

- `git pull origin main`
- git pull změny stáhne a rovnou sloučí s naším lokálním kódem (přepíše jej) - pokud se chci změny pouze stáhnout, abych je mohl porovnat se svým lokálním a nechci svůj kód přepsat, mohu použít `git fetch origin main`

## 7. Práce s Gitem

- ulož změny `git commit -am "informace o změnách"` 
- pošli na Github `git push origin main`

*Pokud vytvoříme nový soubor je potřeba nejprve použít `git add název_souboru` nebo `git add .` (tečka znamená vše)*