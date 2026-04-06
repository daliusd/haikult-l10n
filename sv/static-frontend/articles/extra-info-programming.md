---
title: 'Ytterligare informationsprogrammering'
date: '2024-06-16'
modified: '2024-06-16'
---

Detta är en avancerad funktion som låter dig ändra fältet för ytterligare information
på en faktura baserat på vad som anges i andra fält. Om du inte är
programmerare skulle mitt förslag vara att helt enkelt granska exemplen nedan, välja
ett som passar dina behov och anpassa det därefter.

## Exempel

Här hittar du olika exempel som du kan använda på [Inställningssidan](/app/settings)
i sektionen "Ytterligare informationsprogram".

### Ange ett betalningsförfallodatum baserat på fakturadatum

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Vänligen betala senast ${formatDate(date)}`;
```

När du skapar en faktura kommer en knapp "Kör ytterligare informationsprogram" att visas
bredvid fältet "Ytterligare information". När den klickas kommer den
att fylla i fältet med text som "Vänligen betala senast 2024-06-26".

### Ange ett betalningsförfallodatum automatiskt

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Vänligen betala senast ${formatDate(date)}`;
```

När du ändrar fakturadatumet eller något annat fält kommer fältet för ytterligare information
att uppdateras automatiskt. Tänk på att detta fält kommer att skrivas över
automatiskt, så dina manuella ändringar kan gå förlorade. Därför, använd
den automatiska varianten (första raden `// AUTO`) endast när du vill att den ytterligare
informationen alltid ska se likadan ut.

### Ange betalningsförfallodatum baserat på fakturadatum och språk (automatiskt)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'lt') {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
}
```

### Ange betalningsmetod baserat på köpare eller belopp

```js
let result = 'Vänligen betala';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' via BANKÖVERFÖRING';
} else {
  result += ' KONTANT';
}
globalThis.result = result;
```

I detta exempel, om köparfältet innehåller "Corp" eller "Inc" eller fakturabeloppet
är mer än 500 (belopp ges till programmet i ören, så 50000
anges), då begär vi betalning via banköverföring. Annars begär vi
kontant betalning.

### Kombinera information

Du kan kombinera denna information om du vill ange både
betalningsdatumet och betalningsmetoden.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Vänligen betala senast ${formatDate(date)}\n`;

result += 'Betalningsmetod: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'BANKÖVERFÖRING';
} else {
  result += 'KONTANT';
}
globalThis.result = result;
```

## Information för programmerare

Programmet för ytterligare information är skrivet i programmeringsspråket JavaScript.

Programmet tar emot denna information:

- `invoiceType` - Fakturatyp. Kan vara `standard`, `proforma` eller `credit`.
- `seriesName` - serienamn
- `seriesId` - serienummer
- `date` - fakturadatum
- `language` - språk
- `seller` - säljarinformation
- `buyer` - köparinformation
- `issuer` - person som skapade fakturan
- `items` - array av tjänster eller produkter
- `price` - summa av fakturaposter eller tjänster i ören

Exempeldata som skickas till programmet:

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

Om programmets första rad är kommentaren `// AUTO`, kommer programmet att köras
varje gång fält ändras.

```js
// AUTO
```

Program märkta med `// AUTO` kommer också att köras vid batchredigering av flera
fakturor.

`formatDate` är en hjälpfunktion som formaterar datum i ÅÅÅÅ-MM-DD-format,
t.ex. 2024-06-26
