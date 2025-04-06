🚧 Work in progress ... 🚧

# Lambda je anonymní funkce

```python
# klasické funkce
def hello():
    print("Hello")


def plus10(x):
    print(x + 10)


# anonymní funkce, které vytváříme klíčovým slovem lambda
# anonymní funkce můžeme uložit pod proměnnou nebo použít přímo (např. v tkinter)
# lambda parametr : co provedeme s parametrem (automaticky returnují výsledek)
a = lambda x: x + 10

# anonymní funkce mohou být pouze na 1 řádek
# anonymní funkce mohou být i bez parametru
b = lambda: print("Hello")


print(a(0))

b()
```
