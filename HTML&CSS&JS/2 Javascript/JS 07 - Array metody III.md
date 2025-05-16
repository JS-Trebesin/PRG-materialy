# Array metody III

**Metody neměnící array**

*tzv. immutable array methods*

žádná z metod níže nezmění původní array, ale vrátí nový array nebo jinou hodnotu

**Metody zmíněné v sekcích I, II a III jsou pouze některé vybrané metody, které Javascript poskytuje - celý seznam všech array metod v Javascriptu lze najít např. na stránkách [mozilly](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).**

**Pokusný array plný objektů, sloužící k demonstraci funkčnosti metod uvedených níže**

```jsx
const veci = [
	{ nazev = "Trampolína", cena: 500  },
	{ nazev = "Skluzavka",  cena: 1000 },
	{ nazev = "Hrad",       cena: 5000 },
	{ nazev = "Bazén",      cena: 300  }
]
```

**Pro všechny metody níže platí**

- lze vložit celou funkci místo arrow funkce (šipky) - např. array.filter(název funkce)

## filter

*Arrayi, vyfiltruj mi následující hodnoty*

- filtruje vše co neodpovídá podmínce

```jsx
array.filter((něco) => {
	return podmínka 
  // např. něco.hodnota === 100
})
```

```jsx
const levneVeci = veci.filter((vec) => {
	return vec.cena <= 1000
	})
	// vrátí nový array s věcmi 
	// s cenou do 1000
})
```

- vrátí nový array s hodnotama, které odpovídají podmínce

## forEach

*************************************Arrayi, pro každou položku udělej…*************************************

- pro každou věc v arrayi provede určitý kód

```jsx
array.foEach((něco) => {
	kód, který chceme asi se provedl
	pro každou věc
  // např. console.log(něco)
})
```

```jsx
veci.foEach((vec) => {
	console.log(vec.cena)
	// vypíše všechny ceny
})
```

- nic nevrací (nemá return)
- podobný cyklu for, je kratší a čitelnější
- pokud chceme přístup k indexu, můžeme zadat druhý parametr`array.forEach((něco, index) => {kód})`
- alernativou k forEach je for…of, které umožňuje použít break, continue nebo return

## map

*Arrayi, změň položky*

- vezme array a změní ho v nový array s pozměněnýma hodnotama

```jsx
array.map((něco) => {
	return úpravené něco
  // např. něco * 2
})
```

```jsx
const ceny = veci.map((vec) => {
	return vec.cena
  // vypíše nový array s cenami
})
```

- vrátí nový array s hodnotama, které odpovídají podmínce
- funguje podobně jako forEach, ale vrátí nový array
- pokud nevyužiješ return (a nově vytvořený array), použij raději forEach nebo for…of

## find

****Arrayi, najdi první věc, která…****

- najde první objekt v arrayi, který odpovídá kritériím

```jsx
array.find((něco) => {
	return kritérium
  // např. něco === "hodnota"
})
```

```jsx
const hledanaVec = veci.find((vec) => {
	return vec.nazev === "Hrad"
	// vypíše celý objekt se jménem Hrad
	// tzn. { nazev = "Hrad", cena: 5000 }
})
```

- vrátí pouze první objekt
- vrátí celý objekt

## some

*Arrayi, je tam něco takovýho?*

- zkontroluje, jestli alespoň **jedna** položka v arrayi odpovídá zvoleným kritériím a vrátí ano/ne (resp. true/false)

```jsx
array.some((něco) => {
	return kritérium
  // např. něco < 100
})
```

```jsx
const vecNadTisic = veci.some((vec) => {
	return vec.cena > 1000
	// vrátí true
})
```

- pokud chceš najít pouze konkrétní hodnotu v jednodušším arrayi (např. pouze string nebo integer), použij raději `array.includes()`
- vrátí pouze true nebo false
- stačí když jedna věc v arrayi odpovídá kritériím

## every

*Arrayi, jsou všechny položky… ?*

- zkontroluje, jestli **všechny** položky v arrayi odpovídá zvoleným kritériím a vrátí ano/ne (resp. true/false)

```jsx
array.every((něco) => {
	return kritérium
  // např. něco < 100
})
```

```jsx
const vseNadTisic = veci.every((vec) => {
	return vec.cena > 1000
	// vrátí false
})
```

- vrátí pouze true nebo false
- všechny položky v arrayi musí odpovídat kritériím

## reduce

*Arrayi, spojt vše do jedné hodnoty*

- vezme array a vytvoří jednu výslednou hodnotu

```jsx
array.reduce((akumulátor, něco) => {
	return akumulátor + něco
  // např. akumulátor + něco.hodnota
}, počáteční hodnota)
```

```jsx
const celkovaCena = veci.reduce((soucet, vec) => {
	return soucet + vec.cena
}, 0)
console.log(celkovaHodnota) // vypíš součet všech cen aneb 5800
```

- má dva parametry, první je akumulátor, druhý prvek (který jsme měli i v ostatních metodách)
- + je potřeba uvést i počáteční hodnotu
- prochází celý array a přidává hodnoty jednotlivých položek do jedné výsledné hodnoty
- vrací výslednou hodnotu
- nemusí pouze sčítat, může také násobit atd.