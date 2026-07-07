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

### Fälligkeitsdatum angeben

```js
if (dueDate) {
  globalThis.result = `Bitte zahlen Sie bis ${formatDate(dueDate)}`;
}
```

Beim Erstellen einer Rechnung erscheint eine Schaltfläche "Programm für zusätzliche Informationen ausführen"
neben dem Feld "Zusätzliche Informationen". Wenn Sie darauf klicken, wird das Feld
mit Text wie "Bitte zahlen Sie bis 2024-06-26" gefüllt.

### Fälligkeitsdatum automatisch angeben

```js
// AUTO
if (dueDate) {
  globalThis.result = `Bitte zahlen Sie bis ${formatDate(dueDate)}`;
}
```

Wenn Sie das Rechnungsdatum oder ein anderes Feld ändern, wird das Feld für zusätzliche Informationen
automatisch aktualisiert. Beachten Sie, dass dieses Feld
automatisch überschrieben wird, sodass Ihre manuellen Änderungen verloren gehen können. Verwenden Sie daher
die automatische Variante (erste Zeile `// AUTO`) nur, wenn Sie möchten, dass die zusätzlichen
Informationen immer gleich aussehen.

### Fälligkeitsdatum basierend auf Sprache angeben (automatisch)

```js
// AUTO
if (dueDate) {
  if (language == 'lt') {
    globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(dueDate)}`;
  } else if (language === 'en') {
    globalThis.result = `Please pay by ${formatDate(dueDate)}`;
  } else if (language === 'de') {
    globalThis.result = `Bitte zahlen Sie bis ${formatDate(dueDate)}`;
  }
}
```

### Zahlungsart angeben

Beim Erstellen oder Bearbeiten einer Rechnung können Sie eine Zahlungsart (bar
oder per Überweisung) aus dem Dropdown unter dem Fälligkeitsdatum auswählen.
Diese Auswahl steht dem Programm als Variable `paymentMethod` zur Verfügung, die
`'cash'`, `'bank'` oder `null` ist, wenn nichts ausgewählt wurde. Das Dropdown
selbst erscheint nicht auf der Rechnung — verwenden Sie das Programm, um es in
das Feld für zusätzliche Informationen zu schreiben.

```js
if (paymentMethod === 'bank') {
  globalThis.result = 'Bitte zahlen Sie per BANKÜBERWEISUNG';
} else if (paymentMethod === 'cash') {
  globalThis.result = 'Bitte zahlen Sie in BAR';
}
```

Sie können den Text anhand der Rechnungssprache `language` anpassen:

```js
if (paymentMethod === 'bank') {
  if (language === 'de') {
    globalThis.result = 'Bitte zahlen Sie per Banküberweisung';
  } else {
    globalThis.result = 'Please pay by BANK TRANSFER';
  }
} else if (paymentMethod === 'cash') {
  if (language === 'de') {
    globalThis.result = 'Bitte zahlen Sie in bar';
  } else {
    globalThis.result = 'Please pay in CASH';
  }
}
```

### Informationen kombinieren

Sie können diese Informationen kombinieren, wenn Sie sowohl das Zahlungsdatum
als auch die Zahlungsmethode angeben möchten.

```js
if (dueDate) {
  let result = `Bitte zahlen Sie bis ${formatDate(dueDate)}\n`;

  if (paymentMethod === 'bank') {
    result += 'Zahlungsart: BANKÜBERWEISUNG';
  } else if (paymentMethod === 'cash') {
    result += 'Zahlungsart: BAR';
  }
  globalThis.result = result;
}
```

## Informationen für Programmierer

Das Programm für zusätzliche Informationen ist in der Programmiersprache JavaScript geschrieben.

Das Programm erhält diese Informationen:

- `invoiceType` - Rechnungstyp. Kann `standard`, `proforma` oder `credit` sein.
- `seriesName` - Serienname
- `seriesId` - Seriennummer
- `date` - Rechnungsdatum
- `dueDate` - Fälligkeitsdatum als JavaScript-`Date`-Objekt, oder `null` wenn nicht gesetzt
- `paymentMethod` - gewählte Zahlungsart: `'cash'`, `'bank'` oder `null` wenn nicht gesetzt
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
const dueDate = null;
const paymentMethod = null;
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

`formatDate` ist eine Hilfsfunktion, die Datumsangaben im Format JJJJ-MM-TT formatiert,
z. B. 2024-06-26
