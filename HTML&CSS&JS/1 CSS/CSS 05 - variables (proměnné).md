# Proměnné v CSS

Stejně jako v programovacích jazycích, i v CSS můžeme využívat proměnné (variables).

Pod proměnnou můžeme schovat hodnotu a později ji použít, aneb můžeme dát nějaké hodnotě (např. specifické barvě) vlastní přezdívku a později ji zavolat touto přezdívkou - nemusíme si tak pamatovat složitou hodnotu.

Proměnné se obvykle definují pro celý dokument, což znamená, že je vytváříme na úrovni rootu pomocí dvou pomlček: `--nazev-promenne: hodnota;`

```css
:root {
    --svetle-zelena: #7ae582;
}
```

Barvu poté použiji pomocí klíčového slova `var(--nazev-promenne)`

```css
:root {
    --svetle-zelena: #7ae582;
}

h1 {
    color: var(--svetle-zelena);
}
```

Výše uvedený kód obarví hlavní nadpis vybranou barvou. Nemusím si pamatovat, že mnou vybraná barva má hex kód #7AE582, ale stačí použít mnou zvolenou přezídku --svetle-zelena

Takto mohu proměnnou zavolat pro kterýkoliv další prvek/classu/id a usnadnit si práci, pokud chci mít konzistentní design mé webové stránky.

Proměnné nemusíme používat pouze pro barvy, ale pro kteroukoliv hodnotu.

Příklad:
Chci, aby pod každým textem byla mezera 50px.

```css
:root {
    --odsazeni: 50px;
}

h1 {
    margin-bottom: var(--odsazeni);
}

h2 {
    margin-bottom: var(--odsazeni);
}

p {
    margin-bottom: var(--odsazeni);
}
```

Pokud se později rozhodnu, že odsazení 50 pixelů se mi nelíbí a stránka vypadá lépe, pokud použiji odsazení 100px, stačí změnit pouze hodnotu u proměnné a nemusím přepisovat margin u všech prvků, kde jsem tuto hodnotu použil.

Stačí pak přepsat `--odsazeni`

```css
:root {
    --odsazeni: 100px;
}
```

a hodnoty u h1, h2 a p už měnit nemusím.

### Pokročilejší použití - lokální proměnné

Proměnnou lze lokálně upravit pro specifický prvek. Například, pokud bych se rozhodl, že můj největší nadpis bude mít dvojnásobné odsazení, mohu u něj proměnnou `--odsazeni` přepsat.

```css
:root {
    --odsazeni: 50px;
}

h1 {
    /* funkce calc() umožňuje používat matematické výpočty v CSS */
    --odsazeni: calc(2 * var(--odsazeni));
    margin-bottom: var(--odsazeni);
}

h2 {
    margin-bottom: var(--odsazeni);
}

p {
    margin-bottom: var(--odsazeni);
}
```

V tomto příkladu jsme pro prvek h1 upravili proměnnou `--odsazeni` na dvojnásobek její původní hodnoty. Pokud změním `--odsazeni` u rootu na 100px, u h1 se automaticky změní na 200px.
