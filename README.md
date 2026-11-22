# Herkansing JavaScript: Webshop

## Wat ga je maken?

De opdracht is een **webshop** maken. De HTML en CSS (het design) krijg je van de docent. Je schrijft alleen de JavaScript. De producten komen niet uit je eigen HTML, maar uit een **API** op internet. Je schrijft dus geen producten met de hand in je code.

Een bezoeker van de webshop kan:

1. alle producten zien,
2. een product zoeken op naam,
3. producten filteren op categorie,
4. producten sorteren op prijs,
5. de details van één product bekijken,
6. producten opslaan als favoriet (met een hartje). De favorieten blijven bewaard, ook als je de pagina ververst.

Je hoeft **geen** echte betaling, inlogsysteem of database te maken. Het gaat om de JavaScript.

**Kort gezegd:** de opdracht is af als alle MOET-user stories (verderop) werken. De EXTRA-stories zijn voor een hoger cijfer.


| | Alleen | Met z'n tweeën |
| --- | --- | --- |
| MOET-stories | US1, US2, US3, US4, US6, US7 | Alle 10 (US1 t/m US10) |
| EXTRA-stories | US5, US8, US9, US10 en E1 t/m E4 | E1 t/m E4 |

Bij elke user story die je alleen niet hoeft te maken, staat **(alleen: extra)**.

## Aan de slag

1. Klik rechtsboven op **Use this template** en maak een eigen repository.
2. Werk je met z'n tweeën? Dan maakt één persoon de repository en voegt de ander toe als collaborator: **Settings → Collaborators → Add people**. Daarna kunnen jullie allebei pushen.
3. Clone de repository naar je eigen computer.
4. Open de map in VS Code en start `index.html` met de extensie **Live Server**.
5. Zet de site online met **GitHub Pages** (Settings → Pages → branch `main`).

**Bestanden in deze repository**

| Bestand | Wat is het? | Mag je het veranderen? |
| --- | --- | --- |
| `index.html` | De pagina, met comments en voorbeeld-HTML | Nee |
| `style.css` | Het design | Nee |
| `script.js` | Hier schrijf je al je JavaScript | Ja! |
| `README.md` | Deze opdracht | Alleen de eindcheck afvinken |

## Spelregels en planning

Je hebt **4 weken** de tijd. Werk je met z'n tweeën? Dan schrijven jullie allebei evenveel JavaScript: iedereen maakt 5 van de 10 MOET-stories (zie de taakverdeling onderaan).

**Regels**

- Je krijgt van de docent de **startbestanden**: `index.html`, `style.css` en een leeg `script.js`. Die staan al in deze repository.
- Aan `index.html` en `style.css` verander je **niets**. Je werkt alleen in `script.js`.
- In `index.html` staan comments met de id's die je kunt gebruiken en voorbeelden van de HTML die je met JavaScript moet maken (de productkaart en de details). Lees die eerst goed.
- Je werkt in één GitHub-repository. Met z'n tweeën? Dan maakt ieder commits met zijn eigen account.
- Commit minimaal **2 keer per week** (met z'n tweeën: per persoon), met een duidelijke boodschap. Dus niet `update` maar `zoekbalk werkt`.
- Code van internet of AI mag je alleen gebruiken als je het **zelf kunt uitleggen**. Bij de oplevering vraagt de docent dit.
- Gebruik **geen** libraries of frameworks (geen jQuery, React). Alleen gewone JavaScript.

**Weekplanning**

| Week | Alleen | Met z'n tweeën: persoon A | Met z'n tweeën: persoon B |
| --- | --- | --- | --- |
| 1 | US1, US2 | US1, US2 | US4 (begin: categorieën ophalen) |
| 2 | US3, US4 | US3 | US4 (af), US5 |
| 3 | US6, US7 | US9 | US6, US7 |
| 4 | Testen met de eindcheck, extra's, inleveren | US10 | US8 |

Ben je eerder klaar? Begin dan aan de EXTRA-stories.

Loop je een week achter? Meld het dan meteen bij je docent. Niet pas in week 4.

**Wat lever je in?**

1. De link naar je GitHub-repository.
2. De link naar de werkende website (bijvoorbeeld GitHub Pages).
3. De ingevulde **eindcheck** (onderaan deze README). Vink af door `[ ]` te veranderen in `[x]`.

In de laatste les laat je de webshop zien en leg je een stuk van je eigen code uit. Met z'n tweeën doet ieder dat voor zijn eigen code.

## De API: DummyJSON

Je gebruikt de gratis API van [DummyJSON](https://dummyjson.com/docs/products). Je hebt geen account of sleutel nodig. Open de links hieronder eerst in je browser, dan zie je hoe de data eruitziet.

| Wat wil je? | URL |
| --- | --- |
| Alle producten (194 stuks) | `https://dummyjson.com/products?limit=0` |
| Alle categorieën | `https://dummyjson.com/products/categories` |

**Let op 1:** de producten zitten niet direct in het antwoord, maar in `data.products`. Je krijgt dit terug:

```json
{
  "products": [
    {
      "id": 1,
      "title": "Essence Mascara Lash Princess",
      "description": "The Essence Mascara Lash Princess is a popular mascara...",
      "category": "beauty",
      "price": 9.99,
      "rating": 4.94,
      "stock": 5,
      "thumbnail": "https://cdn.dummyjson.com/..."
    }
  ],
  "total": 194
}
```

**Let op 2:** een categorie is een object met een `slug` en een `name`, bijvoorbeeld `{ "slug": "beauty", "name": "Beauty" }`. In een product staat bij `category` de **slug**. Die twee vergelijk je dus met elkaar.

**Belangrijk:** je haalt de producten **één keer** op en bewaart ze in een array, bijvoorbeeld `let alleProducten = []`. Zoeken, filteren en sorteren doe je daarna zelf in JavaScript met `filter()` en `sort()`. Je gebruikt dus niet de zoekfunctie van de API.

De producten zijn in het Engels. Dat is prima; je eigen teksten (knoppen, kopjes, meldingen) zijn in het Nederlands.

## Welke JavaScript moet je laten zien?

Alles wat je nodig hebt, staat op de [cheat sheet](https://meesterjson.nl/cheat-sheet/pages/javascript/). In de tabel zie je welk onderwerp je bij welke user story gebruikt.

| Onderwerp op de cheat sheet | Wat doe je ermee? | User story |
| --- | --- | --- |
| [Variables & Data Types](https://meesterjson.nl/cheat-sheet/pages/javascript/variables-datatypes.html) | `const` en `let` gebruiken, geen `var` | alle |
| [Functions](https://meesterjson.nl/cheat-sheet/pages/javascript/functions.html) | Je code opdelen in functies, zoals `toonProducten(lijst)` | alle |
| [JSON & Fetch](https://meesterjson.nl/cheat-sheet/pages/javascript/json.html) + [Async/Await](https://meesterjson.nl/cheat-sheet/pages/javascript/async-await.html) | Producten ophalen uit de API | US1 |
| [Error Handling](https://meesterjson.nl/cheat-sheet/pages/javascript/error-handling.html) | `try` / `catch` om je fetch | US10 |
| [Loops](https://meesterjson.nl/cheat-sheet/pages/javascript/loops.html) + [Modern Syntax](https://meesterjson.nl/cheat-sheet/pages/javascript/modern-syntax.html) | `forEach` of `for...of` en template literals voor de productkaarten | US2 |
| [DOM Manipulatie](https://meesterjson.nl/cheat-sheet/pages/javascript/dom-manipulatie.html) | Kaarten maken met `createElement` of `innerHTML` | US2, US8 |
| [Events & Listeners](https://meesterjson.nl/cheat-sheet/pages/javascript/events.html) | Reageren op typen, kiezen en klikken | US3 t/m US9 |
| [String Methods](https://meesterjson.nl/cheat-sheet/pages/javascript/string-methods.html) | `toLowerCase()` en `includes()` voor zoeken | US3 |
| [Arrays & Methods](https://meesterjson.nl/cheat-sheet/pages/javascript/arrays-methods.html) | `filter()` en `sort()` | US3, US4, US5 |
| [Conditionals](https://meesterjson.nl/cheat-sheet/pages/javascript/conditionals.html) | `if` / `else`, bijvoorbeeld: is dit product al favoriet? | US6, US10 |
| [classList](https://meesterjson.nl/cheat-sheet/pages/javascript/classlist.html) | Het hartje aan- en uitzetten met `toggle()` | US6 |
| [DOM & Local Storage](https://meesterjson.nl/cheat-sheet/pages/javascript/dom-local-storage.html) | Favorieten bewaren met `JSON.stringify()` en `JSON.parse()` | US7 |
| [Array Methods Extra](https://meesterjson.nl/cheat-sheet/pages/javascript/array-methods-extra.html) | `some()` of `find()` | US6, US9 |

**Afspraken over je code**

- Je schrijft al je code in `script.js`. (Alleen bij EXTRA E4 maak je meer bestanden.)
- Je gebruikt de **id's en classes uit `index.html`**. Je bedenkt geen eigen classes, want daar is geen CSS voor.
- Namen van variabelen en functies zeggen wat ze doen: `zoekInput`, niet `x`.
- Elke functie heeft een korte comment erboven: wat doet deze functie?
- Er staan **geen rode foutmeldingen** in de console (F12) als je de webshop gebruikt.

## User stories: MOET (voor een voldoende)

Een user story vertelt wat een bezoeker wil. Onder elke story staat een checklist: **je bent pas klaar als je alles kunt afvinken.** Werk ze op volgorde af, want ze bouwen op elkaar.

Werk je alleen? Dan hoef je de stories met **(alleen: extra)** niet te maken. Die tellen voor jou als EXTRA-story.

### US1: Producten ophalen uit de API

*Als bezoeker wil ik dat de webshop echte producten laat zien, zodat er iets te kopen valt.*

Je bent klaar als:

- [ ] Je haalt de producten op met `fetch()` en `async` / `await`.
- [ ] De producten worden bewaard in een array, bijvoorbeeld `alleProducten`.
- [ ] Je ziet in de console (F12) met `console.log()` dat er 194 producten zijn.
- [ ] De fetch zit in een eigen functie, bijvoorbeeld `haalProductenOp()`.

### US2: Producten tonen op de pagina

*Als bezoeker wil ik alle producten netjes naast elkaar zien, zodat ik kan rondkijken.*

Je bent klaar als:

- [ ] Elk product staat op een eigen **kaart** met: foto (`thumbnail`), naam (`title`), prijs (`price`) en categorie.
- [ ] De HTML van elke kaart is precies zoals de **voorbeeldkaart** in de comment onderaan `index.html` (`class="kaart"`, `class="kaart-titel"` enzovoort). Dan ziet hij er vanzelf goed uit.
- [ ] De prijs staat er zo: **€ 9,99** (met euroteken en komma).
- [ ] De kaarten worden door JavaScript gemaakt in een loop en komen in `#producten`.
- [ ] Je hebt één functie `toonProducten(lijst)` die elke lijst met producten op het scherm kan zetten. Die functie gebruik je straks steeds opnieuw.
- [ ] Staan de producten op het scherm? Dan verberg je de tekst "Producten laden..." in `#melding` met de class `verborgen`.

### US3: Zoeken op naam

*Als bezoeker wil ik een product zoeken op naam, zodat ik snel vind wat ik zoek.*

Je bent klaar als:

- [ ] Je gebruikt het zoekveld `#zoekveld`.
- [ ] Terwijl je typt, veranderen de producten meteen (event `input`). Je hoeft niet op een knop te drukken.
- [ ] Hoofdletters maken niet uit: "PHONE", "phone" en "Phone" geven hetzelfde resultaat.
- [ ] Je gebruikt `filter()`, `toLowerCase()` en `includes()`.
- [ ] Is het zoekveld leeg? Dan zie je weer alle producten.
- [ ] Is er niets gevonden? Dan staat in `#melding` de tekst "Geen producten gevonden".

### US4: Filteren op categorie

*Als bezoeker wil ik alleen producten uit één categorie zien, zodat ik niet door alles hoef te scrollen.*

Je bent klaar als:

- [ ] Je gebruikt de keuzelijst `#categorie`. Daar staat al de optie "Alle categorieën" in (met `value="alle"`).
- [ ] De andere opties maak je met JavaScript. Ze komen uit de API (`/products/categories`). Gebruik `slug` als `value` en `name` als tekst.
- [ ] Kies je een categorie, dan zie je alleen producten uit die categorie (event `change`).
- [ ] Kies je "Alle categorieën", dan zie je weer alles.

### US5: Sorteren op prijs (alleen: extra)

*Als bezoeker wil ik producten sorteren op prijs, zodat ik de goedkoopste of duurste bovenaan zie.*

Je bent klaar als:

- [ ] Je gebruikt de keuzelijst `#sorteren`. De opties hebben de waarden `standaard`, `laag-hoog` en `hoog-laag`.
- [ ] Bij "Prijs laag - hoog" staat het goedkoopste product linksboven.
- [ ] Bij "Prijs hoog - laag" staat het duurste product linksboven.
- [ ] Je gebruikt `sort()`.

### US6: Favoriet maken met een hartje

*Als bezoeker wil ik op een hartje klikken, zodat ik producten kan onthouden die ik leuk vind.*

Je bent klaar als:

- [ ] Op elke productkaart staat een hartje-knop (`class="hartje"`, zie de voorbeeldkaart).
- [ ] Klik je erop, dan wordt het hartje rood. Klik je nog een keer, dan is het weer grijs.
- [ ] Je doet dit met `classList.toggle("actief")`. De CSS voor `.actief` staat al klaar.
- [ ] Het `id` van het product wordt toegevoegd aan een array `favorieten`, of eruit gehaald.
- [ ] Een product kan **niet twee keer** in de favorieten staan.

### US7: Favorieten bewaren in localStorage

*Als bezoeker wil ik dat mijn favorieten blijven bestaan, zodat ik ze niet kwijt ben als ik de pagina ververs.*

Je bent klaar als:

- [ ] Elke keer dat de favorieten veranderen, sla je ze op in `localStorage` met `JSON.stringify()`.
- [ ] Als de pagina laadt, lees je ze weer uit met `JSON.parse()`.
- [ ] Test: maak 3 favorieten, druk op F5. De 3 hartjes zijn nog steeds rood.
- [ ] Is er nog niets opgeslagen (eerste bezoek)? Dan krijg je geen foutmelding, maar een lege lijst.

### US8: Mijn favorieten bekijken (alleen: extra)

*Als bezoeker wil ik al mijn favorieten bij elkaar zien, zodat ik snel kan kiezen.*

Je bent klaar als:

- [ ] Op de knop `#favorieten-knop` staat het aantal favorieten. Dat getal zet je in `#favorieten-aantal` en het klopt altijd.
- [ ] Klik je op die knop, dan zie je alleen je favoriete producten en staat in `#titel` "Mijn favorieten".
- [ ] Klik je op `#alle-producten-knop`, dan zie je weer alles en staat in `#titel` "Alle producten".
- [ ] Haal je een hartje weg in het favorietenoverzicht, dan verdwijnt dat product meteen uit het overzicht.
- [ ] Heb je geen favorieten? Dan staat in `#melding` "Je hebt nog geen favorieten".

### US9: Productdetails bekijken (alleen: extra)

*Als bezoeker wil ik meer informatie over een product zien, zodat ik weet of ik het wil hebben.*

Je bent klaar als:

- [ ] Klik je op een productkaart (niet op het hartje), dan opent de pop-up `#popup`. Dat doe je door de class `verborgen` weg te halen.
- [ ] In `#popup-details` staan: grote foto, naam, prijs, beschrijving (`description`), beoordeling (`rating`) en voorraad (`stock`). Gebruik de voorbeeld-HTML uit `index.html`.
- [ ] Je zoekt het product op in je array met `find()`. Je doet hiervoor **geen** nieuwe fetch.
- [ ] Klik je op `#popup-sluiten` (✕), dan gaat de pop-up dicht: je zet de class `verborgen` terug.

### US10: Laden en foutmelding (alleen: extra)

*Als bezoeker wil ik zien wat er gebeurt, zodat ik niet naar een lege pagina zit te kijken.*

Je bent klaar als:

- [ ] Tijdens het ophalen staat in `#melding` "Producten laden...". (Die tekst staat er al in de HTML.)
- [ ] Zijn de producten geladen, dan verberg je `#melding` met de class `verborgen`.
- [ ] Je fetch staat in een `try` / `catch`.
- [ ] Lukt het ophalen niet, dan staat in `#melding`: "Er ging iets mis. Probeer het later opnieuw." Geef `#melding` dan ook de class `fout`, dan wordt hij rood.
- [ ] Test: zet een tikfout in je API-URL. Zie je de foutmelding op de pagina? Haal de tikfout daarna weer weg.

## User stories: EXTRA (voor een hoger cijfer)

Begin hier **pas aan als alle MOET-stories af zijn**. Je mag zelf kiezen welke je doet. Werk je alleen? Dan tellen US5, US8, US9 en US10 ook als EXTRA-story.

### E1: Zoeken, filteren en sorteren tegelijk

*Als bezoeker wil ik zoeken, filteren en sorteren combineren, zodat ik precies vind wat ik wil.*

- [ ] Zoek je op "phone" en kies je categorie "smartphones", dan zie je alleen smartphones met "phone" in de naam.
- [ ] Daarna sorteren op prijs werkt ook, zonder dat zoeken of filteren verdwijnt.
- [ ] De knop `#wis-filters-knop` zet alles terug. Haal met JavaScript de class `verborgen` weg, zodat de knop te zien is.

### E2: Winkelwagen

*Als bezoeker wil ik producten in een winkelwagen doen, zodat ik zie wat ik ga kopen.*

- [ ] De knop `#winkelwagen-knop` is zichtbaar (haal de class `verborgen` weg) en toont het aantal in `#winkelwagen-aantal`.
- [ ] Op elke kaart staat een knop "In winkelwagen" (zie het voorbeeld in `index.html`).
- [ ] De pop-up `#winkelwagen` laat de producten zien in `#winkelwagen-lijst` en het **totaalbedrag** in `#winkelwagen-totaal`. Het totaal reken je uit met `reduce()`.
- [ ] Je kunt een product weer uit de winkelwagen halen.
- [ ] De winkelwagen wordt bewaard in `localStorage`.

### E3: Korting tonen

*Als bezoeker wil ik zien hoeveel korting een product heeft, zodat ik een koopje kan vinden.*

- [ ] Op de kaart staat de korting, bijvoorbeeld "-12%" (veld `discountPercentage`, afgerond).
- [ ] De oude prijs staat doorgestreept, de nieuwe prijs ernaast.

### E4: Code in modules

*Als programmeur wil ik mijn code over bestanden verdelen, zodat het overzichtelijk blijft.*

- [ ] Je code staat in minimaal 3 bestanden, bijvoorbeeld `api.js`, `favorieten.js` en `main.js`.
- [ ] Je gebruikt `import` en `export` (zie [Modules](https://meesterjson.nl/cheat-sheet/pages/javascript/modules.html)).
- [ ] Dit is de enige keer dat je `index.html` mag veranderen: maak van de laatste regel `<script type="module" src="main.js"></script>`.

## Beoordeling en eindcheck

| Wat heb je gedaan? | Cijfer |
| --- | --- |
| Niet alle MOET-stories werken | onvoldoende |
| Alle MOET-stories werken, je houdt je aan de afspraken over je code en je kunt je code uitleggen | 6 |
| Hetzelfde + 1 EXTRA-story | 7 |
| Hetzelfde + 2 EXTRA-stories | 8 |
| Hetzelfde + 3 of meer EXTRA-stories, en je code is netjes en overzichtelijk | 9 of 10 |

Kun je je eigen code niet uitleggen? Dan telt dat deel niet mee.

**Eindcheck: test dit samen vóór je inlevert**

Doe elke test echt in de browser. Vink pas af als het werkt: verander `[ ]` in `[x]` en commit. Werk je alleen? Dan sla je de tests over bij user stories die je niet gemaakt hebt.

- [ ] Ik open de site: ik zie alle producten met foto, naam, prijs en categorie.
- [ ] (US10) Tijdens het laden staat er "Producten laden..." en daarna is die tekst weg.
- [ ] Ik typ "phone" in het zoekveld: ik zie alleen producten met "phone" in de naam.
- [ ] Ik typ "xyzxyz": ik zie "Geen producten gevonden".
- [ ] Ik maak het zoekveld leeg: alle producten zijn terug.
- [ ] Ik kies categorie "beauty": ik zie alleen beauty-producten.
- [ ] (US5) Ik sorteer op "Prijs laag - hoog": het goedkoopste product staat bovenaan.
- [ ] Ik klik op 3 hartjes: ze worden rood.
- [ ] Ik druk op F5: de 3 hartjes zijn nog rood.
- [ ] (US8) De knop zegt "Favorieten (3)". Ik open mijn favorieten en haal er 1 weg: ik zie er nog 2 en de knop zegt "Favorieten (2)".
- [ ] (US9) Ik klik op een product: ik zie de details en kan het venster sluiten.
- [ ] (US10) Ik zet een tikfout in de API-URL: ik zie een nette foutmelding. (Daarna weer goed zetten!)
- [ ] Ik open de console (F12): er staan geen rode fouten.
- [ ] Alle code is gepusht naar GitHub en de site staat online.

## Hulp en tips

**Waar vind je hulp?**

- [Hulp week 5: Productcatalogus](https://meesterjson.nl/cheat-sheet/pages/javascript/opdrachten/week5-hulp.html) lijkt erg op dit project (zoeken en sorteren). Kijk daar eerst.
- Krijg je een rode fout in de console? Zoek hem op bij [Foutmeldingen](https://meesterjson.nl/cheat-sheet/pages/javascript/foutmeldingen.html).
- Kom je er na 15 minuten zelf niet uit? Werk je met z'n tweeën? Vraag dan eerst je teamgenoot. Daarna de docent.

**Een goed begin: zo kan je script.js eruitzien**

Dit is alleen het skelet. De inhoud van de functies schrijf je zelf.

```javascript
// Hier bewaren we alle producten uit de API
let alleProducten = [];

// Haalt de producten op uit de API
async function haalProductenOp() {
  // fetch, await, try/catch ...
}

// Zet een lijst met producten op het scherm
function toonProducten(lijst) {
  // maak de container leeg, loop door de lijst, maak kaarten ...
}

haalProductenOp();
```

**Tips die je veel tijd besparen**

1. **Eerst console.log, dan pas het scherm.** Kijk altijd eerst in de console of je data goed is, voordat je er HTML van maakt.
2. **Filter altijd vanaf `alleProducten`.** Pas je originele array nooit aan. Maak een nieuwe lijst met `filter()` en geef die aan `toonProducten()`.
3. **Prijs in euro's:** `price.toFixed(2).replace(".", ",")` maakt van `9.99` de tekst `9,99`.
4. **localStorage is leeg bij je eerste bezoek.** Gebruik daarom: `JSON.parse(localStorage.getItem("favorieten")) || []`.
5. **Hartje opent ook de details?** Klik je op het hartje en gaat ook de pop-up open, gebruik dan `event.stopPropagation()` in de klik op het hartje.
6. **Werk elke dag in kleine stapjes.** Werkt iets? Meteen committen. Dan kun je altijd terug.

**Werk je met z'n tweeën? Dit is de taakverdeling: ieder 5 stories**

| Persoon A | Persoon B |
| --- | --- |
| US1: producten ophalen | US4: filteren op categorie |
| US2: producten tonen | US5: sorteren op prijs |
| US3: zoeken | US6: favoriet maken |
| US9: productdetails | US7: favorieten bewaren |
| US10: laden en foutmelding | US8: favorietenoverzicht |

Leg elkaar aan het eind van elke week uit wat je gemaakt hebt, zodat jullie allebei alle onderdelen snappen. Bij de oplevering kan de docent jou over **elk** stuk code iets vragen.
