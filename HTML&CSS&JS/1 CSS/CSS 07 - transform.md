# CSS Transform

CSS transform vlastnost umožňuje měnit pozici, velikost a tvar elementů bez narušení normálního toku dokumentu.

## Základní použití

```css
.element {
    transform: funkce(hodnota);
}
```

## Hlavní transformační funkce

1. **translate()** - posun elementu
2. **scale()** - změna velikosti
3. **rotate()** - otočení
4. **skew()** - zkosení

## Příklady použití

### Translate (posun)

Starší zápis:

```css
.box {
    transform: translateX(50px) translateY(20px);
    /* nebo */
    transform: translate(50px, 20px);
}
```

### Scale (změna velikosti)

```css
.box {
    transform: scale(1.5); /* zvětšení o 50% */
}
```

### Rotate (otočení)

```css
.box {
    transform: rotate(45deg);
}
```

### Skew (zkosení)

```css
.box {
    transform: skew(10deg, 20deg);
}
```

## Nový zápis:

Nově v CSS můžeme _translate_, _rotate_ a _scale_ zapisovat přímo:

```css
.box {
    translate: 50px 20px;
}
/* Pozn: první hodnota je pro osu x, druhá pro osu y */
```

```css
.box {
    rotate: 45deg;
}
```

```css
.box {
    scale: 1.5;
}
```

## Kombinování transformací

Můžete kombinovat více transformací v jednom příkazu:

```css
.box {
    transform: translate(50px, 20px) rotate(45deg) scale(1.5);
}
```

nebo

```css
.box {
    translate: 50px, 20px;
    rotate: 45deg;
    scale: 1.5;
}
```

## Pokročilejší transformace:

### 3D transformace

CSS transform podporuje i 3D transformace:

```css
.box {
    transform: rotateX(45deg) rotateY(30deg) translateZ(100px);
}
```

### Transform-origin

Určuje výchozí bod pro transformace:

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

## Doporučené materiály:

https://www.youtube.com/watch?v=rzD-cPhq02E
