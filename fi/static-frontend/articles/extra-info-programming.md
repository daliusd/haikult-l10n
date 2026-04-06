---
title: 'Lisätietojen ohjelmointi'
date: '2024-06-16'
modified: '2024-06-16'
---

Tämä on edistynyt ominaisuus, jonka avulla voit muuttaa laskun lisätietokenttää sen mukaan, mitä on syötetty muihin kenttiin. Jos et ole ohjelmoija, ehdotan että tutustut alla oleviin esimerkkeihin, valitset tarpeisiisi sopivan ja muokkaat sitä tarpeen mukaan.

## Esimerkkejä

Täällä löydät erilaisia esimerkkejä, joita voit käyttää [Asetukset-sivun](/app/settings) "Lisätietojen ohjelma" -osiossa.

### Määritä maksun eräpäivä laskun päivämäärän perusteella

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Maksa viimeistään ${formatDate(date)}`;
```

Kun luot laskun, "Lisätiedot"-kentän viereen ilmestyy "Suorita lisätietojen ohjelma" -painike. Kun sitä painetaan, kenttään täytetään teksti kuten "Maksa viimeistään 2024-06-26".

### Määritä maksun eräpäivä automaattisesti

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
globalThis.result = `Maksa viimeistään ${formatDate(date)}`;
```

Kun muutat laskun päivämäärää tai mitä tahansa muuta kenttää, lisätietokenttä päivittyy automaattisesti. Huomaa, että tämä kenttä ylikirjoitetaan automaattisesti, joten manuaaliset muutoksesi voivat kadota. Siksi käytä automaattista vaihtoehtoa (ensimmäinen rivi `// AUTO`) vain kun haluat lisätietojen näyttävän aina samalta.

### Määritä maksun eräpäivä laskun päivämäärän ja kielen perusteella (automaattisesti)

```js
// AUTO
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
if (language == 'fi') {
  globalThis.result = `Maksa viimeistään ${formatDate(date)}`;
} else if (language === 'en') {
  globalThis.result = `Please pay by ${formatDate(date)}`;
}
```

### Määritä maksutapa ostajan tai summan perusteella

```js
let result = 'Maksa';
if (buyer.includes('Oy') || buyer.includes('Ab') || price > 50000) {
  result += ' TILISIIRROLLA';
} else {
  result += ' KÄTEISELLÄ';
}
globalThis.result = result;
```

Tässä esimerkissä, jos ostajatiedoissa on "Oy" tai "Ab" tai laskun summa on yli 500 (summat annetaan ohjelmalle sentteinä, joten määritetään 50000), pyydämme maksua tilisiirrolla. Muutoin pyydämme käteismaksua.

### Tietojen yhdistäminen

Voit yhdistää nämä tiedot, jos haluat määrittää sekä maksupäivän että maksutavan.

```js
const daysUntilDue = 10;
date.setDate(date.getDate() + daysUntilDue);
let result = `Maksa viimeistään ${formatDate(date)}\n`;

result += 'Maksutapa: ';
if (buyer.includes('Oy') || buyer.includes('Ab') || price > 50000) {
  result += 'TILISIIRTO';
} else {
  result += 'KÄTEINEN';
}
globalThis.result = result;
```

## Tietoja ohjelmoijille

Lisätietojen ohjelma on kirjoitettu JavaScript-ohjelmointikielellä.

Ohjelma saa nämä tiedot:

- `invoiceType` - Laskun tyyppi. Voi olla `standard`, `proforma` tai `credit`.
- `seriesName` - sarjan nimi
- `seriesId` - sarjanumero
- `date` - laskun päivämäärä
- `language` - kieli
- `seller` - myyjän tiedot
- `buyer` - ostajan tiedot
- `issuer` - laskun luoja
- `items` - palveluiden tai tuotteiden taulukko
- `price` - laskun nimikkeiden tai palveluiden summa sentteinä

Esimerkki ohjelmalle välitettävästä datasta:

```js
const invoiceType = 'standard';
const seriesName = 'INV';
const seriesId = 47;
const date = new Date(1718540924628);
const language = 'fi';
const seller = 'Ostaja';
const buyer = 'Myyjä';
const email = '';
const issuer = 'Matti Meikäläinen';
const items = [{ id: 0, name: '', unit: 'H87', amount: 1, price: 0 }];
const price = 0;
```

Jos ohjelman ensimmäinen rivi on kommentti `// AUTO`, ohjelma suoritetaan joka kerta kun kenttiä muutetaan.

```js
// AUTO
```

`// AUTO`-merkinnällä varustetut ohjelmat suoritetaan myös joukkoeditointivelhossa.

`formatDate` on apufunktio, joka muotoilee päivämäärät VVVV-KK-PP-muotoon, esim. 2024-06-26
