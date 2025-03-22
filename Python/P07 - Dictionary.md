# Dictionary

_Dictionary_ neboli slovník slouží k ukládání dat, konkrétně páru key - value (klíč - hodnota).

_Slovník_ je podobný typ dat jako seznam (list), nicméně seznam umožňuje ukládat data pouze pod určitý index číselné hodnoty - 0, 1, 2, ... - kdežto u slovníku si můžeme index pojmenovat.

### Vytvoření slovníku

Slovník vytváříme pomocí složených závorek `{}` a jednotlivé páry klíčů a hodnot oddělujeme čárkou

```python
pokemon = {
    "jméno": "Pikachu",
    "typ": "elektrický",
    "výška": 40.6,
    "evoluce": False,
}
```

_Key_ (klíč) musí být vždy v uvozovkách, tak jako string. _Value_ (hodnota) může být jakýkoliv datový typ - string, int, float, boolean, ale také seznam nebo další slovník.

### Přístup k hodnotám

Pokud chceme vypsat hodnotu ve slovníku, přistupujeme k nim podobně, jako k hodnotám v seznamu

```python
print(pokemon["jméno"])
# Vypíše Pikachu
```

Pokud chceme vypsat všechny hodnoty slovníku, využijeme cyklus for

```python
for key in pokemon:
    print(pokemon[key])

# Vypíše Pikachu, elektrický, 40.6, False
```

Alternativně lze použít i funkci .values()

```python
for value in pokemon.values():
    print(value)

# Vypíše Pikachu, elektrický, 40.6, False
```

V případě, že chceme pracovat jak s klíčem, tak s hodnotou, použijeme funkci .items()

```python
for key, value in pokemon.items():
    print(f"Klíč je {key}, hodnota je {value}")

```

Chceme-li zkontrolovat, jestli se určitý key nachází v našem slovníku, můžeme využít výraz `in` ve spojení s podmínkou `if`

```python
key = "jméno"

if key in pokemon:
    print(pokemon[key])
else:
    print("Nenalezeno")

# Vypíše pikachu
```

```python
key = "barva"

if key in pokemon:
    print(pokemon[key])
else:
    print("Nenalezeno")

# Vypíše Nenalezeno --> náš pokémon nemá key "barva"
```

### Přepsání hodnoty

Pokud chceme hodnotu změnit, přiřadíme ji novou hodnotu podobně jako bychom chtěli přepsat hodonotu indexu u listu - využijeme hranatých závorek

```python
pokemon["výška"] = 41
```

Stejně postupujeme, chceme-li přidat nový pár key-value

```python
pokemon["barva"] = "žlutočerná"
```
