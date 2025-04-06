# Cyklus for

For je dalším typem cyklu. Když se rozhodujeme, jestli použít `while` nebo `for`, častokrát záleží na prefernci a čitelnosti kódu. Obecně platí, že `for` se používá převážně tam, kde dopředu víme, kolikrát se něco bude opakovat, popřípadě, pokud potřebujeme index (pořadí hodnoty v arrayi). Naopak `while` používáme častěji tehdy, když nevíme, kolikrát se bude něco opakovat.

## Syntax cyklu for

Cyklus for vytvoříme pomocí slovíčka `for`, v závorce pak následuje tzv. inicializace, podmínka a inkrementace. Inicializace nám určuje proměnnou, standardně `i` a hodnotu, na které začínáme. Podmínka určuje, do kdy se bude cyklus opakovat, podobně jako u while. Inkrementace (popř. dekrementace) nám určuje, o kolik budeme zvyšovat (či snižovat) `i` každé kolo cyklu.

```js
for (inicializace; podmínka; inkrementace / dekrementace) {
    // Blok kódu, který chceme opakovat
}
```

Příklad s počítáním do 10:

```js
for (let i = 1; i <= 10; i++) {
    console.log(i)
}
```

Příklad se slovem, které chceme několikrát zopakovat:

```js
for (let i = 1; i <= 3; i++) {
    console.log("cool")
}
```

**Pozor, také z cyklu for můžeme snadno vytvořit nekonečnou smyčku.**
