---
title: 'Programação de Informação Adicional'
date: '2024-06-16'
modified: '2024-06-16'
---

Esta é uma funcionalidade avançada que permite alterar o campo de informação adicional numa fatura com base no que está inserido noutros campos. Se não é programador, a minha sugestão seria simplesmente rever os exemplos abaixo, escolher um que se adeque às suas necessidades e adaptá-lo em conformidade.

## Exemplos

Aqui encontrará vários exemplos que pode usar na secção "Programa de Informação Adicional" da [página de Configurações](/app/settings).

### Especificar uma data de vencimento de pagamento com base na data da fatura

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Por favor, pague até ${formatDate(date)}`;
```

Ao criar uma fatura, aparecerá um botão "Executar programa de informação adicional" junto ao campo "Informação adicional". Quando clicado, irá preencher o campo com texto como "Por favor, pague até 2024-06-26".

### Especificar uma data de vencimento de pagamento automaticamente

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Por favor, pague até ${formatDate(date)}`;
```

Quando altera a data da fatura ou qualquer outro campo, o campo de informação adicional será atualizado automaticamente. Tenha em mente que este campo será automaticamente substituído, pelo que as suas alterações manuais podem ser perdidas. Portanto, use a variante automática (primeira linha `// AUTO`) apenas quando quiser que a informação adicional tenha sempre o mesmo aspeto.

### Especificar data de vencimento de pagamento com base na data da fatura e idioma (automaticamente)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'lt') {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Por favor, pague até ${formatDate(date)}`;
}
```

### Especificar método de pagamento com base no comprador ou valor

```js
let result = 'Por favor, pague';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' por TRANSFERÊNCIA BANCÁRIA';
} else {
  result += ' em DINHEIRO';
}
globalThis.result = result;
```

Neste exemplo, se o campo do comprador contiver "Corp" ou "Inc" ou o valor da fatura for superior a 500 (os valores são fornecidos ao programa em cêntimos, por isso é especificado 50000), então solicitamos pagamento por transferência bancária. Caso contrário, solicitamos pagamento em dinheiro.

### Combinar informação

Pode combinar esta informação se quiser especificar tanto a data de pagamento como o método de pagamento.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Por favor, pague até ${formatDate(date)}\n`;

result += 'Método de pagamento: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'TRANSFERÊNCIA BANCÁRIA';
} else {
  result += 'DINHEIRO';
}
globalThis.result = result;
```

## Informação para Programadores

O programa de informação adicional é escrito na linguagem de programação JavaScript.

O programa recebe esta informação:

- `invoiceType` - Tipo de fatura. Pode ser `standard`, `proforma`, ou `credit`.
- `seriesName` - nome da série
- `seriesId` - número da série
- `date` - data da fatura
- `language` - idioma
- `seller` - informação do vendedor
- `buyer` - informação do comprador
- `issuer` - pessoa que criou a fatura
- `items` - array de serviços ou produtos
- `price` - soma dos itens ou serviços da fatura em cêntimos

Exemplo de dados passados ao programa:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const language = 'en';
const seller = 'Comprador';
const buyer = 'Vendedor';
const email = '';
const issuer = 'João Silva';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Se a primeira linha do programa for o comentário `// AUTO`, o programa será executado sempre que os campos mudarem.

```js
// AUTO
```

Os programas marcados com `// AUTO` também serão executados ao editar múltiplas faturas em lote.

`formatDate` é uma função auxiliar que formata datas no formato AAAA-MM-DD, por exemplo, 2024-06-26
