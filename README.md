# Rita & Ervin – esküvői weboldal

Statikus weboldal (egyetlen `index.html` + két virágkép), GitHub Pages-en futtatható.
Kétnyelvű (magyar / angol), visszaszámlálóval, programmal, helyszínekkel, galériával, GYIK-kal és RSVP űrlappal.

## Közzététel GitHub Pages-en

1. A repó **Settings → Pages** oldalán a *Source* legyen **Deploy from a branch**, a branch **main**, a mappa **/ (root)**.
2. Pár perc múlva az oldal elérhető: `https://<felhasználónév>.github.io/<repó neve>/`

## RSVP bekötése Google Formba

Az oldal saját (kétnyelvű) űrlapja a válaszokat az „Esküvői RSVP” Google Formba küldi, onnan a hozzá kapcsolt Google Sheet táblázatba kerülnek.
A vendég a Google Formot nem látja; bármelyik nyelven tölti ki az oldalt, a Formba mindig a magyar válaszlehetőségek kerülnek.

Az összerendelés az `index.html` végén, a `GOOGLE_FORM` / `saveRsvp` részben van:

| Weboldal mezője | Google Form kérdése | Beküldött érték |
|---|---|---|
| Teljes neved | Név | szöveg |
| Ott leszek / Nem tudok jönni | Részt tudsz venni az esküvőnkön? | `Igen, alig várom!` / `Sajnos nem :(` |
| Ételérzékenység | Ételérzékenységed van? | `Nincs`, vagy az „Egyéb” mezőbe a beírt szöveg |
| Gyereket hozol? | Gyereket hozol magaddal? | `Igen` / `Nem` |
| Hozol +1 főt? | Hozol +1 főt magaddal? | `Igen` / `Nem` |
| Kísérőd neve | Név (2. szakasz) | szöveg |
| Kísérőd ételérzékenysége | Étel érzékenységed van? (2. szakasz) | `Nincs`, vagy az „Egyéb” szöveg |

**Ha a Google Formon változtatsz** (kérdés vagy válaszlehetőség szövegén, új kérdésen, szakaszokon), az oldalt is igazítani kell, különben a beküldés csendben elveszhet.
A válaszlehetőségek szövegének (pl. `Igen, alig várom!`) pontosan egyeznie kell.

## Szerkesztés

Az `index.html` alján, a `<script>` elején vannak a könnyen módosítható adatok:

- `WEDDING_AT` – a szertartás időpontja (a visszaszámláló ehhez számol)
- `TIMELINE` – a nap programja, magyarul és angolul
- `FAQ` – kérdések és válaszok
- `PHOTOS` – a galéria; tegyél képeket egy `photos/` mappába, és adj meg `src: "photos/kep.jpg"` mezőt
- `T` – minden további felirat magyarul (`hu`) és angolul (`en`)
