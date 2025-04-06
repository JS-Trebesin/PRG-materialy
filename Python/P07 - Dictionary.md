# Dictionary

_Dictionary_ neboli slovník slouží k ukládání páru dat: key - value (klíč - hodnota)

_Slovník_ je iterable, je to tedy podobný datový typ jako list (seznam), nicméně seznam umožňuje ukládat data pouze pod určitý index číselné hodnoty - 0, 1, 2, ... - kdežto u slovníku si můžeme index pojmenovat

## Vytvoření slovníku

Slovník vytváříme pomocí složených závorek `{}` a jednotlivé páry klíčů a hodnot oddělujeme čárkou

```python
pokemon = {
    "jméno": "Pikachu",
    "typ": "elektrický",
    "výška": 40.6,
    "evoluce": False,
}
```

_Key_ (klíč) musí být vždy v uvozovkách, tak jako string. _Value_ (hodnota) může být jakýkoliv datový typ - string, int, float, boolean, ale také seznam nebo další slovník

## Přístup k hodnotám

Pokud chceme vypsat hodnotu ve slovníku, přistupujeme k nim podobně, jako k hodnotám v listu

```python
print(pokemon["jméno"]) # Pikachu
```

Alternativně můžeme využít funkce `.get()`

```python
print(pokemon.get("jméno")) # Pikachu
```

Funkce `.get()` má výhodu, že nevyhodí error, pokud daný pár key-value neexistuje. V závorce můžeme jako druhý argument zvolit hodnotu, kterou funkce vrátí, pokud daný *key* neexistuje - pokud druhý argument neuvedeme, vrátí `None`

```python
print(pokemon["barva"]) # Error, key barva neexistuje

print(pokemon.get("barva")) # None
print(pokemon.get("barva", "barva nenalezena")) # barva nenalezena
```

### Procházení dictionary - chceme keys

Dictionary je iterable, tzn. pro procházení dictionary můžeme využít cyklus `for`. `for proměnná in dictionary` prochází *klíče* (keys)

```python
for key in pokemon:
    print(key)

# jméno, typ, výška, evoluce
```

Pokud chceme být explicitní, můžeme využít funkci `keys()`. Kód je díky tomu čitelnější, na první pohled vidíme, proč používáme cyklus

```python
for key in pokemon.keys():
    print(key)

# jméno, typ, výška, evoluce
```

### Procházení dictionary - chceme values

Častěji však chceme hodnoty (values). Zde máme také dvě možnosti

```python
for key in pokemon:
    print(pokemon[key])

# Pikachu, elektrický, 40.6, False
```

Alternativně lze použít i funkci `values()`. Také zde je výhoda čitelnost kódu

```python
for value in pokemon.values():
    print(value)

# Pikachu, elektrický, 40.6, False
```

### Procházení dictionary - chceme keys i values

V případě, že chceme pracovat jak s klíčem, tak s hodnotou, použijeme funkci `items()`

```python
for key, value in pokemon.items():
    print(f"Klíč je {key}, hodnota je {value}")
```

### `if` `in`

Chceme-li zkontrolovat, jestli se určitý key nachází v našem slovníku, můžeme využít výraz `in` ve spojení s podmínkou `if`

```python
key = "jméno"

if key in pokemon:
    print(pokemon[key])

# Pikachu
```

```python
key = "barva"

if key in pokemon:
    print(pokemon[key])
else:
    print("Nenalezeno")

# Nenalezeno --> náš pokémon nemá key "barva"
```

## Přepsání hodnoty

Pokud chceme hodnotu změnit, přiřadíme ji novou hodnotu, podobně jako u listu

```python
pokemon["výška"] = 41
```

Stejně postupujeme, chceme-li přidat nový pár key-value

```python
pokemon["barva"] = "žlutočerná"
```

## Smazání hodnoty

Pro smazání hodnoty můžeme použít buď `pop(key)`, které funguje obdobně jako u listu nebo funkci `del(key)`

