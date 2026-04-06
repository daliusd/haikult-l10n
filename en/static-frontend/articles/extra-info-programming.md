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

### Specify a payment due date based on invoice date

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Please pay by ${formatDate(date)}`;
```

When creating an invoice, a "Run additional information program" button will
appear next to the "Additional information" field. When clicked, it will
populate the field with text like "Please pay by 2024-06-26".

### Specify a payment due date automatically

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Please pay by ${formatDate(date)}`;
```

When you change the invoice date or any other field, the additional information
field will update automatically. Keep in mind that this field will be
automatically overwritten, so your manual changes may be lost. Therefore, use
the automatic variant (first line `// AUTO`) only when you want the additional
information to always look the same.

### Specify payment due date based on invoice date and language (automatically)

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

### Specify payment method based on buyer or amount

```js
let result = 'Please pay';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' by BANK TRANSFER';
} else {
  result += ' by CASH';
}
globalThis.result = result;
```

In this example, if the buyer field contains "Corp" or "Inc" or the invoice
amount is more than 500 (amounts are provided to the program in cents, so 50000
is specified), then we request payment by bank transfer. Otherwise, we request
cash payment.

### Combining information

You can combine this information if you want to specify both the payment date
and payment method.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Please pay by ${formatDate(date)}\n`;

result += 'Payment method: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'BANK TRANSFER';
} else {
  result += 'CASH';
}
globalThis.result = result;
```

## Information for Programmers

The additional information program is written in the JavaScript programming language.

The program receives this information:

- `invoiceType` - Invoice type. Can be `standard`, `proforma`, or `credit`.
- `seriesName` - series name
- `seriesId` - series number
- `date` - invoice date
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
