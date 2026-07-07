---
title: 'Papildomos informacijos programavimas'
date: '2024-06-16'
modified: '2024-06-16'
---

Tai yra funkcionalumas pažengusiems leidžiantis keisti papildomą informaciją
sąskaitoje faktūroje priklausomai nuo to kas įvesta kituose laukuose. Jeigu
nesate programuotoja(s) mano pasiūlymas būtų tiesiog peržiūrėti pavyzdžius
žemiau, pasirinkti jums tinkamą/reikiamą ir pritaikyti pagal savo poreikius.

## Pavyzdžiai

Čia rasite įvairių pavyzdžių, kuriuos galite naudoti [Nustatymų
puslapio](/app/settings) „Papildomos informacijos programa" sekcijoje.

### Nurodyti apmokėjimo datą

```js
if (dueDate) {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(dueDate)}`;
}
```

Kuriant sąskaitą faktūrą prie „Papildoma informacija“ lauko atsiras mygtukas
„Vykdyti papildomos informacijos programą“, kurį paspaudus papildomos
informacijos lauke atsiras eilutė panaši į „Prašome apmokėti sąskaitą iki
2024-06-26“.

### Nurodyti apmokėjimo datą (automatiškai)

```js
// AUTO
if (dueDate) {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(dueDate)}`;
}
```

Pakeitus sąskaitos faktūros datą ar bet kurį kitą laukelį papildomos
informacijos laukelis pasikeis automatiškai. Turėkite omeny, kad šis laukas bus
perrašomas automatiškai ir jūsų pakeitimai gali dingti. Todėl naudokite
automatinį variantą (pirma eilutė `// AUTO`) tik tada, kai norite, kad
papildoma informacija atrodytų taip pat.

### Nurodyti apmokėjimo datą pagal kalbą (automatiškai)

```js
// AUTO
if (dueDate) {
  if (language == 'lt') {
    globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(dueDate)}`;
  } else if (language === 'en') {
    globalThis.result = `Please pay by ${formatDate(dueDate)}`;
  }
}
```

### Nurodyti apmokėjimo būdą

Kuriant ar redaguojant sąskaitą faktūrą galite pasirinkti apmokėjimo būdą
(grynais arba bankiniu pavedimu) iš išskleidžiamojo sąrašo, esančio po
apmokėjimo data. Šis pasirinkimas programai pasiekiamas kaip `paymentMethod`
kintamasis, kurio reikšmė yra `'cash'`, `'bank'` arba `null`, kai nieko
nepasirinkta. Pats sąrašas sąskaitoje nematomas — naudokite programą, kad
įrašytumėte jį į papildomos informacijos lauką.

```js
if (paymentMethod === 'bank') {
  globalThis.result = 'Prašome apmokėti BANKINIU PAVEDIMU';
} else if (paymentMethod === 'cash') {
  globalThis.result = 'Prašome apmokėti GRYNAIS';
}
```

Tekstą galite pateikti pagal sąskaitos kalbą `language`:

```js
if (paymentMethod === 'bank') {
  if (language === 'lt') {
    globalThis.result = 'Prašome apmokėti bankiniu pavedimu';
  } else {
    globalThis.result = 'Please pay by BANK TRANSFER';
  }
} else if (paymentMethod === 'cash') {
  if (language === 'lt') {
    globalThis.result = 'Prašome apmokėti grynais';
  } else {
    globalThis.result = 'Please pay in CASH';
  }
}
```

### Informacijos apjungimas

Ir žinoma galima apjungti šią informaciją, jei norime nurodyti ir apmokėjimo
datą ir atsiskaitymo būdą.

```js
if (dueDate) {
  let result = `Prašome apmokėti sąskaitą iki ${formatDate(dueDate)}\n`;

  if (paymentMethod === 'bank') {
    result += 'Atsiskaitymas BANKINIU PAVEDIMU';
  } else if (paymentMethod === 'cash') {
    result += 'Atsiskaitymas GRYNAIS';
  }
  globalThis.result = result;
}
```

## Informacija programuojantiems

Papildomos informacijos programa yra rašoma JavaScript programavimo kalba.

Programa gauna šią informaciją:

- `invoiceType` - SF tipas. Gali būti `standard`, `proforma` arba `credit`.
- `seriesName` - serijos vardas
- `seriesId` - serijos numeris
- `date` - SF data
- `dueDate` - apmokėjimo data kaip JavaScript `Date` objektas, arba `null` jei nenustatyta
- `paymentMethod` - pasirinktas apmokėjimo būdas: `'cash'`, `'bank'` arba `null` jei nenustatyta
- `language` - kalba
- `seller` - pardavėjo informacija
- `buyer` - pirkėjo informacija
- `issuer` - SF išrašęs asmuo
- `items` - paslaugų ar prekių masyvas
- `price` - SF prekių ar paslaugų suma centais

Taip gali atrodyti duomenys paduoti programai:

```js
const invoiceType = 'standard';
const seriesName = 'DD';
const seriesId = 47;
const date = new Date(1718540924628);
const dueDate = null;
const paymentMethod = null;
const language = 'lt';
const seller = 'Pirkėjas';
const buyer = 'Pardavėjas';
const email = '';
const issuer = 'Dalius Dobravolskas';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Jei pirma programos eilutė yra komentaras `// AUTO`, tai programa bus vykdoma
kaskart pasikeitus laukams.

```js
// AUTO
```

Programa pažymėta `// AUTO` bus taip pat vykdoma keičiant kelias sąskaitas
faktūras.

`formatDate` yra tik pagalbinė funkcija, kuri suformatuoja datą
YYYY-MM-DD formatu, pvz.: 2024-06-26
