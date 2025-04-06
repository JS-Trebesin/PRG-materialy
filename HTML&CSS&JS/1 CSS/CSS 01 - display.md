# Display

Vlastnost `display` určuje, jak se prvek zobrazí na webové stránce. Základní typy display jsou:

- block
- inline
- inline-block

Každý prvek v HTML má defautlně nastavenou hodnotu display, toto nastavení ale můžeme libovolně měnit pomocí CSS. Jaké nastavení prvek má poznáme podle toho, jestli odsadí ostatní prvky kolem sebe nebo ne.


## Block


Prkvy, které mají nastavnou s `display: block` zabírají samostatný řádek. Block způsobuje, že se okolní prvky zobrazí na nových řádcích.

![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/79a014c5-4a40-42a5-8a80-14789b6a3f26)

Mezi prvky, které jsou výchozím nastavení block patří:

- `<p>`
- nadpisy
- seznamy
- `<div>`



## Inline

Prvky s `display: inline` se zobrazují vedle sebe na stejném řádku.

![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/01502d06-fd12-4138-b79e-5114c5201e81)


Mezi prvky, které jsou ve výchozím nastavení inline patří:

- `<img>`
- `<span>`


## Inline-block

Problém s inline je, že prvky neakceptují, pokud jim nastavíme `width` nebo `height`. Nelze u nich měnit výšku a šířku, nemůže tak vytvořit například tvary.

Jako řešení existuje `display: inline-block` - prvky s tímto nastavením zůstavají na stejném řádku ale umožňují nastavení width a height.


![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/b30085eb-de59-41eb-a379-6d01f7b300c2)


## Demo

Na [této stránce](https://js-trebesin.github.io/visualize-code/ivb/ivb.html)  si můžete vyzkoušet chování divů v případě nastavení block, inline a inline-block
