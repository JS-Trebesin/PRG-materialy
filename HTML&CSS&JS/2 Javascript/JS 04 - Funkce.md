# Funkce
Funkce je blok kódu, který můžeme pojmenovat a později zavolat. Díky tomu můžeme část kódu, který funkce obsahuje, snadno opakovaně využít v našem programu, aniž bychom museli celý kód znovu přepisovat. Funkce nám také umožňují kód lépe organizovat a efektivněji upravovat.

Například, pokud budu chtít v rámci programu převádět hodnotu z kilometrů na míle, nemusím pokaždé vypisovat vzoreček, místo toho můžu vytvořit funkci a zavolat jí.

Do funkcí mohu psát jakýkoliv kód, takže například podmínky, cykly. atd.

### Vytvoření funkce

Funkci vytvoříme pomocí slovíčka function, poté zvolíme její název, pak použijeme kulaté závorky (funkce může, ale nemusí přijímat tzv. parametry) a poté složené závorky, které ohraničují blok kódu dané funkce

````js
function pozdrav(jmeno) {
    console.log("Pápá" + jmeno)
}
````



### Zavolání funkce

Funkci mohu zavolat (spustit) tím, že napíšu její název a zadám parametr (ne každá funkce má parametr, pokud jej nemá, musím stejně napsat prázdné závorky)

````js
pozdrav("Tinky Winky")
````



Po zavolání funkce se provede kód, tzn. do konzole se vypíše 

````
Pápá Tinky Winky
````





_Funkce se spouští až při jejím zavolání, dokud funcki nezavolám, je kód uvnitř funkce **neaktivní**_



## Parametry

### Funkce s parametry

Funkce může přijímat parametry, které píšu do závorky, když funkci vytvářím. Parametrů může mít i vícero.

```js
function scitani(a,b) {
    let vysledek = a + b
    console.log(vysledek)
}
```




Hodnoty, se kterými bude dané funkce konkrétně pracovat poté dosadím, když funkci zavolám. 

Například `scitani(2,3)` vypíše výsledek `5`




_Parametry fungují v rámci funkce v podstatě jako proměnné._
_V kódu funkce mohu vytvářet také klasické proměnné, ale pozor na to, pokud je definuji uvnitř funkce, tak s nimi nelze pracovat mimo danou funkci._



### Funkce bez parametrů

Ne každá funkce musí mít parametr. Pokud parametr nemá, vytvářím 

````js 
function pozdrav() {
    console.log("Ahoj")
}
````



a volám funkci

````js 
pozdrav() 

````


s prázdnými kulatými závorkami. Tato funkce nepřijímá žádný parametr a proto bude mít statický kód, což ale může být často žádoucí.

````
Ahoj
````

## Return

Funkce nám také mohou vrátit nějakou hodnotu. K tomu používáme slovíčko **return**. Return **ukončí ** funkci a vrátí hodnotu tam, kde byla funkce zavolána. 
Tzn. jakýkoliv kód, který je ve funkci napsán po return se již neprovede.

````js 
function prevodNaMile(km) {
    let mile = km * 1.6
}
````

Díky tomu mohu získat výsledek operace ve funkci a použít jej dále ve svém kódu. Takový výsledek mohu například schovat pod proměnnou

````js 
let petKmNaMile = prevodNaMile(5)
````


Pod touto proměnnou je nyní schován výsledek funkce, tzn. číslo 8

## Anonymní funkce

V Javascriptu můžeme vytvářet také anonymní funkce, kterým nedáme název. 

Pokud chceme vytvořit funkci a použít ji pouze jednou, nemusíme zbytečně vymýšlet její název a raději použijeme anonymní funkci. Taková situace může nastat například v případě, že chceme vložit funkci do jiné funkce (např. do addEventListeneru).

Příklad právě u addEventListeneru:

````js 
tlacitko.addEventListener("click", function() {
    console.log("Tlačítko stisknuto")
})
````

Anonymni funkci mohu také schovat do proměnné, ale většinou bývá v takovém případě lepší funkci rovnou pojmenovat.

## Arrow funkce

V Javascriptu můžeme využít zkrácený zápis funkce pomocí šipky `=>`
- používá se zejména pro anonymní funkce. 
- `function()` je nahrazeno `() =>`

````js 

// místo tradičního zápisu anonymní funkce

tlacitko.addEventListener("click", function() {
    console.log("Tlačítko stisknuto")
})

// můžeme použít

tlacitko.addEventListener("click", () => {
    console.log("Tlačítko stisknuto")
})

````
A pokud chceme vrátit hodnotu a máme pouze jeden řádek kódu, můžeme vynechat `{}`. Příklad:  `(a) => a + 100`

Arrow funkce je vždy bez názvu, můžeme ji však schovat pod proměnnou, například:


````js 

// tradiční zápis anonymní funkce

const prictiSto1 = function (a) {
    return a + 100
}

// arrow funkce

const prictiSto2 = (a) => a + 100
````



