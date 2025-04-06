# CSS Stíny

CSS nabízí dva hlavní typy stínů: box-shadow pro elementy a text-shadow pro text.

## Box Shadow

Box-shadow přidává stín kolem celého elementu.

### Základní syntaxe:

```css
.element {
    box-shadow: h-offset v-offset blur spread color;
}
```

-   `h-offset`: horizontální posun stínu
-   `v-offset`: vertikální posun stínu
-   `blur`: rozmazání stínu (volitelné)
-   `spread`: rozšíření stínu (volitelné)
-   `color`: barva stínu

### Příklady:

```css
/* Jednoduchý stín */
.box1 {
    box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.3);
}

/* Stín s rozšířením */
.box2 {
    box-shadow: 0 0 10px 5px #888888;
}

/* Vnitřní stín */
.box3 {
    box-shadow: inset 0 0 10px #000000;
}

/* Více stínů */
.box4 {
    box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.3), inset 0 0 5px rgba(0, 0, 0, 0.5);
}
```

## Text Shadow

Text-shadow přidává stín za text.

### Základní syntaxe:

```css
.text {
    text-shadow: h-offset v-offset blur color;
}
```

-   `h-offset`: horizontální posun stínu
-   `v-offset`: vertikální posun stínu
-   `blur`: rozmazání stínu (volitelné)
-   `color`: barva stínu

### Příklady:

```css
/* Jednoduchý text stín */
.text1 {
    text-shadow: 2px 2px 4px #000000;
}

/* Světelný efekt */
.text2 {
    color: #ffffff;
    text-shadow: 0 0 10px #00ff00;
}

/* Více text stínů */
.text3 {
    text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
}
```
