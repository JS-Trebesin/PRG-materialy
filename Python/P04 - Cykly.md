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

V Pythonu zapisujeme cyklus for následujícím způsobem `for promenna in nejaky_seznam`

```python
# Vypsání čísel od 0-10
for x in range(0, 11):
  print(x)

seznam = ["Kulík", "Dulík", "Bubík"]

# Vypsání seznamu
for jmeno in seznam:
    print(jmeno)
```

-   TODO:
-   \_
-   range()
-   nested loops
