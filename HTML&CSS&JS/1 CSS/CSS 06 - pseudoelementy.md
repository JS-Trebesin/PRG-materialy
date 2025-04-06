# Pseudoelementy v CSS

Pseudoelementy jsou speciální selektory v CSS, které umožňují stylovat určité části elementu nebo vkládat obsah před nebo za element. Pseudoelementy zapisujeme s dvojitou dvojtečkou `::before`. Zde jsou nejdůležitější pseudoelementy:

## ::before a ::after

Tyto pseudoelementy umožňují vložit obsah před nebo za vybraný element.

```css
.ukazka::before {
    content: "Před ";
    color: red;
}

.ukazka::after {
    content: " Po";
    color: blue;
}
```

## Další pseudoelementy

`::before` a `::after` jsou nejpoužívanější pseudoelementy, nicméně existují i další, například:

-   `::first-line`: upraví první řádek textu
-   `::first-letter`: upraví první písmenko textu
-   `::selection`: upraví část textu, kterou označil uživatel
-   `::marker`: upraví odrážku nebo číslo v seznamu
