# Array metody I

**Metody měnící array**

*tzv. mutable array methods*

všechny z metod níže změní původní array

## push

*Arrayi, přidej věc*

- přidá novou položku do arraye

```jsx
array.push(něco)
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.push("Prófa")
console.log(trpaslici)
// vypíše ['Šmudla', 'Kejchal', 'Dřímal', 'Rejpal', 'Prófa']
```

- nová položka je přidána na konec
- také lze vložit proměnnou, např. `novyTrpaslik = "Prófa"`, `trpaslici.push(novyTrpaslik)` nebo vložit přímo hodnotu (viz příklad výše)

## pop

*Arrayi, vyhoď poslední věc*

- vyhodí poslední položku z arraye a vrátí její hodnotu

```jsx
array.pop()
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.pop()
console.log(trpaslici)
// vypíše ['Šmudla', 'Kejchal', 'Dřímal']
```

- vyhozenou položku lze uložit do proměnné `vykopnutyTrpaslik= trpaslici.pop()` a poté s ní můžeme dále pracovat `console.log(vyhozenyTrpaslik)`

## shift

*Arrayi, vyhoď první věc*

- vyhodí první položku z arraye a vrátí její hodnotu

```jsx
array.shift()
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.shift()
console.log(trpaslici)
// vypíše ['Kejchal', 'Dřímal', 'Rejpal']
```

- vyhozenou položku lze uložit do proměnné `vykopnutyTrpaslik= trpaslici.shift()` a poté s ní můžeme dále pracovat `console.log(vyhozenyTrpaslik)`

## unshift

*Arrayi, přidej věc na začátek arraye*

- přidá novou položku na začátek arraye

```jsx
array.unshift(něco)
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.unshift("Prófa")
console.log(trpaslici)
// vypíše ['Prófa', 'Šmudla', 'Kejchal', 'Dřímal', 'Rejpal']
```

- nová položka je přidána na začátek
- také lze vložit proměnnou, např. `novyTrpaslik = "Prófa"`, `trpaslici.unshift(novyTrpaslik)` nebo vložit přímo hodnotu (viz příklad výše)

## splice

*Arrayi, jdeme operovat - nahraď/vyhoď/dosaď/ věc na konkrétní místo*

- splice je taková chirurgická operace - umožní z určitého místa vyhoď položku, nahradit ji nebo dosadit položku

```jsx
array.splice(z jakého místa, kolik věcí nahradit, čím to nahradit)
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.splice(3, 0, "Prófa")
// z indexu 3 (4. místo) vyhoď 0 položek a dosaď tam Prófu
console.log(trpaslici)
// ['Šmudla', 'Kejchal', 'Dřímal', 'Prófa', 'Rejpal']
```

*Alternativní příklad:*

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.splice(1, 2, "Prófa")
// od indexu 1 (2. místo) vyhoď 2 položky a dosaď tam Prófu
console.log(trpaslici)
// vypíše ['Šmudla', 'Prófa', 'Rejpal']
```

- splice pracuje s indexy arraye (aneb pořadím položek v array - důležité vědět: array počítá od 0)
- pokud chci nahradit pouze jednu hodnotu, je lepší použít např. `trpaslici[1] = "Prófa"`, což vymění Kejchala za Prófu
- pomocí splice také můžeme vyhodit položku z konkrétního místa v arrayi, například `trpaslici.splice(2, 1)` vyhodí položku z indexu 2, což by v našem příkladu vyhodilo Dřímala
- nově existuje metoda `array.toSpliced()`, která funguje totožně, ale vrátí nový array a původní nezmění `trpasliciy.toSpliced(2, 1)`

## sort

*Arrayi, seřaď se*

- seřadí array - podle abecedy nebo největšího po nejmenší

```jsx
array.sort()
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.sort()
console.log(trpaslici)
// vypíše ['Dřímal', 'Kejchal', 'Rejpal', 'Šmudla']
```

- nově existuje metoda `array.toSorted()`, která funguje totožně, ale vrátí nový array a původní nezmění

## reverse

*Arrayi, otoč pořadí položek v arrayi*

- otočí pořadí položek arrayi

```jsx
array.reverse()
```

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.reverse()
console.log(trpaslici)
// vypíše ['Rejpal', 'Dřímal', 'Kejchal', 'Šmudla']
```

- pokud chci seřadit položky v arrayi podle abecedy od z po a nebo hodnoty od nejvyšší po nejnižší, je potřeba nejdřív použít .sort() a až poté .reverse()

```jsx
const trpaslici = ["Šmudla", "Kejchal", "Dřímal", "Rejpal"]

trpaslici.sort()
trpaslici.reverse()
console.log(trpaslici)
// vypíše ['Šmudla', 'Rejpal', 'Kejchal', 'Dřímal']
```

- nově existuje metoda `array.toReversed()`, která funguje totožně, ale vrátí nový array a původní nezmění