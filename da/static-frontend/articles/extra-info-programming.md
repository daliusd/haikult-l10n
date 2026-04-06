---
title: 'Programmering af yderligere information'
date: '2024-06-16'
modified: '2024-06-16'
---

Dette er en avanceret funktion, der giver dig mulighed for at ændre feltet med yderligere information
på en faktura baseret på, hvad der er indtastet i andre felter. Hvis du ikke er
programmør, vil mit forslag være blot at gennemgå eksemplerne nedenfor, vælge
et, der passer til dine behov, og tilpasse det derefter.

## Eksempler

Her finder du forskellige eksempler, som du kan bruge i [Indstillinger
siden](/app/settings) sektionen "Program til yderligere information".

### Angiv en betalingsforfaldsdato baseret på fakturadato

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Betal venligst senest ${formatDate(date)}`;
```

Ved oprettelse af en faktura vil en knap "Kør program til yderligere information" fremkomme
ved siden af feltet "Yderligere information". Når der klikkes på den, vil
feltet blive udfyldt med tekst som "Betal venligst senest 2024-06-26".

### Angiv en betalingsforfaldsdato automatisk

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Betal venligst senest ${formatDate(date)}`;
```

Når du ændrer fakturadatoen eller et andet felt, vil feltet med yderligere information
blive opdateret automatisk. Husk, at dette felt vil blive
automatisk overskrevet, så dine manuelle ændringer kan gå tabt. Brug derfor
den automatiske variant (første linje `// AUTO`) kun når du vil have, at den yderligere
information altid skal se ens ud.

### Angiv betalingsforfaldsdato baseret på fakturadato og sprog (automatisk)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'da') {
  globalThis.result = `Betal venligst senest ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
}
```

### Angiv betalingsmetode baseret på køber eller beløb

```js
let result = 'Betal venligst';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' ved BANKOVERFØRSEL';
} else {
  result += ' KONTANT';
}
globalThis.result = result;
```

I dette eksempel, hvis køberfeltet indeholder "Corp" eller "Inc", eller fakturaens
beløb er mere end 500 (beløb leveres til programmet i cents, så 50000
er angivet), så anmoder vi om betaling ved bankoverførsel. Ellers anmoder vi om
kontant betaling.

### Kombination af information

Du kan kombinere denne information, hvis du vil angive både betalingsdatoen
og betalingsmetoden.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Betal venligst senest ${formatDate(date)}\n`;

result += 'Betalingsmetode: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'BANKOVERFØRSEL';
} else {
  result += 'KONTANT';
}
globalThis.result = result;
```

## Information til programmører

Programmet til yderligere information er skrevet i programmeringssproget JavaScript.

Programmet modtager denne information:

- `invoiceType` - Fakturatype. Kan være `standard`, `proforma` eller `credit`.
- `seriesName` - serienavn
- `seriesId` - serienummer
- `date` - fakturadato
- `language` - sprog
- `seller` - sælgerinformation
- `buyer` - køberinformation
- `issuer` - person, der oprettede fakturaen
- `items` - array af tjenester eller produkter
- `price` - sum af fakturaposter eller tjenester i cents

Eksempel på data, der sendes til programmet:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const language = 'da';
const seller = 'Køber';
const buyer = 'Sælger';
const email = '';
const issuer = 'John Doe';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Hvis den første linje af programmet er kommentaren `// AUTO`, vil programmet blive
kørt hver gang felter ændres.

```js
// AUTO
```

Programmer markeret med `// AUTO` vil også blive kørt ved batch-redigering af flere
fakturaer.

`formatDate` er en hjælpefunktion, der formaterer datoer i YYYY-MM-DD format,
f.eks. 2024-06-26
