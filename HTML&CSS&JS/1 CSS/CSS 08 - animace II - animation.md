# CSS Animations

CSS animations umožňují vytvářet komplexnější animace bez použití JavaScriptu. Na rozdíl od transitions, animations mohou běžet automaticky a opakovaně.

## Základní použití

1. Definujte keyframes:

```css
@keyframes nazev-animace {
    0% {
        /* počáteční stav */
    }
    50% {
        /* stav v polovině animace */
    }
    100% {
        /* konečný stav */
    }
}
```

2. Použijte animaci na element:

```css
.element {
    animation: nazev-animace duration timing-function delay iteration-count
        direction fill-mode;
}
```

Příklad:

```css
@keyframes blink {
    0%,
    100% {
        opacity: 1;
    }
    50% {
        opacity: 0;
    }
}

.blinking-text {
    animation: blink 2s ease-in-out infinite;
}
```

## Vlastnosti animation

-   `animation-name`: Název keyframes
-   `animation-duration`: Doba trvání jednoho cyklu
-   `animation-timing-function`: Průběh animace (např. ease, linear)
-   `animation-delay`: Zpoždění před začátkem
-   `animation-iteration-count`: Počet opakování (nebo `infinite`)
-   `animation-direction`: Směr animace (normal, reverse, alternate)
-   `animation-fill-mode`: Stav před/po animaci (forwards, backwards, both)

## Více animací najednou

```css
.element {
    animation: slide 3s ease infinite, fade 2s linear infinite;
}
```

Úkol: Vytvořte animaci, která bude kontinuálně měnit barvu pozadí elementu mezi třemi různými barvami.

## Doporučené materiály:

https://www.youtube.com/watch?v=YszONjKpgg4
