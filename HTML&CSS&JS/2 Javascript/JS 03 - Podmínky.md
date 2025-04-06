# Podmínky

Podmínky jsou základním stavebním kamenem pro tvorbu logiky programu.

*"Pokud něco platí, tak proveď daný kód."*

## Syntax podmínek

Podmínky vytvořím pomocí slovíčka `if` a do kulatých závorek napíšu, co musí platit, aby se spustit kód, který bude ve složených závorkách. Jelikož jedno rovnítko používáme pro přiřazování hodnot k proměnným, pro porovnávání používáme více rovnítek. V Javascriptu to jsou tři rovníka ===.

```js
if (podmínka) {
    // Blok kódu, který se provede pokud podmínka platí
}
```

```js
let pizza = "hawaii"

if (pizza === "hawaii") {
    console.log("Za to by tě italové nepochválili!")
}

// program vypíše "Za to by tě italové nepochválili!"
```

Kód porovná jestli se pizza rovná slovu hawaii a pokud je to pravda, vykoná kód. Pokud to pravda není a pizza se nerovná hawaii, kód ve složených závorkách je ignorován.

```js
let pizza = "margherita"

if (pizza === "hawaii") {
    console.log("Za to by tě italové nepochválili!")
}

// nic se nestane
```

## else if

Slovíčkem `else if` můžeme rozšířit logiku našeho kódu. Za `else if` můžeme napsat druhou podmínku (a třetí, čtvrtou, pátou atd, počet použitých `else if` není omezen). Za `else if`, stejně jako za samotným `if` píšeme podmínku do kulatých závorek a kód ke spuštění do závorek složených.

```js
let pizza = "funghi"

if (pizza === "hawaii") {
    console.log("Za to by tě italové nepochválili!")

} else if (pizza === "funghi") {
    console.log("Houby na pizze jsou větší hřích než ananas")
}

// program vypíše "Houby na pizze jsou větší hřích než ananas"
```

## else

Posledním klíčovým slovem v klasikých `if` podmínkách je slovíčko `else`. Samotné `else` znamená _"v ostatních případech"_ a provede následující kód v případě, že není splněna žádná z podmínek výše. Proto se u else nepoužívají kulaté závorky, není totiž potřeba žádná nová podmínka. Pouze do složených závorek napíšeme kód, který se splní v případech, že původní tvrzení neodpovídá žádné z našich podmínek.

```js
let pizza = "margherita"

if (pizza === "hawaii") {
    console.log("Za to by tě italové nepochválili!")

} else if (pizza === "funghi") {
    console.log("Houby na pizze jsou větší hřích než ananas")

} else {
    console.log("Nekontroverzní výběr")
}

// program vypíše "Nekontroverzní výběr"
```

Jelikož v příkladě výše "mergherita" nesplňuje ani první `if` podmínku, ani následující `else if`, provede se kód u `else`.

## Porovnávání v podmínkách


Pro porovnávání používáme znaky:

- rovná se `===` 
- nerovná se `!==`
- větší `>`, popř. větší nebo rovno `<=`
- menší `<`, popř. menší nebo rovno `>=`

Pokud je v závorce jediná hodnota, např `if (proměnná)`, je to zkrácený zápis pro `if (proměnná === true)`

Podobně `if (!proměnná)` se dá popsat jako "if NOT proměnná", kde "not" znamená "ne" nebo "opak". Aneb pokud je proměnná `false`, prázdný string `""`, `0` nebo pokud třeba vůbec neexistuje, říkáme tomu, že je tzv. "falsy" --> a splní se podmínka `if (!proměnná)`
