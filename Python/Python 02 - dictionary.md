# Dictionary

_Dictionary_ neboli slovník, který slouží k ukládání dat - konkrétně páru key - value (klíč - hodonota).

_Dictionary_ je podobný typ dat jako list, nicméně list umožňuje ukládat data pouze pod určitý index číselné hodnoty - 0, 1, 2, ... - kdežto u dictionary si můžeme index pojmenovat.

### Vytvoření dictionary

Dictionary vytváříme pomocí složených závorek `{}` a jednotlivé páry hodnot oddělujeme čárkou

```python
pokemon = {
    "jméno": "Pikachu",
    "typ": "elektrický",
    "výška": 40.6,
    "evoluce": False,
}
```

Dictionary vytváříme pomocí složených závorek `{}` a jednotlivé páry hodnot oddělujeme čárkou.

_Key_ musí být vždy v uvozovkách, jako string. _Value_ (hodnota) může být jakýkoliv datový typ - string, int, float, boolean, ale také list nebo další dictionary.

### Přístup k hodnotám

Pokud chceme vypsat hodnotu v dictionary, přistupujeme k nim podobně, jako k hodnotám v listu

```python
print(pokemon["jméno"])
# Vypíše Pikachu
```

Pokud chceme vypsat všechny hodnoty dictionary, využijeme cyklus for

```python
for value in pokemon:
    print(pokemon[value])

# Vypíše Pikachu, elektrický, 40.6, False
```

Chceme-li zkontrolovat, jestli se určitý key nachází v našem dictionary, můžeme využít výraz `in` ve spojí s podmínkou `if`

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

# Vypíše Nenalezeno, protože náš pokémon nemá key "barva"
```

### Přepsání hodnoty

Pokud chceme hodnotu změnit, klasicky ji přiřadíme novou hodnotu

```python
pokemon["výška"] = 41
```

Stejně postupujeme, chceme-li přidat nový pár key-value

```python
pokemon["barva"] = "žlutočerná"
```
