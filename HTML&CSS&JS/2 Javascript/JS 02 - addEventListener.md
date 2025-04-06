# addEventListener
přidá listener (naslouchač) nějakému prvku


## Příklad:


````js

let mujText = document.querySelector("#text")
let tlacitko = document.querySelector("#tlacitko")

tlacitko.addEventListener("click", zmenBarvuTextu) 

function zmenBarvuTextu() {
    mujText.style.color = "purple"
}

````


### Co se děje:

1. mám text a tlačítko v HTML

````js
let mujText = document.querySelector("#text")
let tlacitko = document.querySelector("#tlacitko")
````

2. přidám tlačítku listener, který naslouchá kliku myši, pokud se událost provede (uživatel klikne na tlačítko) spustí funkci zmenBarvuTextu

````js
tlacitko.addEventListener("click", zmenBarvuTextu) 
````
3. vytvořím funkci zmenBarvuTextu, na kterou jsem odkázal při přidání listeneru a která změní barvu textu na fialovou

````js
function zmenBarvuTextu() {
    mujText.style.color = "purple"
}

````


### Výsledek:

![chameleon](https://user-images.githubusercontent.com/84028625/225429651-3165fc68-79c5-4969-aa43-0435b5ccc59b.gif)
