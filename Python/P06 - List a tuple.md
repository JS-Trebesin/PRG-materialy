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
