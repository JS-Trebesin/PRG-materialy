# Iterables - lists, tuples (a lehce taky sets)

Lists (seznamy), tuples a sets jsou datové typy, do kterých lze uložit více hodnot, informací. Poté jimi můžeme procháet položku po položce, tzn. jsou iterovatelné.

Mezi iterables patří ale také string (což je vlastně seznam jednotlivých znaků) a dictionary (slovník). O dictionary více v navazující [kapitole 7](P06%20-%20List%20a%20tuple.md)

### `for`

Pro procházení jednotlivými položkami iterables používáme cyklus for

```python
for promenna in nazev_iterable:
    print(promenna)
```

```python

kaceri = ["Kulík", "Dulík", "Bubík"]

for kacer in kaceri:
    print(promenna)
# Kulík, Dulík, Bubík

# nebo pro string ↓

for pismeno in "Czenglish":
    print(pismeno)
# C z e n g l i s h
```


## `list` - List (seznam)

List je seznam hodnot. Může obsahovat libovolné datové typy - například té dictionary nebo další list (seznamu v seznamu). Lze jej měnit
s

```python
zmateny_den = ["Budík ⏰", True, 8.25, "😱", "🏃", "📅", "Sobota", "🤦‍♂️", "🛌💤", True]
seznam_studentu = ["Jarmil", "Anděla", "Hvězďon", "Višeslava"]

```

## Přístup k hodnotám

Každá položka má svůj **index**, tj. pořadní číslo - počítače počítají od 0, takže první položka má index 0, druhá index 1, atd.


Pro přístup k jednotlivým položkám používáme `nazev_listu[index]`

```python
print(seznam_studentu[1]) # Anděla
```

Pokud chci hodnotu změnit, použiji stejný syntax a přiřadím novou hodnotu

```python
seznam_studentu[2] = "Kvído" # [["Jarmil", "Anděla", "Kvído", "Višeslava"]
```

### Přidání a mazání

Pro přidání do listu používáme funkci `append()`.
```python
seznam_studentu.append("Ctirad") # ["Jarmil", "Anděla", "Kvído", "Višeslava", "Ctirad"]
```

Více k listům na [W3 schools](https://www.w3schools.com/python/python_lists_methods.asp) nebo na [Nauč se Python](https://naucse.python.cz/lessons/beginners/list/)

### `tuple` - Tuple (neměnitelný seznam)

Podobný listu, ale používáme obyčejné závorky `()`. **Nelze** jej měnit (nelze přidávat, mazat nebo upravovat položky)

Více o tuplech v kapitole [List a tuple]()

```python
souradnice = (50.1294, 16.3103)
barva = (255, 0, 0)
```
