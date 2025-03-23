# Cykly (loops)

Cykly používáme, pokud chceme opakovat nějakou operaci vícekrát.
Místo toho, abychom se opakovali...

```python
print("Haf!")
print("Haf!")
print("Haf!")
print("Haf!")
print("Haf!")
```

... můžeme využít cykly.

```python
for x in range(5):
    print("Haf!")
```

V Pythonu máme dva hlavní cykly, `while` a `for`

## Cyklus `while`

Opakuje se, dokud je podmínka pravdivá.

```python
cislo = 0

while cislo < 5:
    print(cislo)
    cislo += 1
```

Cyklu while využíváme zejména v případech, kdy dopředu nevíme, kolikrát se bude operace opakovat...

```python
spravne_heslo = "Admin123"
zadane_heslo = ""

while zadane_heslo != spravne_heslo:
  print("Špatné heslo")
  zadane_heslo = input("Zadej heslo: ")
```

...v ukázce výše nevíme, na kolikátý pokus uaživatel zadá správné heslo

**nekonečný cyklus**

Pozor na vytvoření nekonečného cyklu. Pokud se podmínka nikdy nezmění, poběží cyklus navždy.

```python
cislo = 0

while cislo < 5:
    print(cislo)

# 0 0 0 0 0 0 0 ... opakování 0 do nekonečna
```

Může se hodit: klávesová zkratka `ctrl+c` použitá v konzoli zastaví běžící program

**`while True`**

Za určitých okolností chceme vytvořit nekonečný cyklus. V tom případě můžeme použít spojení `while True`

## `break`

Příkaz `break` předčasně přeruší cyklus...

```python
cislo = 0

while True:
    cislo += 1
    if cislo == 5:
        break
    print(cislo)
# 1 2 3 4
```

... na příkladu výše vidíme i ukázku použití podmínky uvnitř cyklu. Cyklus se přeruší, jakmile `cislo` nabyde hodnotu `5`

## `continue`

Pomocí `continue` můžeme přeskočit jedno kolo

```python
cislo = 0

while cislo < 5:
    cislo += 1
    if cislo == 2:
        continue
    print(cislo)

# 1 3 4 5
```

`break` a `continue` lze použít jak pro cyklus `while`, tak pro cyklus `for`

## Cyklus `for`

Druhým typem cyklu je cyklus `for`.
Tento cyklus používáme zejména v případě:

-   když vím, kolikrát se bude něco opakovat
-   když potřebuji projít tzv. _iterable_, což je objekt, který lze procházet - například list nebo slovník

V Pythonu zapisujeme cyklus `for` následujícím způsobem: `for proměnná in nějaký_seznam:`

```python
kaceri = ["Kulík", "Dulík", "Bubík"]

for kacer in kaceri:
    print(kacer)
```

### `enumerate()`

Procházíme-li listem pomocí cyklu `for`, nemáme automaticky přístup k indexu. Abychom mohli používat v cyklu také index, pomůžeme si funkcí `enumerate()`

```python
kaceri = ["Kulík", "Dulík", "Bubík"]

for i, kacer in enumerate(kaceri):
    print(f"{i+1}. {kacer}") # i+1, protože index začíná nulou

# 1. Kulík, 2. Dulík, 3. Bubík
```

### `range()`

Funkce `range()` vytvořít rozsah čísel. Její nejčastější využití je v kombinaci s cyklem `for`. Chceme-li něco zopakovat x-krát, použijeme právě tuto kombinaci

```python
for i in range(11):
  print(i)
```

Pozn. pokud proměnnou v cyklu `for` nevyužiji, je standardem napsat místo jejího názvu podtržítko `_`. Lze ukázat na příkladu cyklu s opakováním textu ze začátku této kapitoly

```python
for _ in range(5):
  print("Haf!")
```

**Syntax funkce `range()`**

```python
range(start, stop, step)
# alternativně range(od kolika, do kolika, po kolika)
```

-   start – odkud začít (výchozí 0)

-   stop – kam až (bez posledního zmíněného čísla)

-   step – o kolik se zvyšuje (výchozí 1), lze používat záporné hodnoty a tak odpočítávat

Start a stop nemusíme uvádět, v takovém případě jsou použity výchozí hodnoty, tzn. `range(5)` je stejné jako `range(0, 5, 1)`

### Odsazení

Pozor na odsazení, cokoliv je odsazené, patří do cyklu. Co je na stejné úrovni, jako `for` nebo `while` již do cyklu nepatří a nebude se opakovat

```python
for _ in range(3):
  print("Haf!")
print("Mňau!")

# Haf! Haf! Haf! Mňau!
```

## Vnořené cykly (nested loops)

Do cyklu můžeme vnořit další cyklus. Častokrát se používá pro tabulky, vzorce, kombinace nebo grid (mřížku)

```python
for x in range(5):
    for y in range(5):
        print("*", end=" ")
    print()
```

Vypíše:

```
*****
*****
*****
*****
```

Další příklad vnořených cyklů

```python
barvy = ["červená", "modrá", "zelená"]
tvary = ["čtverec", "kolečko", "trojúhelník"]

for barva in barvy:
    for tvar in tvary:
        print(barva)

# Tento kód vypíše kombinaci všech barev se všemi tvary

```
