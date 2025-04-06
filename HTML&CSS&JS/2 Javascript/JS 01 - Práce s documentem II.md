# Upravování HTML pomocí Javascriptu

## Vytvoření nového prvku

Pomocí Javascriptu můžeme vytvořit nový prvek. K tomu použijeme příkaz `document.createElement("název-prvku")`

Příklad:

```js
let novyDiv = document.createElement("div")
```

V závorce v uvozovkách je vždy název prvku: `h1`, `p` `div`, `span`, atd.

## Vložení nového prvku do Javascriptu

`document.createElement("název-prvku")` vytvoří nový prvek a my tento prvek uložíme pod určitou proměnnou, aby se ale zobrazil na naší stránce, musíme ho do HTML vložit. K tomu používáme příkaz `komu.append(co)` aneb nový prvek bude child prvku stávajícího `parent.append(child)`

Příklad:

```js
// Vyberu již existující prvek na mé webové stránce - seznam ul
let seznam = document.querySelector("#moje-ul")

// Vytvořím nový prvek - li
let noveLi = document.createElement("li")

// Do li přidám text
noveLi.innerText = "Nová položka v seznamu"

// Nové li přídám do seznamu
seznam.append(noveLi)
```

Stejném způsobem můžeme vytvořit například nový nadpis `h1` a vložit ho do `div` apod.

## Přidání classy prvku

Předtím, než nově vytvořený prvek vložíme do HTML, můžeme mu přidat classu z CSS. Tím se postaráme o to, že prvek bude mít určitý vzhled.

Classu přidáváme pomocí `prvek.classList.add("název-classy")`. Název classy musí být v uvozovkách.

Příklad:

CSS

```css
.modra {
    color: blue;
}
```

Javascript

```js
let novyNadpis = document.createElement("h1")
novyNadpis.innerText = "Text nadpisu"

novyNadpis.classList.add("modra")
```

Tím nám vznikne nový nadpis, který bude mít modrý text. Pomocí `.append()` jej pak mohu vložit do dokumentu.

### Odebrání a přepínání classy

`.classList` má další funkce. Místo `.add()`, které classu přidává, můžeme použít `.remove()` pro odebrání classy, `.toggle()` pro přepínání classy (přidává/odebírá) nebo `.replace()` pro nahrazení jedné classy jinou.

Příklady:

```js
let mujDiv = document.querySelector("#muj-div")

// Přidat classu .modra
mujDiv.classList.add("modra")

// Přidat classu .modra a .zluta
mujDiv.classList.add("modra", "zluta")

// Odebrat classu .modra
mujDiv.classList.remove("modra")

// Přepínat classu .modra
mujDiv.classList.toggle("modra")

// Nahradit classu .modra classou .cervena
mujDiv.classList.replace("modra", "cervena")
```
