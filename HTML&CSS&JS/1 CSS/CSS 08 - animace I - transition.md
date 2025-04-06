# CSS Transitions

CSS transitions umožňují plynulé přechody mezi různými stavy elementu. Pomocí nich můžeme vytvářet jednoduché animace.

## Základní použití

```css
.element {
    transition: property duration timing-function delay;
}
```

-   `property`: vlastnost, kterou chceme animovat (např. color, width, opacity)
-   `duration`: doba trvání přechodu (např. 0.5s, 200ms)
-   `timing-function`: průběh animace (např. ease, linear, ease-in, ease-out)
-   `delay`: zpoždění před začátkem animace

## Příklad

```css
.button {
    background-color: blue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: red;
}
```

## Více vlastností najednou

```css
.element {
    transition: background-color 0.3s ease, transform 0.5s ease-in-out;
}
```

## Vlastnosti pro transition

Můžete použít transition na různé CSS vlastnosti, například:

-   color
-   background-color
-   width, height
-   opacity
-   transform

## Transform a Translate

Transform je často používán s transitions pro pohyb nebo transformaci elementu.

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translate(50px, 0);
}
```

Nebo samostatně `translate`:

```css
.element {
    transition: translate 0.5s ease-in-out;
}

.element:hover {
    translate: 20px 20px;
}
```

## Doporučené materiály:

https://www.youtube.com/watch?v=YszONjKpgg4
