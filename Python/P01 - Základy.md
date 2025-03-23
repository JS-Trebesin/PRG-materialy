# Základy

## Trocha teorie

Python je programovací jazyk, který vydal v roce 1991 Guido van Rossum. Název je inspirovaný britskou komediální skupinou Monty Python.

Python se vyznačuje snadným syntaxem jazyka. Jeho výhodou je jeho popularita - využívá se v mnoha oblastech, příklady využí jsou: datová analýza, automatizace, AI, na serverech, ve vědě nebo třeba softwarovém testování
Díky jeho rozšířenosti k němu existuje spousta dokumentace, návodů, tutoriálů a knihoven.
Knihovny jsou předpřipravený kód (funkce, classy, atd.), které můžete snadno vložit do svého kódu. Spousta problému v programování již byla vyřešena a vy můžete snadno využít cizí řešení a nemusíte psát často používané funkce od začátku.

Python je interpretovaný jazyk, do strojového kódu se překládá řádek po řádku. Z čeho vyplývá i jeho hlavní nevýhoda - kód v Pythonu neběží tak rychle, jako v jiných jazycích (C, C#, Java, atd.). To je důležité zejéma pro náročné programy, jako jsou například komplexní 3D hry.

## Instalace

Abyste mohli Python začít používat ve Windows nebo na Mac, musíte jej nejdřív stáhnout na internetu a nainstalovat do počítače. Doporučuji nepoužívat Windows store a stáhnout Python z [oficiálních stránek](https://www.python.org/downloads/). Ve VS code nezapomeňte přidat extension Python.

**Důležité! Při instalaci zaškrněte**

-   **[x] Add Python to PATH**

## Nastavení extension pro Python

**Důležité!** Abychom se vyvarovali budoucím chybám, je potřeba změnit nastavení Python extensio ve VS code

Proklikejte se do nastavení přes _File -> Preferences -> Settings_ (nebo klávesovou zkrátkou _ctrl + ,_) a do vyhledávacího pole napište _python terminal execute_ a zaškrtněte položku **_Python > Terminal: Execute In File Dir_**

## Spuštění souboru

V terminálu ve VS code zadejte správnou cestu k souboru (může se hodit: pravým klik na soubor a Open in Integrated Terminal) a napište příkaz: `python nazevsouboru.py`, alternativně stačí `py nazevsouboru.py`

V Linuxu nebo na Macu je potřeba napsat `python3 nazevsouboru.py`

Pokud jste správně nastavili extension (viz odstavec výš), můžete spustit souboru pomocí symbolu play <| v pravém horním rohu

## Odsazování

V Pythonu je nezbytné správně odsazovat. Kdežto v Javascriptu je odsazování dobrovolné a jeho hlavní důvod je čitelnost a zachování dobrého mentálního stavu vašeho učitele, **v Pythonu je odsazování povinné (!)** - Python totiž nepoužívá složené závorky pro označení, kde začíná a končí kód. Místo toho používá právě odsazení

## snake_case

V Pythonu je standard používat tzv. snake_case po pojmenovávání víceslovných proměnných.

```python
krestni_jmeno = "Jarmil"
```

## Komentáře

Komentáře v Pythonu začínáme pomocí křížku ("hashtagu") `#`

```python
# Toto je komentář
```

## Vytváření proměnných

Python nepoužívá žádné klíčové slovo jako `var`, `let` nebo `const`, pokud chci vytvořit proměnnou, stačí napsat její jméno a =

```python
text = "What  is the answer to the ultimate question of life, the universe, and everything"
cislo = 42
```

Chceme-li zvýšit hodnoty proměnné o 1, používáme syntax `cislo += 1`

### Konstanta

Pokud vytváříme konstantu, tj. proměnnou, u které neočekáváme, že ji později změníme, je standardem používat velká písmena

```python
HVEZDA = "Polárka"
```

Pozor, přesto lze tuto proměnnou v Pythonu přepsat. Nicméně to, že je psaná v caps lockem by nás mělo upozornit, že bychom to neměli dělat

### Pojmenování proměnných

Pokud používáš češtinu pro názvy proměnných, vyvaruj se používání diakritiky. V některých případech, ačkoliv jsou velmi vzácné, to může způsobovat chyby. Standardem je používat buď anglické názvy proměnných nebo české bez diakritiky. Do hodnoty v textu, do uvozovek, již samozřejmě diakritiku použít můžeš

```python
cislo = 42
jmeno = "Kvído"
```

## Vypisování do konzole

Pro vypsání textu/čísla/proměnné do konzole používáme v Pythonu funkci `print()`

```python
# Vypíše ahoj
print("Ahoj")
```

## Přijímání inputu z konzole

Příkaz `input()` přijímá uživatelův input v příkazovém řádku (konzoli). Input přijímá vždy `string`, který na `int` můžeme změnit pomocí funkce `int()`

```python
# Přijme input z příkazového řádku
uziv_input = input()

# Vypíše uživatelův input
print(uziv_input)

```

## Základní matematické operace

```python
a = 10 + 5    # sčítání
b = 10 / 3    # dělení
c = 10 // 3   # celočíselné dělení
d = 10 % 3    # zbytek po dělení
e = 2 ** 3    # mocnina
```

Pozn. zbytek po dělení, tzv. _modulo_ (`%`), se používá pro zjištění, jestli je číslo sudé nebo liché. Pokud aneb pokud je zbytek po dělení dvěma nula (x % 2 == 0), tak víme, že číslo je sudé.

```python
cislo = int(input("Zadej číslo: "))
if cislo % 2 == 0:
    print("Číslo je sudé")
```
