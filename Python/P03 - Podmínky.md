# Podmínky (conditions)

Podmínky jsou základní logická struktura každého programovacího jazyku. Pokud tohle, proveď tamto. Občas říkáme, že tím větvíme kód - pokud je podmínka splněna jdeme jednou cestou, když je, jdeme druhou

## Základy

### `if`

Podmínky v Pythonu mají jednoduchá syntax. Nepoužíváme žádné závorky, pouze klíčové slovo `if`, poté podmínku a dvojtečku `:`. Důležité je však dodržovat odsazení, protože díky odsazení víme, které část kódu patří k podmínce

```python
a = 666
b = 51

if a > b:
    print("Číslo a je větší, než číslo b")
```

Pokud je číslo `a` větší než `b`, vypiš _Číslo a je větší, než číslo b_. Naše podmínka byla splněna, věta bude vypsána do konzole. Všimni si, že `print()` je odsazen, aby program věděl, že patří k podmínce `if a > b`

### `else`

Pokud chceme zachytit ostatní případy a provést kód v případě, že podmínka není splněna, používáme klíčové slovo `else`. Opět je potřeba dodržovat správné odsazení, `else` je na stejné úrovni jako `if`, kód který se provede v případě nesplněné podmínky je odsazen pod `else`

```python
a = 666
b = 51

if a > b:
    print("Číslo a je větší, než číslo b")
else:
    print("Číslo a není větší, než číslo b")

```

### `elif`

Podmínku můžeme rozšířit o více možností pomocí klíčového slova `elif`

```python
a = 666
b = 51

if a > b:
    print("Číslo a je větší, než číslo b")
elif a < b:
    print("Číslo a je menší, než číslo b")
else:
    print("Čísla se rovnají")

```

`elif` můžeme v případě potřeby použít vícekrát

### Porovnávací operátory

Pokud je podmínka splněna, je vyhodnocena jako `True`. Pokud ne, je vyhodnocena jako `False`.

Python podporuje obvyklé operace z matematiky:

| Operátor | Význam           | Příklad (`True`) |
| -------- | ---------------- | ---------------- |
| `==`     | rovná se         | `5 == 5`         |
| `!=`     | nerovná se       | `5 != 3`         |
| `>`      | větší než        | `7 > 2`          |
| `<`      | menší než        | `3 < 9`          |
| `>=`     | větší nebo rovno | `10 >= 10`       |
| `<=`     | menší nebo rovno | `8 <= 10`        |

**Důležité! Při porovnávání používáme dvě rovnítka `==`.** V programování jedno rovnítko přiřazuje hodnotu a dvě rovnítka porovnávají

**Porovnávání textu**

Pomocí `==` můžeme porovnávat také shodu v textu

```python
heslo = "Admin123"

if heslo == "Admin123":
    print("Zadal jsi správné heslo")
```

**Zkrácený zápis**

Pokud porováváme `bool` a chcem zjistit, jestli je proměnná pravda, nemusíme uvádět celou podmínku `if x == True:`, můžeme ji zkrát na pouhé `if x:`

```python
hlad = True

if hlad:
    print("Student má hlad a nedává pozor.")
```

## Logické operátory

Chceme-li zkombinovat více podmínek nebo otočit jejich hodnotu, můžeme používat logické operátory `not`, `and` a `or`

-   `not` – otočí hodnotu (True → False, False → True)

```python
hlad = True

if not hlad:
    print("Student nemá hlad, ale stejně nedává pozor.")
```

-   `and` – obě podmínky musí být pravdivé

```python
hlad = True
pocet_kafe = 2

if hlad and pocet_kafe < 5:
    print("Student pravděpodobně zkolabuje.")
```

-   `or` – stačí, když je pravdivá alespoň jedna podmínka

```python
den = "Sobota"

if den == "Sobota" or den == "Neděle":
    print("Je víkend, přesto se student zajisté poctivě učí a připravuje na další týden.")
```

## Vnořené podmínky

Do podmínky můžeme také vnořit další podmínku. Podmínkoception

```python

piseme_test = True
tahak = True


if piseme_test:
    if tahak:
        print("Situace zachráněna")
    else:
        print("Sakra...")
```

## `input()`

Pokud pracujeme s inputem z konzole, častokrát jej porovnáváme v rámci podmínky. Důležité! **Hodnota z `input()` je string**. Pokud chceš porovnávat pomocí matematické operace, musíš input nejdříve převést na číslo, např. pomocí funkce `int()`

```python
odehrane_minuty = int(input("Kolik jsi odehrál minut v LoL? "))

if odehrane_minuty >= 30:
    print("Oficiální doporučení je okamžitě vyhledat lékařskou pomoc.")
else:
    print("Pochvala pro tebe za to, že dbáš o svůj mentální stav.")

```

## `lower()` a `upper()`

Při porovnávání textu je výsledek `True` pouze v případě, pokud je text naprosto shodný a to včetně malých a velkých písmen

```python
print("Jarmil" == "jarmil") # False

```

Když příjímáme textový input od uživatele, tak často nastává situace, kdy uživatel zadá input trochu jinak, než bychom očekáváli. Abychom nemuseli psát podmínku pro každou variantu textového inputu...

```python
jmeno = input("Zadej své jméno ")
if jmeno == "Jarmil":
    print("To je ale skvělé jméno")
elif jmeno == "jarmil":
    print("To je ale skvělé jméno")
elif jmeno == "JARMIL":
    print("To je ale skvělé jméno")

```

... je vhodné text nejprve převést na malá písmena pomocí metody `lower()`. Metoda je funkce, kterou píšeme na konec a s tečkou - `ukazka.lower()`

```python
jmeno = input("Zadej své jméno ")

if jmeno.lower() == "jarmil":
    print("To je ale skvělé jméno")

```

Takto vyřešíme jakoukoliv kombinaci malých a velkých písmen, které může uživatel zadat

`upper()` funguje obdobně, akorát převede text na velká písmena

## `match`..`case`

Pokud máme vícero podmínek, může být přehlednější použít místo podmínek `if`..`elif`..`else` alternativu v podobě `match`..`case`. Tento zápis je vhodný k rozlišení případů podle hodnot.

U `match` uvádíme proměnnou, kterou chceme porovnávat, u `case` možnosti a situace, které mohou nastat.

`case _` má podobnou funkci, jako `else`, tzn. když něco neodpovídá žádné z možností

```python
zvire = input("Zadej zvíře: ")

match zvire:
    case "Pes":
        print("Haf")
    case "Kočka":
        print("Mňau")
    case "Ovce":
        print("Béé")
    case _:
        print("Toto zvíře neznám")

```
