---
title: 'Programmation des informations supplémentaires'
date: '2024-06-16'
modified: '2024-06-16'
---

Il s'agit d'une fonctionnalité avancée qui vous permet de modifier le champ d'informations supplémentaires d'une facture en fonction de ce qui est saisi dans d'autres champs. Si vous n'êtes pas programmeur, je vous suggère simplement de consulter les exemples ci-dessous, de choisir celui qui correspond à vos besoins et de l'adapter en conséquence.

## Exemples

Vous trouverez ici divers exemples que vous pouvez utiliser dans la section "Programme d'informations supplémentaires" de la [page Paramètres](/app/settings).

### Spécifier une date d'échéance de paiement basée sur la date de facture

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Veuillez payer avant le ${formatDate(date)}`;
```

Lors de la création d'une facture, un bouton "Exécuter le programme d'informations supplémentaires" apparaîtra à côté du champ "Informations supplémentaires". Lorsque vous cliquez dessus, il remplira le champ avec un texte tel que "Veuillez payer avant le 2024-06-26".

### Spécifier une date d'échéance de paiement automatiquement

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Veuillez payer avant le ${formatDate(date)}`;
```

Lorsque vous modifiez la date de facture ou tout autre champ, le champ d'informations supplémentaires sera mis à jour automatiquement. Gardez à l'esprit que ce champ sera automatiquement écrasé, vos modifications manuelles peuvent donc être perdues. Par conséquent, utilisez la variante automatique (première ligne `// AUTO`) uniquement lorsque vous voulez que les informations supplémentaires aient toujours la même apparence.

### Spécifier la date d'échéance de paiement en fonction de la date de facture et de la langue (automatiquement)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'fr') {
  globalThis.result = `Veuillez payer avant le ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
}
```

### Spécifier le mode de paiement en fonction de l'acheteur ou du montant

```js
let result = 'Veuillez payer';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' par VIREMENT BANCAIRE';
} else {
  result += ' en ESPÈCES';
}
globalThis.result = result;
```

Dans cet exemple, si le champ acheteur contient "Corp" ou "Inc" ou si le montant de la facture est supérieur à 500 (les montants sont fournis au programme en centimes, donc 50000 est spécifié), nous demandons un paiement par virement bancaire. Sinon, nous demandons un paiement en espèces.

### Combiner des informations

Vous pouvez combiner ces informations si vous souhaitez spécifier à la fois la date de paiement et le mode de paiement.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Veuillez payer avant le ${formatDate(date)}\n`;

result += 'Mode de paiement : ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'VIREMENT BANCAIRE';
} else {
  result += 'ESPÈCES';
}
globalThis.result = result;
```

## Informations pour les programmeurs

Le programme d'informations supplémentaires est écrit en langage de programmation JavaScript.

Le programme reçoit ces informations :

- `invoiceType` - Type de facture. Peut être `standard`, `proforma` ou `credit`.
- `seriesName` - nom de série
- `seriesId` - numéro de série
- `date` - date de facture
- `language` - langue
- `seller` - informations sur le vendeur
- `buyer` - informations sur l'acheteur
- `issuer` - personne qui a créé la facture
- `items` - tableau de services ou produits
- `price` - somme des articles ou services de la facture en centimes

Exemple de données transmises au programme :

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

Si la première ligne du programme est le commentaire `// AUTO`, le programme sera exécuté à chaque modification des champs.

```js
// AUTO
```

Les programmes marqués avec `// AUTO` seront également exécutés lors de la modification par lots de plusieurs factures.

`formatDate` est une fonction d'aide qui formate les dates au format YYYY-MM-DD, par exemple 2024-06-26
