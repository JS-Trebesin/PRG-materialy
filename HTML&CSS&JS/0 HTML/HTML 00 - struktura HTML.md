# Struktura HTML

## Příklad

Diagram

```
                        ┌──────┐
                        │ body │
                        └───┬──┘
        ┌───────────────────┴───────────────────┐
     ┌──┴──┐                                 ┌──┴──┐
     │ div │                                 │ div │
     └──┬──┘                                 └──┬──┘
  ┌─────┼─────┬─────┐                           │
┌─┴─┐ ┌─┴─┐ ┌─┴─┐ ┌─┴─┐                       ┌─┴─┐
│h1 │ │ p │ │h2 │ │ p │                       │ul │
└───┘ └───┘ └───┘ └───┘                       └─┬─┘
                                          ┌─────┼─────┐
                                        ┌─┴─┐ ┌─┴─┐ ┌─┴─┐
                                        │li │ │li │ │li │
                                        └───┘ └───┘ └───┘

```

HTML

```html
<body>
    <div>
        <h1></h1>
        <p></p>
        <h2></h2>
        <p></p>
    </div>
    <div>
        <ul>
            <li></li>
            <li></li>
            <li></li>
        </ul>
    </div>
</body>
```

**Parent** (rodič) je prvek, který je ve struktuře HMTL přímo nad určitým prvkem.

V příkladu níže platí, že `ul` je parent pro `li`. Podobně by ale platilo, že `div` je parent pro `ul`, `body` je parent pro `div`.

Prvek, který se nachází uvnitř jiného prvku je jeho **child** (dítě). `li` je child `ul`, `ul` je child `div`, `div` je child `body`

Prvky vedle sebe jsou **siblings** (sourozenci). `li` jsou si navzájem siblings. `h1` je sibling `p`, atd. Siblings mají stejného parenta.

```
                        ┌──────┐
                        │ body │
                        └───┬──┘
        ┌───────────────────┴───────────────────┐
     ┌──┴──┐                                 ┌──┴──┐
     │ div │                                 │ div │
     └──┬──┘                                 └──┬──┘
  ┌─────┼─────┬─────┐                           │
┌─┴─┐ ┌─┴─┐ ┌─┴─┐ ┌─┴─┐                       ┌─┴─┐
│h1 │ │ p │ │h2 │ │ p │                       │ul │ <--- parent pro <li>
└───┘ └───┘ └───┘ └───┘                       └─┬─┘
                                          ┌─────┼─────┐
                                        ┌─┴─┐ ┌─┴─┐ ┌─┴─┐
                                        │li │ │li │ │li │ <--- child <ul>
                                        └───┘ └───┘ └───┘
                                          ↑     ↑     ↑
                                          └─────┼─────┘
                                                |
                                             siblings
```

**Pojmy _parent_, _child_, _sibling_ jsou důležité, protože v jazycích CSS a Javascript se objevují příkazy, které právě tyto pojmy obsahují**
