---
title: 'Tilleggsinformasjonsprogrammering'
date: '2024-06-16'
modified: '2024-06-16'
---

Dette er en avansert funksjon som lar deg endre tilleggsinformasjons-
feltet på en faktura basert på hva som er lagt inn i andre felt. Hvis du ikke er
programmerer, vil mitt forslag være å bare gjennomgå eksemplene nedenfor, velge
et som passer dine behov, og tilpasse det deretter.

## Eksempler

Her finner du diverse eksempler som du kan bruke i [Innstillinger-
siden](/app/settings) "Tilleggsinformasjonsprogram"-seksjonen.

### Spesifiser en betalingsforfallsdato basert på fakturadato

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Vennligst betal innen ${formatDate(date)}`;
```

Når du oppretter en faktura, vil en "Kjør tilleggsinformasjonsprogram"-knapp vises
ved siden av "Tilleggsinformasjon"-feltet. Når den klikkes, vil den
fylle ut feltet med tekst som "Vennligst betal innen 2024-06-26".

### Spesifiser en betalingsforfallsdato automatisk

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Vennligst betal innen ${formatDate(date)}`;
```

Når du endrer fakturadatoen eller et annet felt, vil tilleggsinformasjons-
feltet oppdateres automatisk. Vær oppmerksom på at dette feltet vil bli
automatisk overskrevet, så dine manuelle endringer kan gå tapt. Derfor, bruk
den automatiske varianten (første linje `// AUTO`) kun når du ønsker at tilleggsinformasjonen alltid skal se ut på samme måte.

### Spesifiser betalingsforfallsdato basert på fakturadato og språk (automatisk)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'lt') {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
} else if (language === 'nb') {
  globalThis.result = `Vennligst betal innen ${formatDate(date)}`;
}
```

### Spesifiser betalingsmetode basert på kjøper eller beløp

```js
let result = 'Vennligst betal';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' ved BANKOVERFØRING';
} else {
  result += ' med KONTANTER';
}
globalThis.result = result;
```

I dette eksemplet, hvis kjøperfeltet inneholder "Corp" eller "Inc" eller faktura-
beløpet er mer enn 500 (beløp leveres til programmet i øre, så 50000
er spesifisert), ber vi om betaling ved bankoverføring. Ellers ber vi om
kontantbetaling.

### Kombinere informasjon

Du kan kombinere denne informasjonen hvis du ønsker å spesifisere både betalingsdatoen
og betalingsmetoden.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Vennligst betal innen ${formatDate(date)}\n`;

result += 'Betalingsmetode: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'BANKOVERFØRING';
} else {
  result += 'KONTANTER';
}
globalThis.result = result;
```

## Informasjon for programmerere

Tilleggsinformasjonsprogrammet er skrevet i programmeringsspråket JavaScript.

Programmet mottar denne informasjonen:

- `invoiceType` - Fakturatype. Kan være `standard`, `proforma`, eller `credit`.
- `seriesName` - serienavn
- `seriesId` - serienummer
- `date` - fakturadato
- `language` - språk
- `seller` - selgerinformasjon
- `buyer` - kjøperinformasjon
- `issuer` - personen som opprettet fakturaen
- `items` - array av tjenester eller produkter
- `price` - sum av fakturaoppføringer eller tjenester i øre

Eksempeldata som sendes til programmet:

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

Hvis den første linjen i programmet er kommentaren `// AUTO`, vil programmet bli
utført hver gang felt endres.

```js
// AUTO
```

Programmer merket med `// AUTO` vil også bli utført ved batchredigering av flere
fakturaer.

`formatDate` er en hjelpefunksjon som formaterer datoer i YYYY-MM-DD-format,
f.eks. 2024-06-26
