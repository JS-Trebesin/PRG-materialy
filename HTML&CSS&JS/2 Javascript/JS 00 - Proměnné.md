# Proměnné (variables) v Javascriptu

Je důležité pojmenovávat proměnné popisně, aby název jasně ukazoval, co proměnná obsahuje

V Javascriptu se používá tzv. camelCase - když má proměnná dvě slova, první píšeme malým písmenkem, každé další velkým: prikladTakovePromenne

Nikdy nepoužívat diakritiku v názvech proměnných

## Tři způsoby vytváření (definování) proměnných

### let

```js
let pozdrav = "ahoj"
```

lze později přepsat

```js
pozdrav = "čau"
```

proměnná pozdrav tedy bude mít novou hodnotu "čau", která přepsala hodnotu "ahoj"

### const

nelze přepsat

```js
const pozdrav = "ahoj"
```

### var

zastaralé, ale je dobré znát, může se objevit při googlení v cizím kódu

funguje podobně jako let

```js
var pozdrav = "ahoj"
```

## Typy proměnných

### string

(text) psán vždy v uvozovkách

```js
let jmeno = "Jarmila"
```

### int

(celé číslo) psáno bez uvozovek

```js
let cislo = 42
```

### float / double

(desetinné číslo)

```js
let pozdrav = 12.5
```

### boolean

(true nebo false)

```js
let znalosti = true
```

### array

array (seznam) psát do hranatých závorek, hodnoty oddělené čárkou

```js
let studenti = ["Kvído", "Hvězdoslava", "Kazimír", "Jarmila"]
```

-   každá položka v arrayi má svůj index (své číslo) a jelikož počítač počítá od 0, tak Kvído má index 0, Hvězdoslava 1 atd.

-   když chci zjistit hodnotu určité položky na seznamu, používáme syntax `array[index]`

```js
let studenti = ["Kvído", "Hvězdoslava", "Kazimír", "Jarmila"]
console.log(studenti[1])
// Vypíše 'Hvězdoslava', která je na indexu 1 v arrayi 'studenti'
```

-   pokud chci vytvořit kopii arraye, mohu použít následující syntax `kopieStudentů =  [... studenti]`

### object

tato sekce bude probírána v pozdější látce, ale zde je jednoduchý příklad:

```js
let kocka = {
    jmeno: "Simba",
    barva: "žlutohnědá",
    vek: 8,
}
console.log(kocka.barva)
// Vypíše 'žlutohnědá'
```

## Práce s proměnnými

Na základě toho, o jaký typ proměnné se jedná s nimi mohu rozdílně pracovat.

### Spojování proměnných

String (text) můžeme spojovat (concatenate) pomocí znaménka +

```js
let jmeno = "James"
let prijmeni = "Bond"

console.log(prijmeni + jmeno + prijmeni)
// vypíše BondJamesBond
```

Text mohu spojovat i s dalším textem a tím do něj přidat mezery a čárky, popřípadě jakýkoliv další text.

```js
console.log(prijmeni + ", " + jmeno + " " + prijmeni)
// vypíše Bond, James Bond
```

### Matematické operace

Pro sčítání číselných hodnot, jako jsou celá čísla (integer) a desetinná čísla (float), používáme '+'. Stejně tak můžeme použít '-', '\*', '/' a '\*\*' pro odčítání, násobení, dělení a mocnění.

```js
let a = 3
let b = 5

console.log(a + b)
// vypíše 8
```

**Modulo**

% tzn. modulo, dá nám zbytek dvou čísel po dělení

`4%2` bude `0`. (4/2 = 2 a zbytek 0)

`7%2` bude `1`. (7/2 = 3 a zbytek 1)

(modulo pracuje s celými čísly, takže např. 3%2 je také 1)

Modulo se častokrát používá pro zjišťování sudých čísel

```js
if (cislo % 2 === 0) {
    // co se stane když je cislo sudé
}
```

ale funguje i pro zjišťování dělitelnosti dalších čísel `9%3` je `0`, `5%4` je `1` atd.
