# Flexbox

Flexbox usnadňuje uspořádání prvků na webové stránce.

Flex umožňuje ovládat rozložení prvků na jedné ose - prvky se seřadí buď vertikálně (ve sloupci - column) nebo horizontálně (v řadě, row).

## Základní nastavení flexu

### display: flex

Pokud chceme prvky zarovnat pomocí flexu v CSS nastavíme hodnotu `display: flex`

**! Důležité: Vlastnost 'flex' nastavujeme nadřazenému kontejneru, ve kterém jsou prvky, které chceme uspořádat !**

_Příklad_

-   máme tři divy, které chceme uspořádat

![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/6c26443c-0039-449a-a473-12c0f104a190)

HTML

```html
<body>
    <div class="parent">
        <div class="child"></div>
        <div class="child"></div>
        <div class="child"></div>
    </div>
</body>
```

CSS

-   V CSS nastavíme `display: flex` jejich nadřazenému prvku, jejich parentu

```css
.parent {
    display: flex;
}
```

Výsledek

![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/06e4d805-de9e-4943-b00f-876716191de9)

## Zarovnání prvků

### flex-direction

Vlastnost `flex-direction` určuje, zda budou prvky umístěny vedle sebe (row) nebo pod sebou (column)

Defaultní nastavení je `flex-direction: row` tzn. pokud `flex-direction` explicitně nenastavíme, prvky se seřadí do řady. Pokud chceme prvky pod sebou, nastavíme `flex-direction: column`

```css
flex-direction: row;
/* seřadí prvky vedle sebe */

flex-direction: column;
/* seřadí prvky pod sebe */
```

### justify-content

`justify-content` řadí prvky na hlavní ose.

Tzn. pokud máme `row` `justify-content` nastavuje chování na ose x (horizontálně), pokud jsme nastavili direction `column`, `justify-content` nastavuje chování na ose y (vertikálně)

Možná nastavení pro `justify-content`:

-   flex-start: prvky jsou zarovnány na začátek kontejneru

-   flex-end: prvky jsou zarovnány na konec kontejneru

-   center: prvky jsou zarovnány na střed

-   space-between nebo space-around nebo space-evenly: mezi prvky jsou mezery

### align-items

`align-items` řadí prvky na vedlejší ose.

Pro `row;` nastavuje chování na ose y, pro `column`, ose x (vertikálně)

Možná nastavení pro `align-items`:

-   flex-start

-   flex-end

-   center

-   baseline

## Centrování prvků

Pomocí `justify-content` a `align-items` můžeme snadno zarovnat prvek/prvky na střed

```css
.kontejner-jehoz-prvky-chci-zarovnat {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

_Výsledek_

![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/e0949808-136e-451e-9ccb-9a8e76d0040d)

## Další zdroje

Flex má další možná pokročilá nastavení, co vše můžete pomocí flexu nastavit zjistíte například na:

-   [W3 schools](https://www.w3schools.com/css/css3_flexbox.asp)

-   [Mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)

-   popř. česky na stránce Vzhůru dolů [tady](https://www.vzhurudolu.cz/prirucka/css-flex) a [tady](https://www.vzhurudolu.cz/prirucka/css-flexbox)

-   nebo vám o tom rád poví chatGPT
