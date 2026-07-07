---
title: 'Additional Information Programming'
date: '2024-06-16'
modified: '2024-06-16'
---

This is an advanced feature that allows you to change the additional information
field on an invoice based on what's entered in other fields. If you're not a
programmer, my suggestion would be to simply review the examples below, choose
one that fits your needs, and adapt it accordingly.

## Examples

Here you'll find various examples that you can use in the [Settings
page](/app/settings) "Additional Information Program" section.

### Specify a payment due date

```js
if (dueDate) {
  globalThis.result = `Please pay by ${formatDate(dueDate)}`;
}
```

When creating an invoice, a "Run additional information program" button will
appear next to the "Additional information" field. When clicked, it will
populate the field with text like "Please pay by 2024-06-26".

### Specify a payment due date automatically

```js
// AUTO
if (dueDate) {
  globalThis.result = `Please pay by ${formatDate(dueDate)}`;
}
```

When you change the invoice date or any other field, the additional information
field will update automatically. Keep in mind that this field will be
automatically overwritten, so your manual changes may be lost. Therefore, use
the automatic variant (first line `// AUTO`) only when you want the additional
information to always look the same.

### Specify payment due date based on language (automatically)

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

### Specify the payment method

When creating or editing an invoice, you can choose a payment method (cash or
bank transfer) from the dropdown below the due date. That choice is available to
the program as the `paymentMethod` variable, which is `'cash'`, `'bank'`, or
`null` when nothing is selected. The dropdown itself does not appear on the
invoice — use the program to render it into the additional information field.

```js
if (paymentMethod === 'bank') {
  globalThis.result = 'Please pay by BANK TRANSFER';
} else if (paymentMethod === 'cash') {
  globalThis.result = 'Please pay in CASH';
}
```

You can localize the text based on the invoice `language`:

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

### Combining information

You can combine this information if you want to specify both the payment date
and payment method.

```js
if (dueDate) {
  let result = `Please pay by ${formatDate(dueDate)}\n`;

  if (paymentMethod === 'bank') {
    result += 'Payment method: BANK TRANSFER';
  } else if (paymentMethod === 'cash') {
    result += 'Payment method: CASH';
  }
  globalThis.result = result;
}
```

## Information for Programmers

The additional information program is written in the JavaScript programming language.

The program receives this information:

- `invoiceType` - Invoice type. Can be `standard`, `proforma`, or `credit`.
- `seriesName` - series name
- `seriesId` - series number
- `date` - invoice date
- `dueDate` - due date as a JavaScript `Date` object, or `null` if not set
- `paymentMethod` - selected payment method: `'cash'`, `'bank'`, or `null` if not set
- `language` - language
- `seller` - seller information
- `buyer` - buyer information
- `issuer` - person who created the invoice
- `items` - array of services or products
- `price` - sum of invoice items or services in cents

Example data passed to the program:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const dueDate = null;
const paymentMethod = null;
const language = 'en';
const seller = 'Buyer';
const buyer = 'Seller';
const email = '';
const issuer = 'John Doe';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

If the first line of the program is the comment `// AUTO`, the program will be
executed every time fields change.

```js
// AUTO
```

Programs marked with `// AUTO` will also be executed when batch editing multiple
invoices.

`formatDate` is a helper function that formats dates in YYYY-MM-DD format,
e.g., 2024-06-26
