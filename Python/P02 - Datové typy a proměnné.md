# Proměnné a datové typy

### Pro připomenutí: vytváření proměnných

Python nepoužívá žádné klíčové slovo jako `var`, `let` nebo `const`, pokud chci vytvořit proměnnou, stačí napsat její jméno a =

```python
text = "What  is the answer to the ultimate question of life, the universe, and everything"
cislo = 42
```

Chceme-li zvýšit hodnoty proměnné o 1, používáme syntax `cislo += 1`

**Konstanta**

Pokud vytváříme konstantu, tj. proměnnou, u které neočekáváme, že ji později změníme, je standardem používat velká písmena

```python
HVEZDA = "Polárka"
```

Pozor, přesto lze tuto proměnnou v Pythonu přepsat. Nicméně to, že je psaná v caps lockem by nás mělo upozornit, že bychom to neměli dělat

**Pojmenování proměnných**

Pokud používáš češtinu pro názvy proměnných, vyvaruj se používání diakritiky. V některých případech, ačkoliv jsou velmi vzácné, to může způsobovat chyby. Standardem je používat buď anglické názvy proměnných nebo české bez diakritiky. Do hodnoty v textu, do uvozovek, již samozřejmě diakritiku použít můžeš

```python
cislo = 42
jmeno = "Kvído"
```

## Datové typy

V Pythonu, podobně jako v ostatních programovacích jazycích, můžeme pod proměnné ukrýt různé hodnoty typů:

| Datový typ   | Popis                                        | Příklad                          |
| ------------ | -------------------------------------------- | -------------------------------- |
| `str`        | String (text)                                | `"Ahoj"`, `"Python"`             |
| `int`        | Integer (celé číslo)                         | `42`, `-10`                      |
| `float`      | Float (desetinné číslo)                      | `3.14`, `-0.5`                   |
| `bool`       | Boolean (logická hodnota)                    | `True`, `False`                  |
| `list`       | List (seznam aneb array)                     | `[1, 2, 3]`                      |
| `tuple`      | Tuple (neměnitelný seznam)                   | `(1, 2, 3)`                      |
| `dict`       | Dictionary (slovník)                         | `{"jméno": "Anděla", "věk": 30}` |
| `NoneType`   | None (neobsahuje žádnou hodnotu)             | `None`                           |
| _další typy_ | _(např. set, bytes, bytearray, range, atd.)_ |                                  |

### `str` String (text)

Text, v češtině někdy označován jako textový _řetězec_, který může obsahovat znaky, slova, věty nebo třeba emoji.
Zapisujeme jej do uvozovek `"` nebo `'`. Záleží na programátorovi, jaké uvozovky zvolí, ale měl by být ve své volbě konzistentní

```python
zprava = "Dneska je pátek! 🎉"
zjisteni = "V sobotu není škola 😢"
```

**`f-string`**

V programování častokrát narazíme na případ, kdy chceme do stringu dosadit údaj z existující proměné. Toho můžeme dosáhnout pomocí spojování stringu, tzv. concatenation

```python
pocet_loupezniku = 40
sdeleni = "Ahoj, jmenuji se Alibaba a mám " + pocet_loupezniku + " kamarádů."
```

Tento způsob může být protivný. Musíme si dávat pozor na mezery a při použití většího množství proměnných může být spojování pomocí `+` chaotické

```python
pocet_loupezniku = 40
jmeno = "Alibaba"
pozdrav = "Ahoj"
sdeleni = Pozdrav + ", jmenuji se " + jmeno + " a mám " + pocet_loupezniku + " kamarádů."
```

Python však nabízí alternativu, tzv. `f-string`. Před uvozovky na začátku stringu vložíme písmenko `f` a do věty dosadíme název proměnné do složených závorek `{}`

```python
pocet_loupezniku = 40
jmeno = "Alibaba
pozdrav = "Ahoj
sdeleni = f"{pozdrav}, jmenuji se {jmeno} a mám {pocet_loupezniku} kamarádů."
```

### `int` Integer (celé číslo)

Celé číslo bez desetinné čárky – může být kladné, záporné nebo nula

```python
cena_zbozi = 1200
zustatek_na_ucte = -500
nalada = -5
```

### `float` Float (desetinné číslo)

Celé číslo s desetinnou čárkou. _Pozor, v Pythonu - resp. v angličtině celkově - píšeme s tečkou `.`_

```python
akceptovany_prumer = 1.3
pi = 3.14159

```

### `bool` Boolean (logická hodnota)

Nabývá pouze dvou hodnot: `True`(pravda) nebo `False` (nepravda).
V Pythonu píšeme vždy s velkým písmenem na začátku

```python
miluju_ranni_vstavani = False
poctive_se_ucim = True

```

V programování častokrát potřebujeme vědět, jestli je výraz pravda nebo nepravda. Při porovnávání dvou hodnot dostáváme zpět odpověď, která se rovná buď True nebo False

```python
print(10 > 9) # True
print(10 == 9) # False

```

Podobně také výsledek podmínky `if` vrací True nebo False.

Vetšina hodnot je defaultně `True`. Každý _string_ je _True_, s výjimkou prázdného stringu. Každé _číslo_ je _True_, s výjimkou 0. _List_, _tuple_ nebo _dictionary_ je _True_, pokud není prázdný. _None_ je _False_

### `list` - List (seznam)

List je seznam hodnot. Může obsahovat libovolné datové typy - například té dictionary nebo další list (seznamu v seznamu). Lze jej měnit

Více o listech v kapitole [List a tuple]()

```python
seznam_studentu = ["Jarmil", "Anděla", "Hvězďon", "Višeslava"]
dnesni_den = ["Zvoní budík ⏰", False, "Budík podruhé 🚨", True, 7.45, "😱", "🏃", "⏩🏫", "DTÚ", True, "😢"]
```

Pro přidání do listu používáme funkci `append()`. Pro přístup k jednotlivým hodnotám používáme _index_ (pořadí v listu, začíná 0)

```python
seznam_studentu.append("Ctirad") # ["Jarmil", "Anděla", "Hvězďon", "Višeslava", "Ctirad"]

print(seznam_studentu[1]) # Anděla
```

### `tuple` - Tuple (neměnitelný seznam)

Podobný listu, ale používáme obyčejné závorky `()`. **Nelze** jej měnit (nelze přidávat, mazat nebo upravovat položky)

Více o tuplech v kapitole [List a tuple]()

```python
souradnice = (50.1294, 16.3103)
barva = (255, 0, 0)
```

### `dict` - Dictionary (slovník)

Ukládá dvojci key: value (klíč: hodnota). Používáme pro strukturovaná data. Lze měnit

Více o dictionary v kapitole [Dictionary]()

```python
vzorny_student = {
    "jméno": "Redacted",
    "zápisky": True,
    "známka": 1.2,
    "spí_v_hodinách": False,
}
```

K hodnotám můžeme přistupovat přes `key`. Přes key je můžeme také měnit

```python
print(vzorny_student["známka"]) # 1.2
vzorny_student["známka"] = 1.15 # změní hodnotu známky v původním dictionary
```

### `NoneType` - None (bez hodnoty)

Speciální hodnota, která značí, že zatím nic neobsahuje. Často používáme jako výchozí hodnotu, kterou později přepíšeme.

Může se objevit jako výsledek funkce, která nic nevrací nebo funkce, která měla za úkol něco vyhledat, ale nenašla

```python
vedemosti = None

# Později můžeme změnit
vedomosti = "obsáhlé"

```

## Jak zjistit datový typ proměnné

`type()` užitečná funkce, pomocí které mohu zjistit, jaký datový typ obsahuje proměnná

```python
cislo = 5
print(type(cislo)) # <class 'int'>

radoby_cislo = "5"
print(type(radoby_cislo)) # <class 'str'>

```

## Převody mezi datovými typy (přetypování / type casting)

Pomocí funkcí `str()`, `int()`, `float()`, `bool()`, `list()`, `tuple()`, `dict()` můžeme konvertovat proměnnou na jiný datový typ

```python
lze_zmenit = "True" # původně string
lze_zmenit = bool(lze_zmenit) # nyní boolean True

cislo = 5 # původně integer
cislo = str(cislo) # nyní string -> nově s ním nelze provdáět matematické operace, protože se bude chovat jako text

dalsi_cislo = 14.8 # původně float
dalsi_cislo = int(dalsi_cislo) # změní na celé číslo a zaokrouhlí dolu -> 14

```

Pozor, ne všechny datové typy lze konvertovat mezi sebou

```python
cislo = "7.2" # původně string
cislo = int(cislo) # error, nelze změnit přímo na int

# oprava
cislo = int(float(cislo)) # nejprve změníme na float a poté na int (který číslo zaokrouhlí, vždy dolu, na 3)

```
