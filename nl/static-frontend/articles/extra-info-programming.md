---
title: 'Extra Informatie Programmering'
date: '2024-06-16'
modified: '2024-06-16'
---

Dit is een geavanceerde functie waarmee u het extra informatieveld op een factuur kunt wijzigen op basis van wat er in andere velden is ingevoerd. Als u geen programmeur bent, raad ik aan om simpelweg de onderstaande voorbeelden te bekijken, er een te kiezen die bij uw behoeften past, en deze dienovereenkomstig aan te passen.

## Voorbeelden

Hier vindt u verschillende voorbeelden die u kunt gebruiken in het "Extra Informatie Programma" gedeelte van de [Instellingen pagina](/app/settings).

### Specificeer een betaaltermijn op basis van de factuurdatum

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Gelieve te betalen voor ${formatDate(date)}`;
```

Bij het aanmaken van een factuur verschijnt er een knop "Extra informatie programma uitvoeren" naast het veld "Extra informatie". Wanneer erop wordt geklikt, wordt het veld gevuld met tekst zoals "Gelieve te betalen voor 2024-06-26".

### Specificeer een betaaltermijn automatisch

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Gelieve te betalen voor ${formatDate(date)}`;
```

Wanneer u de factuurdatum of een ander veld wijzigt, wordt het extra informatieveld automatisch bijgewerkt. Houd er rekening mee dat dit veld automatisch wordt overschreven, dus uw handmatige wijzigingen kunnen verloren gaan. Gebruik daarom de automatische variant (eerste regel `// AUTO`) alleen wanneer u wilt dat de extra informatie er altijd hetzelfde uitziet.

### Specificeer betaaltermijn op basis van factuurdatum en taal (automatisch)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'lt') {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
} else if (language === 'nl') {
  globalThis.result = `Gelieve te betalen voor ${formatDate(date)}`;
}
```

### Specificeer betaalmethode op basis van koper of bedrag

```js
let result = 'Gelieve te betalen';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' via BANKOVERSCHRIJVING';
} else {
  result += ' met CONTANT GELD';
}
globalThis.result = result;
```

In dit voorbeeld, als het koperveld "Corp" of "Inc" bevat, of het factuurbedrag meer dan 500 is (bedragen worden aan het programma verstrekt in centen, dus 50000 is gespecificeerd), vragen we om betaling via bankoverschrijving. Anders vragen we om contante betaling.

### Informatie combineren

U kunt deze informatie combineren als u zowel de betaaldatum als de betaalmethode wilt specificeren.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Gelieve te betalen voor ${formatDate(date)}\n`;

result += 'Betaalmethode: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'BANKOVERSCHRIJVING';
} else {
  result += 'CONTANT GELD';
}
globalThis.result = result;
```

## Informatie voor Programmeurs

Het extra informatie programma is geschreven in de JavaScript-programmeertaal.

Het programma ontvangt deze informatie:

- `invoiceType` - Factuurtype. Kan `standard`, `proforma`, of `credit` zijn.
- `seriesName` - serienaam
- `seriesId` - serienummer
- `date` - factuurdatum
- `language` - taal
- `seller` - verkoperinformatie
- `buyer` - koperinformatie
- `issuer` - persoon die de factuur heeft aangemaakt
- `items` - array van diensten of producten
- `price` - som van factuuritems of diensten in centen

Voorbeeld van gegevens die aan het programma worden doorgegeven:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const language = 'en';
const seller = 'Buyer';
const buyer = 'Seller';
const email = '';
const issuer = 'John Doe';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Als de eerste regel van het programma de opmerking `// AUTO` is, wordt het programma uitgevoerd elke keer dat velden wijzigen.

```js
// AUTO
```

Programma's gemarkeerd met `// AUTO` worden ook uitgevoerd bij het batch bewerken van meerdere facturen.

`formatDate` is een hulpfunctie die datums opmaakt in JJJJ-MM-DD formaat, bijvoorbeeld 2024-06-26
