# margin, padding, border... border-box

![image](https://github.com/JS-Trebesin/Gympl-21/assets/84028625/745e6236-fb72-4df3-900a-b164c5393420)


## Margin

`margin` je prostor mezi jedním prvkem a dalším prvky. Jak daleko jsou od sebe, jaký je mezi nimi odstup.

Když nastavíme prvku `margin`, začne se chovat stydlivě a bude si održovat odstup od ostatních.

Margin můžeme nastavit pro každou stranu zvlášť:

```css
.ukazka {
    margin-top: 10px;
    margin-right: 10px;
    margin-bottom: 10px;
    margin-left: 10px;
}
```

nebo najednou

```css
.ukazka {
    margin: 10px;
    /* 10 px pro margin všemi směry */
}
```

popř. pokud máme rozdílné hodnoty tak můžeme nastavit:

```css
.ukazka {
    margin: 10px 15px 20px 25px;
    /* v pořadí top right bottom left - aneb od shora po směru hodin. ručiček*/
}
```

nebo se často používají dvě hodnoty

```css
.ukazka {
    margin: 10px 20px;
    /* 10px pro top a bottom, 20px pro right a left*/
}
```

## Padding

`padding` je vycpávka, představuje vnitřní prostor mezi obsahem prvku a jeho `border` (okrajem).

Pro `padding` platí stejné, co pro `margin`, také `padding` můžeme nastavit pro každou stranu zvlášť.

```css
.ukazka {
    padding: 10px;
    /* 10 px pro padding všemi směry */
}
```

popř. pokud máme rozdílné hodnoty tak můžeme nastavit:

```css
.ukazka {
    padding: 10px 15px 20px 25px;
    /* v pořadí top right bottom left - aneb od shora po směru hodin. ručiček*/
}
```

nebo se často používají dvě hodnoty

```css
.ukazka {
    padding: 10px 20px;
    /* 10px pro top a bottom, 20px pro right a left*/
}
```

## Border

`border` je okraj prvku.
Nejdůležitější hodnoty pro `border` jsou:

-   `border-width` -> tloušťka borderu
-   `border-style` -> jeho styl, např. plná čára nebo přerušovaná
-   `border-color` -> jeho barva

Tyto hodnoty můžeme napsat zvlášť

```css
.ukazka {
    border-width: 2px;
    border-style: solid;
    border-color: black;
}
```

nebo zkráceně

```css
.ukazka {
    border: 2px solid black;
/* Okraj: šířka 2px, plnou čárou a černý */

}
```

## Border-box

Představme si prvek, který má šířku 200px, border 5px a padding 20px. Jeho celková šířka pak bude 200 + 5 + 20 = 225px.

```css
.ukazka {
    width: 200px;
    border: 5px solid black;
    padding: 20px;
    /* celková šířka prvku = 225px */
}
```

`box sizing: border-box` nám usnadňuje práci. Nastaví prvek tak, aby se jeho celková šířka řídila hodnotou nastavenou u `width`, tedy 200px, a to bude jeho celková šířka včetně paddingu a borderu.

```css
.ukazka {
    box-sizing: border-box;
    width: 200px;
    border: 5px solid black;
    padding: 20px;
    /* celková šířka prvku = 200px */
}
```

To samé platí pro výšku. Toto nám usnadní práci, pokud na šířce prvku závisí postavení ostatních prvků na mé stránce. Nebo když se v budoucnu rozhodnu změnit border či padding, nerozhodí to rozvržení webové stránky. Celkově tedy usnadňuje práci s rozložením prvků a zabraňuje nečekaným změnám v rozměrech. Z toho důvodu se velmi často nastavuje `box-sizing: border-box` pro všechny prvky na stránce (* znamená nastav to pro vše).

```css
* {
    box-sizing: border-box;
}
```

