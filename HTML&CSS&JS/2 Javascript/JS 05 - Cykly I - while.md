# Cyklus while

Cykly (smyčky) nám umožňují opakovat určitou část kódu. Tím si můžeme usnadit úkoly, které by byly jinak zbytečně zdlouhavé. Cyklus se opakuje do doby, dokud platí určitá podmínka.

Například, pokud budu chtít napočítat do 100, nebudu vypisovat sto čísel, ale pomůžu si cyklem.

## Syntax cyklu while

Cyklus `while` vytvořím pomocí slovíčka while, za které do kulaté závorky napíšu podmínku - cyklus se bude opakovat do doby, do které tato podmínka platí. Tato podmínka je testována před každým průchodem smyčkou a pokud podmínka platí, provede se blok kódu uvnitř složených závorek.

```js
while (podmínka) {
    // Blok kódu, který se opakuje
}
```

Příklad počítání do 10:

```js
let i = 1

while (i <= 10) {
    console.log(i)
    i++
}
```

Nejprve jsme definovali proměnnou i s hodnotou, na které začínáme počítat, poté opakujeme vypisování do konzole, dokud je i menší nebo rovno 10, každé kolo vypíšeme i a zvětšíme i o 1, tedy při druhém průchodu bude i 2, při dalším průchodu bude i 3 atd., dokud nebude i 11, poté přestane platit podmínka, cyklus se přeruší a kód pokračuje dál na další řádek po cyklem while.

`i++`, což je zkrácený zápis pro `i = i + 1`, nám říká, že i přepisujeme jeho původní hodnotou + 1, aneb zjednodušeně, že i zvýšíme o 1.

Pomocí while můžeme snadno něco zopakovat.

```js
let i = 1

while (i <= 3) {
    console.log("cool")
    i++
}
```

Vypíše slovo `cool` 3x do konzole.

## Pozor na nekonečné smyčky

Pokud špatně nastavíme podmínku, může se stát, že se dostaneme do nekonečné smyčky. To může způsobit zaseknutí prohlížeče nebo počítače (pokud nastane nekonečná smyčka, je dobré vždy vypnout okno prohlížeče)

```js
let i = 1

while (i <= 10) {
    console.log(i)
    // zde chybí i++
}
```

V tomto cyklu chybí i++, tedy navýšení i. To znamená, že i bude vždy 1 a podmínka, že je menší nebo rovno 10 bude vždy platit, smyčka tedy poběží do nekonečna. Toto je jen jeden ze způsobů, jak se dostat do nekonečné smyčky, dalším způsobem může být, že špatně nastavíme podmínku.

## Vkládání podmínek do cyklů a přerušení cyklu

Do while můžeme vnořit `if` podmínky, popřípadě i další cyklus `while`.

Náš první příklad, vypisování čísel do 10 by se dal zapsat i jiným způsobem (jinak bude fungovat stejně, jako první příklad výše, napočítá do 10):

```js
let i = 1

while (true) {
    if (i <= 10) {
        break
    }
    console.log(i)
    i++
}
```

Konstrukt `while (true)` nám vytváří nekonečnou smyčku - true v závorce vždy platí. Jelikož takto úmyslně vytváříme nekonečnou smyčku, aby program správně fungoval, musíme někde vytvořit přerušení - k tomu nám pomůže příkazz `break`. Tento cyklus funguje stejně. Tento zápis se může hodit, pokud vytváříme cyklus, který budeme přerušovat pomocí několika různých podmínek - můžeme tedy využít `if` a `else if` s příkazem `break`.

## Do while

Do while je alternativa cyklu while, která se liší tím, že kód se provede před zkontrolováním podmínky, takže vždy proběhne alespoň jednou. Zapisuje se následovně:

```js
do {
    // Blok kódu
} while (podmínka)
```

Například - uživatel bude přes prompt opakovaně hádat číslo, dokud nezadá správné, v tomto případě 42
Přes do while můžeme zapsat cyklus jednodušeji, než přes klasické while - snáze se řeší případ, pokud zadá správné číslo na první pokus.

```js
let cislo = 0

do {
    cislo = parseInt(prompt("Hádej číslo od 0 do 100:"))
} while (cislo !== 0)
```
