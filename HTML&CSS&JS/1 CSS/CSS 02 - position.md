# Position

Vlastnost `position` v CSS umožňuje měnit umístění prvků na stránce.

V CSS můžeme nastavit tyto pozice:

-   static
-   relative
-   absolute
-   fixed
-   sticky

## static

Position static je výchozí (defaultní) nastavení všech prvků v CSS. Prvek s `position: static` zůstává na svém původním místě a nelze jeho pozici měnit

## relative

`position: relative` nám umožňuje měnit pozici daného prvku a nastavit mu hodnoty:

-   top
-   bottom
-   right
-   left

```css
.jednicka {
    position: relative;
    top: 30px;
    left: 50px;
}

/*  prvek bude 30px od shora a 50px zleva od své původní pozice */
```

<img src="https://github.com/JS-Trebesin/Gympl-21/assets/84028625/ed3faa60-10b5-4a7b-89c3-390b6c5fe1a7" alt="drawing" width="500"/>

Pomocí `position: relative` říkáme, jak daleko bude prvek relativně od své původní pozice (na obrázku výše označeno bíle)

## absolute

Asi nejčastěji používaná `position: absolute` umožňuje umístit prvek nezávisle na jeho původní pozici. Absolute "vytrhne" prvek z dokumentu a způsobí, že ostatní prvky okolo něj jej začnou ignorovat. Opět můžeme nastavit hodnoty:

-   top
-   bottom
-   right
-   left

```css
.nadrazeny-div {
    position: relative;
}

.jednicka {
    position: absolute;
    top: 30px;
    left: 50px;
}
```

Pomocí `position: absolute` říkáme, kde se bude nacházet v poměru ke svému nejbližšímu nadřazenému prvku s `position` jinou, než je `static`.

Tzn. aby `position: absolute` fungovala správně, je potřeba nastavit nadřazený prvek (parent) na `position: relative` - relative bez dalšího nastavení směru sama o sobě nezpůsobí změnu, ale umožní prvku s classou `.jednicka` upravit umístění 30px zhora a 50px zleva od svého parenta.

Pokud by měl parent `position: static` (což má defaultně), `top` a `left` u `.jednicka` by se počítalo od celého `body`.

<img src="https://github.com/JS-Trebesin/Gympl-21/assets/84028625/8b3b81e7-4fe3-4182-81da-01a983167eb6" alt="drawing" width="500"/>

Ostatní prvky začali jedničku ignorovat a dvojka se tedy posunula na její původní místo.

## fixed

`position: fixed` "přibije" prvek k dokumentu a udržuje jej na stejném místo v dokumentu, i když jím scrollujeme. Nastavení směru (top, right, bottom, left) u fixed vždy platí ve vztahu k celému body.

```css
.jednicka {
    position: fixed;
    top: 30px;
    left: 50px;
}
```

<img src="https://github.com/JS-Trebesin/Gympl-21/assets/84028625/18e4de71-e340-4d51-a1e3-7b02a66bac58" alt="drawing" width="500"/>

## sticky

`position: sticky` se chová jako `relative` do té doby, dokud na stránce nescrollujeme níže. Pokud dojde ke scrollování, prvek "přilepí" k hornímu okraji stránky a začne se chovat jako `fixed`.

```css
.jednicka {
    position: sticky;
    top: 30px;
    left: 50px;
}
```

<img src="https://github.com/JS-Trebesin/Gympl-21/assets/84028625/9f2d0643-03b9-4214-850a-f9d278f6fddb" alt="drawing" width="500"/>

## Demo

Na [této stránce](https://js-trebesin.github.io/visualize-code/positions/positions.html) si můžete vyzkoušet chování divů v případě nastavení position static, relative a absolute
