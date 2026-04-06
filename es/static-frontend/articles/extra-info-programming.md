---
title: 'Programación de información adicional'
date: '2024-06-16'
modified: '2024-06-16'
---

Esta es una función avanzada que te permite cambiar el campo de información adicional en una factura según lo que se ingrese en otros campos. Si no eres programador, mi sugerencia sería simplemente revisar los ejemplos a continuación, elegir uno que se ajuste a tus necesidades y adaptarlo en consecuencia.

## Ejemplos

Aquí encontrarás varios ejemplos que puedes usar en la sección "Programa de información adicional" de la [página de Configuración](/app/settings).

### Especificar una fecha de vencimiento de pago según la fecha de la factura

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Por favor pagar antes del ${formatDate(date)}`;
```

Al crear una factura, aparecerá un botón "Ejecutar programa de información adicional" junto al campo "Información adicional". Al hacer clic, llenará el campo con texto como "Por favor pagar antes del 2024-06-26".

### Especificar una fecha de vencimiento de pago automáticamente

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Por favor pagar antes del ${formatDate(date)}`;
```

Cuando cambies la fecha de la factura o cualquier otro campo, el campo de información adicional se actualizará automáticamente. Ten en cuenta que este campo se sobrescribirá automáticamente, por lo que tus cambios manuales pueden perderse. Por lo tanto, usa la variante automática (primera línea `// AUTO`) solo cuando quieras que la información adicional siempre tenga el mismo aspecto.

### Especificar fecha de vencimiento de pago según la fecha y el idioma de la factura (automáticamente)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'lt') {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Por favor pagar antes del ${formatDate(date)}`;
} else if (language === 'es') {
  globalThis.result = `Por favor pagar antes del ${formatDate(date)}`;
}
```

### Especificar método de pago según el comprador o monto

```js
let result = 'Por favor pagar';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += ' por TRANSFERENCIA BANCARIA';
} else {
  result += ' en EFECTIVO';
}
globalThis.result = result;
```

En este ejemplo, si el campo del comprador contiene "Corp" o "Inc" o el monto de la factura es más de 500 (los montos se proporcionan al programa en centavos, por lo que se especifica 50000), entonces solicitamos pago por transferencia bancaria. De lo contrario, solicitamos pago en efectivo.

### Combinando información

Puedes combinar esta información si deseas especificar tanto la fecha de pago como el método de pago.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Por favor pagar antes del ${formatDate(date)}\n`;

result += 'Método de pago: ';
if (buyer.includes('Corp') || buyer.includes('Inc') || price > 50000) {
  result += 'TRANSFERENCIA BANCARIA';
} else {
  result += 'EFECTIVO';
}
globalThis.result = result;
```

## Información para programadores

El programa de información adicional está escrito en el lenguaje de programación JavaScript.

El programa recibe esta información:

- `invoiceType` - Tipo de factura. Puede ser `standard`, `proforma` o `credit`.
- `seriesName` - nombre de serie
- `seriesId` - número de serie
- `date` - fecha de la factura
- `language` - idioma
- `seller` - información del vendedor
- `buyer` - información del comprador
- `issuer` - persona que creó la factura
- `items` - array de servicios o productos
- `price` - suma de artículos o servicios de la factura en centavos

Datos de ejemplo pasados al programa:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const language = 'es';
const seller = 'Comprador';
const buyer = 'Vendedor';
const email = '';
const issuer = 'Juan Pérez';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Si la primera línea del programa es el comentario `// AUTO`, el programa se ejecutará cada vez que cambien los campos.

```js
// AUTO
```

Los programas marcados con `// AUTO` también se ejecutarán al editar múltiples facturas por lotes.

`formatDate` es una función auxiliar que formatea las fechas en formato AAAA-MM-DD, por ejemplo, 2024-06-26
