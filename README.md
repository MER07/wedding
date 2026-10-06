# Rita & Ervin – esküvői weboldal

Statikus weboldal (egyetlen `index.html` + két virágkép), GitHub Pages-en futtatható.
Kétnyelvű (magyar / angol), visszaszámlálóval, programmal, helyszínekkel, galériával, GYIK-kal és RSVP űrlappal.

## Közzététel GitHub Pages-en

1. A repó **Settings → Pages** oldalán a *Source* legyen **Deploy from a branch**, a branch **main**, a mappa **/ (root)**.
2. Pár perc múlva az oldal elérhető: `https://<felhasználónév>.github.io/<repó neve>/`

## RSVP bekötése Google Formba

Az oldal saját űrlapja a válaszokat egy Google Formba küldi, onnan egy Google Sheet táblázatba kerülnek.

1. Hozz létre egy új Google Formot (forms.google.com). Vegyél fel **11 kérdést**, mindegyik típusa **Rövid válasz** legyen, és egyik se legyen kötelező:
   Név · Válasz · Felnőttek · Kísérő neve · Vacsora · Kísérő vacsorája · Gyerekek · Étkezési igény · Dal · Üzenet · Nyelv
2. A *Válaszok* fülön kattints a **Link a Táblázatokhoz** gombra, hogy a válaszok egy Google Sheetbe menjenek.
3. A jobb felső **⋮** menüben válaszd az **Előre kitöltött link lekérése** pontot. A kérdésekbe írd be sorban ezeket a szavakat:
   `name`, `attending`, `adults`, `plus`, `meal`, `plusmeal`, `kids`, `diet`, `song`, `message`, `lang`
4. Kattints a **Link lekérése**, majd a **Link másolása** gombra.
5. Ezt a linket kell beírni az `index.html` végén található `GOOGLE_FORM` beállításba
   (az `action` a link eleje, a `viewform` szót `formResponse`-ra cserélve; a `fields` az `entry.123…` azonosítók).

Ha a `GOOGLE_FORM.action` üres, az űrlap kitölthető, de beküldéskor arra kéri a vendéget, hogy közvetlenül jelezzen vissza.

## Szerkesztés

Az `index.html` alján, a `<script>` elején vannak a könnyen módosítható adatok:

- `WEDDING_AT` – a szertartás időpontja (a visszaszámláló ehhez számol)
- `TIMELINE` – a nap programja, magyarul és angolul
- `FAQ` – kérdések és válaszok
- `PHOTOS` – a galéria; tegyél képeket egy `photos/` mappába, és adj meg `src: "photos/kep.jpg"` mezőt
- `T` – minden további felirat magyarul (`hu`) és angolul (`en`)
