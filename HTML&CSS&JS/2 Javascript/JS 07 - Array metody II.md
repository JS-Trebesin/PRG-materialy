# Array metody II

**Metody neměnící array**

*tzv. immutable array methods*

žádná z metod níže nezmění původní array, ale vrátí nový array nebo jinou hodnotu

## concat

*Spoj dva arraye*

- vytvoří nový arraye spojením dvou jiných arrayů

```jsx
array1.concat(array2)
```

```jsx
const teamCap = ["Captain A", "Falcon", "Bucky"]
const teamIM = ["Iron-man", "Natasha", "Black Panther"]

const avengers = teamCap.concat(teamIM)
console.log(avengers)
// vypíše ['Captain A', 'Falcon', 'Bucky', 'Iron-man', 'Natasha', 'Black Panther']
```

- arrayi, kterým začínáme přidáme metodu concat a do závorek vložíme array, který chceme k prvnímu připojit

## slice

*Vyřízni část arraye*

- vyřízne část arraye a tuto část vrátí

```jsx
array.slice(odkud, kam)
```

```jsx
const starWarsFilmy = ["I", "II", "III", "IV", "V", "VI", "VII", "VII", "IX"]

const koukatelne = starWarsFilmy.slice(3, 6)
console.log(koukatelne)
// vypíše ['IV', 'V', 'VI']
```

- pokud uvedeme pouze jednu hodnotu `starWarsFilmy.slice(6)`, uvádíme odkud řezat a dostaneme tedy zbytek arraye `['VII', 'VII', 'IX']`

## join

*Spoj věci z atrraye do stringu*

- vytvoří string ze všech položek arraye

```jsx
array.join()
```

```jsx
const lvi = ["Scar", "Simba", "Nala", "Mufasa"]

const retezecLvu = lvi.join()
console.log(retezecLvu)
// vypíše Scar,Simba,Nala,Mufasa
```

- do závorky join můžeme uvést, jakým znakem chceme položky arraye spojit `console.log(lvi.join("-")` vypíše `Scar-Simba-Nala-Mufasa`

## indexOf

*Arrayi, jaký index má… ?*

- projde array a vypíše index první položky, která se shoduje se zadáním

```jsx
array.indexOf(něco)
```

```jsx
const lvi = ["Scar", "Simba", "Nala", "Mufasa"]

const simbuvIndex= lvi.indexOf("Simba")
console.log(simbuvIndex)
// vypíše 1
```

- lze dosadit i proměnnou místo přímé hodnoty
- podobným způsobem funguje i `array.lastIndexOf(něco)`, který vypíše index poslední položky, která se shoduje se zadáním

## includes

*Arrayi, obsahuješ tuhle hodnotu ?*

- zkontroluje, jestli alespoň **jedna** položka v arrayi má určitou hodnotu vrátí ano/ne (resp. true/false)

```jsx
array.includes(něco)
```

```jsx
const lvi = ["Scar", "Simba", "Nala", "Mufasa"]

const jeTamSimba = lvi.includes("Simba")
console.log(jeTamSimba )
// vypíše true
```

- pokud chceš najít komplexnější kritérium, než jen hodnotu stringu nebo integeru, použij `array.some()`

## at

*Arrayi, co se nachází na indexu… ?*

- vrátí hodnotu, která se nachází na zvoleném indexu

```jsx
array.at(2)
```

```jsx
const lvi = ["Scar", "Simba", "Nala", "Mufasa"]

const lviIndexDva = lvi.at(2)
console.log(lviIndexDva )
// vypíše Nala
```