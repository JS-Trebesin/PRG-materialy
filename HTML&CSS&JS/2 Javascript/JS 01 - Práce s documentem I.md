# Upravování HTML pomocí Javascriptu

## Označení HTML prvku v Javascriptu

_**Podobně jako v CSS, také v Javascriptu potřebuji nejprve označit (selectnout) HTML prvek, kterým budu chtít manipulovat pomocí kódu.**_

_K tomu máme dvě možnosti:_

### 1. querySelector

pomocí `document.querySelector("selectorPrvek")` mohu označit HTML prvek, buď pomocí id ("#nazev") nebo classy (".nazev") nebo celý prvek ("body") - pozor, je důležité dodržovat uvozovky

![image](https://user-images.githubusercontent.com/84028625/225417935-f000d07e-1d79-4d3f-89b0-8e5cc27807f0.png)

### 2. getElementByID

pomocí `document.getElementByID("prvek")` mohu označit prvek pouze pomocí id => querySelector je tedy univerzálnější, u getElementById ale nemusím používat symbol #

![image](https://user-images.githubusercontent.com/84028625/225417666-a08f4eae-f55c-4197-8317-3050cc842b5f.png)

-   Slovo `document` je v Javascriptu označení pro naší webovou stránku (HTML) -> `document.getElementByID("text")` bychom mohli přeložit jako _"z HTML zvol prvek, který má ID "text"_

---

**Jak u querySelectoru tak u getElementById musí název v závorce odpovídat nastavení z HTML**

![image](https://user-images.githubusercontent.com/84028625/225419835-9eda620b-95f2-4b91-b2c0-0a58430d8949.png)

---

**Proměnná, pod kterou schováváme označený HTML prvek, může, ale nemusí být mít stejný název jako má id (popř.) classa v HTML (viz příklady níže)**

_(aneb název vlevo nemusí být stejný jako v HTML, ale to, co je v závorce vpravo musí být stejné jako id/classa v HTML)_

![image](https://user-images.githubusercontent.com/84028625/225421099-f51ce95d-704d-459d-92a2-d4d735d31d0e.png)

## Úprava zvoleného prvku

### innerText

Pomocí prvek.innerText mohu změnit jeho text

![image](https://user-images.githubusercontent.com/84028625/225423846-b6d46eb3-ebb9-470d-b90d-883b1dd9f6e2.png)

**Název proměnné, který jsem zvolili pak používáme v rámci další práce v Javascriptu**

---

### style

Podobným způsobem můžeme upravit také CSS daného prvku, využijeme k tomu .style.vlastnost

![image](https://user-images.githubusercontent.com/84028625/225427207-529ec1c5-9c7a-4570-8bef-73195b39f3d3.png)

---

### value

Pokud mám input v HTML, mohu přečíst jeho hodnotu (to, co tam uživatel v HTML zadá), pomocí označení .value

![image](https://user-images.githubusercontent.com/84028625/225431575-bbfde64d-9b5c-4311-b090-29344f1722f3.png)

S touto hodnotou mohu dále pracovat, třeba ji schovat pod nějakou proměnnou

![image](https://user-images.githubusercontent.com/84028625/225431721-0a0b28f8-5561-451a-af63-66fcb3b2bc72.png)

nebo třeba touto hodnotou přímo přepsat text nějakého prvku

![image](https://user-images.githubusercontent.com/84028625/225432212-bde0294b-3c85-4f68-9036-86c4d8554919.png)
