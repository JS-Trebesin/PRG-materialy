Work in progress...


```python
import sys

def kladne_zaporne(x):
    if x > 0:
        print("číslo je kladné")
    elif x < 0:
        print("číslo je záporné")
    else:
        print("číslo je 0")

while True:
    try:
        cislo = int(input("Zadej číslo: "))
        kladne_zaporne(cislo)
    except KeyboardInterrupt:
        print("Program manuálně ukončen")
        sys.exit()
    except ValueError:
        print("Špatný input... zadal/a jsi číslo?")
    else:
        print("Kód proběhl úspěšně")
        break
    finally:
        print("Finally se vypíše vždy")
```
