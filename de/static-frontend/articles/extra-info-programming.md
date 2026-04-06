---
title: 'Programmierung zusätzlicher Informationen'
date: '2024-06-16'
modified: '2024-06-16'
---

Dies ist eine erweiterte Funktion, die es Ihnen ermöglicht, das Feld für zusätzliche Informationen
einer Rechnung basierend auf dem zu ändern, was in anderen Feldern eingegeben wird. Wenn Sie kein
Programmierer sind, würde ich vorschlagen, einfach die unten stehenden Beispiele durchzusehen, eines
auszuwählen, das Ihren Bedürfnissen entspricht, und es entsprechend anzupassen.

## Beispiele

Hier finden Sie verschiedene Beispiele, die Sie im Bereich "Programm für zusätzliche Informationen"
auf der [Einstellungsseite](/app/settings) verwenden können.

### Fälligkeitsdatum basierend auf Rechnungsdatum angeben

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Bitte zahlen Sie bis ${formatDate(date)}`;
```

Beim Erstellen einer Rechnung erscheint eine Schaltfläche "Programm für zusätzliche Informationen ausführen"
neben dem Feld "Zusätzliche Informationen". Wenn Sie darauf klicken, wird das Feld
mit Text wie "Bitte zahlen Sie bis 2024-06-26" gefüllt.

### Fälligkeitsdatum automatisch angeben

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Bitte zahlen Sie bis ${formatDate(date)}`;
```

Wenn Sie das Rechnungsdatum oder ein anderes Feld ändern, wird das Feld für zusätzliche Informationen
automatisch aktualisiert. Beachten Sie, dass dieses Feld
automatisch überschrieben wird, sodass Ihre manuellen Änderungen verloren gehen können. Verwenden Sie daher
die automatische Variante (erste Zeile `// AUTO`) nur, wenn Sie möchten, dass die zusätzlichen
Informationen immer gleich aussehen.

### Fälligkeitsdatum basierend auf Rechnungsdatum und Sprache angeben (automatisch)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'lt') {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
} else if (language === 'de') {
  globalThis.result = `Bitte zahlen Sie bis ${formatDate(date)}`;
}
```

### Zahlungsmethode basierend auf Käufer oder Betrag angeben

```js
let result = 'Bitte zahlen Sie';
if (buyer.includes('GmbH') || buyer.includes('AG') || price > 50000) {
  result += ' per BANKÜBERWEISUNG';
} else {
  result += ' in BAR';
}
globalThis.result = result;
```

In diesem Beispiel, wenn das Käuferfeld "GmbH" oder "AG" enthält oder der Rechnungsbetrag
mehr als 500 beträgt (Beträge werden dem Programm in Cent bereitgestellt, daher wird 50000
angegeben), fordern wir die Zahlung per Banküberweisung an. Andernfalls fordern wir
Barzahlung an.

### Informationen kombinieren

Sie können diese Informationen kombinieren, wenn Sie sowohl das Zahlungsdatum
als auch die Zahlungsmethode angeben möchten.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Bitte zahlen Sie bis ${formatDate(date)}\n`;

result += 'Zahlungsmethode: ';
if (buyer.includes('GmbH') || buyer.includes('AG') || price > 50000) {
  result += 'BANKÜBERWEISUNG';
} else {
  result += 'BAR';
}
globalThis.result = result;
```

## Informationen für Programmierer

Das Programm für zusätzliche Informationen ist in der Programmiersprache JavaScript geschrieben.

Das Programm erhält diese Informationen:

- `invoiceType` - Rechnungstyp. Kann `standard`, `proforma` oder `credit` sein.
- `seriesName` - Serienname
- `seriesId` - Seriennummer
- `date` - Rechnungsdatum
- `language` - Sprache
- `seller` - Verkäuferinformationen
- `buyer` - Käuferinformationen
- `issuer` - Person, die die Rechnung erstellt hat
- `items` - Array von Dienstleistungen oder Produkten
- `price` - Summe der Rechnungspositionen oder Dienstleistungen in Cent

Beispieldaten, die an das Programm übergeben werden:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const language = 'de';
const seller = 'Verkäufer';
const buyer = 'Käufer';
const email = '';
const issuer = 'Max Mustermann';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Wenn die erste Zeile des Programms der Kommentar `// AUTO` ist, wird das Programm
jedes Mal ausgeführt, wenn sich Felder ändern.

```js
// AUTO
```

Programme, die mit `// AUTO` markiert sind, werden auch ausgeführt, wenn mehrere
Rechnungen im Batch-Modus bearbeitet werden.

`formatDate` ist eine Hilfsfunktion, die Daten im Format JJJJ-MM-TT formatiert,
z. B. 2024-06-26
