# Asynchronní funkce

Javascript běžně vykonává kód řádek po řádku, aneb synchronně. V některých případech však tento způsob není vyhovující - například, pokud komunikujeme se vzdáleným serverem, od kterého požadujeme data a odpověď serveru trvá určitou dobu, náš kód bude v tuto chvíli pozastaven a zabrzdí načítání celé stránky. V takovémto případu chceme, aby tento kód počkal bokem, na pozadí a provedl se až když bude mít všechny informace a instrukce. Takovému principu říkáme **asynchronní programování**.

### Příklady využití asynchronního kódu

* čekání na dopověď API
* čekání na server
* setTimetout
* čtení/zápis do souboru

## Tradiční přístup - Callback a Promise

První způsob použití byl tzv. *callback* - funkce, která spustí další funkci

```js
ziskejData(function(data) {
  console.log("Data jsou:", data)
})
```
Později byla do Javascriptu přidána možnost vytvořit `Promise` (slib, že nějaká hodnota bude získána v budoucnu - Promise tedy nemá hodnotu okamžitě, získá ji později)


```js
fetch("https://ukazka.api.cz")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Chyba:", error))
```

V příkladu výše spouštíme funkci `fetch`, která fetchne (přinese) data z nějakého vzdáleného serveru. Na tu navážeme funkcí `then`, kde odpověď změníme na JSON, na to navážeme znovu funkcí `then`, kde data vypíšeme do konzole a nakonec na druhé then navážeme funkcí `catch`, která nás upozorní chybu, kdyby k ní náhodou došlo.
Celý kód výše by mohl být na jednom řádku, `.` tečkou navazujeme funkce na sebe. Kód odsazujeme pouze kvůli čitelnosti.

```js
fetch("https://ukazka.api.cz").then(response => response.json()).then(data => console.log(data)).catch(error => console.error("Chyba:", error))
```

*Toto řetězení však není nejpřehlednější, proto pozdější update Javascriptu přišel s metodou async/await, která je dnes obecně preferována a na kterou se budeme soustředit i my.*

## `async` / `await`

Async / await je moderní způsob práce s asynchronním kódem, který nám zjednodušeuje práce s Promisy.

### Základní syntax

```js
async function necoUdelej() {
  const vysledek = await nejakyPromise()
  console.log(vysledek)
}
```

Asynchronní funkci vytvoříme stejně, jako klasickou funkci, jen na začátek napíšeme klíčové slovo `async`.
Pokud chceme pracovat s Promisem - aneb výsledkem, který nebude okamžitý - musíme použít klíčové slovo `await`. Await lze použít pouze uvnitř asynchronních funkcí.
Každá asynchronní funkce automaticky vrací Promise, tzn, pokud má async funkce nějaké return a my s ním chceme dále pracovat, budeme muset použít `await`.


### Ukázka použití z hodin

```js
const mojeApi = "https://catfact.ninja/fact"

async function ziskejData(adresa) {
    try {
        const odpoved = await fetch(adresa)

        if (!odpoved.ok) {
            throw new Error("Něco je špatně")
        }

        return await odpoved.json()

    } catch (error) {
        console.error("Chyba při zpracování dat", error)
    }
}

async function zobrazData() {
    const kociciFakta = await ziskejData(mojeApi)

    if (kociciFakta) {
        console.log(kociciFakta["fact"])
    }
}

zobrazData()

```

**Stejný kód s komentáři**

```js
const mojeApi = "https://catfact.ninja/fact"


async function ziskejData(adresa) {
    // try / catch vyzkouší operaci a případně zachytí chybu
    // try / catch není pro kód nezbytný, je ale standard jej používat
    try {
        // ulož výsledek fetchnutí pod proměnnou odpoved
        // fetch je asynchronní proto klíčové slovo await
        const odpoved = await fetch(adresa)

        // vykřičník na začátku znamená opak, aneb když je odpoved.ok !== true
        // fetch vrací ok: true pokud se provede správně (dostaneme zpět 200 ok)
        // pokud odpoved.ok je false vytvoř nový error
        if (!odpoved.ok) {
            throw new Error("Něco je špatně")
        }

        // pokud se nesplnila podmínka, aneb odpoved.ok je true tak vrať odpověď převedenou z jsonu
        // .json() je asynchronní, proto await
        return await odpoved.json()

        // pokud kód v try nefunguje, vypiš do konzole chybu
    } catch (error) {
        console.error("Chyba při zpracování dat", error)
    }
}

// jelikož získávání dat je asynchronní, jejich zobrazení musí být též asynchronní
// protože musí počkat, až se data získají
async function zobrazData() {
    // pod proměnnou kociciFakta ulož výsledek z funkce, která data získává
    // ziskejData() je asynchronní, proto await
    const kociciFakta = await ziskejData(mojeApi)

    // pokud kociciFakta existují (rovnají se true) tak je vypiš do konzole
    // nevypisuj celý object ale jen konkrétní fakt
    if (kociciFakta) {
        console.log(kociciFakta["fact"])
    }
}

// funkci zobrazData() je potřeba zavolat, aby se provedla
zobrazData()
```