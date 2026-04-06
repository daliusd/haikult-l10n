---
title: 'Sąskaitų faktūrų žymėjimo kalba (InML)'
date: '2026-02-22'
modified: '2026-02-22'
---

InML (Invoice Markup Language) yra XML pagrindu sukurta šablonų kalba,
skirta apibrėžti sąskaitų faktūrų PDF išdėstymą „Haiku.lt" sistemoje.
Ji suteikia visišką kontrolę sąskaitos struktūrai, stiliui ir turiniui.

Galite pasirinkti vieną iš penkių integruotų stilių kaip pradinį tašką ir
pritaikyti jį pagal savo poreikius arba sukurti šabloną nuo nulio.

## Pagrindinė struktūra

Kiekvienas InML šablonas prasideda šakniniu `<inml>` elementu:

```xml
<inml version="1.0" page-size="A4" margin="20mm"
      font-regular="Roboto-Light" font-bold="Roboto-Medium">
  <page>
    <!-- elementai piešiami kiekviename puslapyje -->
  </page>
  <layout>
    <!-- turinio sritys -->
  </layout>
</inml>
```

### Šakninio elemento atributai

| Atributas      | Aprašymas                                                  |
| -------------- | ---------------------------------------------------------- |
| `version`      | InML versija. Šiuo metu `1.0`.                             |
| `page-size`    | Puslapio formatas. Šiuo metu palaikomas tik `A4`.          |
| `margin`       | Numatytoji puslapio paraštė (pvz. `20mm`).                 |
| `font-regular` | Šriftas paprastam tekstui (pvz. `Roboto-Light`).           |
| `font-bold`    | Šriftas paryškintam tekstui (pvz. `Roboto-Medium`).        |

## Matavimo vienetai

Visi matmenys nurodomi milimetrais (`mm`) arba taškais. Reikšmės rašomos
kaip `20mm`, `5mm`, `210mm`. Šriftų dydžiai nurodomi taškais be vienetų
(pvz. `font-size="12"`).

## Puslapio elementai

`<page>` sekcija apibrėžia elementus, kurie piešiami **kiekviename puslapyje**,
po pagrindiniu turiniu. Naudokite fono paveikslėliams, dekoratyviniams
stačiakampiams ar linijoms.

```xml
<page>
  <image src="{{background}}" x="0mm" y="0mm" width="210mm" height="297mm" />
  <rect x="0mm" y="0mm" width="210mm" height="30mm" fill="#f1f5f9" />
  <line x1="20mm" y1="50mm" x2="190mm" y2="50mm" color="#cccccc" width="0.5mm" />
</page>
```

### Galimi puslapio elementai

- **`<image>`** — fono paveikslėlis. Atributai: `src`, `x`, `y`, `width`,
  `height`.
- **`<rect>`** — stačiakampis. Atributai: `x`, `y`, `width`, `height`, `fill`,
  `stroke`, `stroke-width`.
- **`<line>`** — linija. Atributai: `x1`, `y1`, `x2`, `y2`, `color`, `width`.

## Išdėstymas ir sritys

`<layout>` sekcijoje yra vienas ar daugiau `<region>` elementų. Kiekviena
sritis yra nepriklausoma turinio zona su savo pozicionavimo režimu.

```xml
<layout>
  <region id="header" flow="fixed" margin-top="5mm"
          margin-left="20mm" content-width="170mm">
    <!-- turinys -->
  </region>
  <region id="body" flow="sequential" margin-top="20mm">
    <!-- turinys -->
  </region>
</layout>
```

### Srities atributai

| Atributas       | Aprašymas                                                                          |
| --------------- | ---------------------------------------------------------------------------------- |
| `id`            | Unikalus srities identifikatorius.                                                 |
| `flow`          | Pozicionavimo režimas: `sequential`, `absolute` arba `fixed`.                      |
| `margin-left`   | Horizontalus poslinkis nuo puslapio krašto.                                        |
| `content-width` | Turinio pločio perrašymas šiai sričiai.                                            |
| `margin-top`    | Vertikalus poslinkis. `sequential` sritims prideda tarpą virš srities.             |
| `min-height`    | Minimalus srities aukštis, net jei turinys yra trumpesnis.                         |

### Pozicionavimo režimai

- **`sequential`** — sritys išdėstomos viena po kitos iš viršaus į apačią.
  Tai dažniausiai naudojamas režimas pagrindiniam turiniui.
- **`absolute`** — pozicionuojama konkrečioje vietoje, apskaičiuojant nuo
  dabartinės vertikalios pozicijos. Sekančios „sequential" sritys tęsiasi
  po jos.
- **`fixed`** — pozicionuojama fiksuotoje puslapio vietoje, nepriklausomai
  nuo kitų sričių. Naudinga antraštėms ar uždengimams.

### Išdėstymo stulpeliai

Norėdami sudėti sritis greta viena kitos, apgaubkite jas `<columns>`
elementu išdėstymo lygmenyje:

```xml
<layout>
  <columns>
    <column margin-left="20mm" content-width="80mm">
      <region id="left" flow="sequential">
        <!-- kairysis turinys -->
      </region>
    </column>
    <column content-width="80mm">
      <region id="right" flow="sequential">
        <!-- dešinysis turinys -->
      </region>
    </column>
  </columns>
</layout>
```

Kiekvienas `<column>` gali turėti `margin-left` ir `content-width` atributus
ir savyje talpina vieną ar daugiau `<region>` elementų.

## Turinio elementai

Turinio elementai dedami sričių viduje. Visi turinio elementai turi šiuos
bendrus nebūtinus atributus:

| Atributas       | Aprašymas                                                |
| --------------- | -------------------------------------------------------- |
| `font`          | `regular` arba `bold`.                                   |
| `font-size`     | Šrifto dydis taškais (pvz. `12`).                        |
| `color`         | Teksto ar užpildo spalva (pvz. `#333333`).               |
| `align`         | Teksto lygiavimas: `left`, `right` arba `center`.        |
| `margin-top`    | Tarpas virš elemento.                                    |
| `margin-bottom` | Tarpas po elementu.                                      |

### `<logo>`

Rodo įmonės logotipą, išlaikant proporcijas.

```xml
<logo src="{{logo}}" width="50mm" ratio="{{logoRatio}}" />
```

| Atributas | Aprašymas                                                   |
| --------- | ----------------------------------------------------------- |
| `src`     | Paveikslėlio duomenys (naudokite `{{logo}}` kintamąjį).    |
| `width`   | Rodymo plotis.                                              |
| `height`  | Neprivalomas fiksuotas aukštis.                             |
| `ratio`   | Proporcijų santykis (naudokite `{{logoRatio}}` kintamąjį). |

### `<title>`

Antraštės tekstas, dažniausiai naudojamas sąskaitos pavadinimui.

```xml
<title font="bold" font-size="14" align="center">{{invoiceTitle}}</title>
```

### `<text>`

Paprastas tekstas.

```xml
<text font="regular" font-size="12">{{seller}}</text>
```

### `<columns>` ir `<column>`

Išdėsto turinį greta srities viduje.

```xml
<columns>
  <column width="50%" align="left">
    <text font="bold" font-size="12">{{t.invoice.seller}}</text>
    <text font="regular" font-size="12" margin-top="5mm">{{seller}}</text>
  </column>
  <column width="50%" align="right">
    <text font="bold" font-size="12">{{t.invoice.buyer}}</text>
    <text font="regular" font-size="12" margin-top="5mm">{{buyer}}</text>
  </column>
</columns>
```

Kiekvienas `<column>` turi `width` atributą procentais (pvz. `50%`) ir
neprivalomą `align` atributą.

### `<stack>` ir `<group>`

Vertikaliai sudėtos turinio grupės su nurodomomis tarpais tarp jų.

```xml
<stack spacing="10mm">
  <group>
    <text font="bold" font-size="12">Pirma sekcija</text>
    <text font="regular" font-size="12">Turinys čia</text>
  </group>
  <group>
    <text font="bold" font-size="12">Antra sekcija</text>
    <text font="regular" font-size="12">Daugiau turinio</text>
  </group>
</stack>
```

`spacing` atributas nustato vertikalų tarpą tarp grupių.

### `<box>`

Konteineris su rėmeliu ir užpildu.

```xml
<box stroke="#cccccc" padding="5mm">
  <text font="regular" font-size="12">Turinys rėmelyje</text>
</box>
```

| Atributas | Aprašymas                      |
| --------- | ------------------------------ |
| `stroke`  | Rėmelio spalva.                |
| `padding` | Vidinis užpildas.              |
| `height`  | Neprivalomas fiksuotas aukštis.|

### `<rect>`

Stačiakampis turinio sraute.

```xml
<rect width="170mm" height="1mm" fill="#238c83" />
```

| Atributas | Aprašymas              |
| --------- | ---------------------- |
| `width`   | Stačiakampio plotis.   |
| `height`  | Stačiakampio aukštis.  |
| `fill`    | Užpildo spalva.        |
| `stroke`  | Rėmelio spalva.        |

### `<image>`

Paveikslėlis turinio sraute.

```xml
<image src="{{logo}}" width="50mm" height="20mm" />
```

### `<spacer>`

Prideda vertikalų tarpą tarp elementų.

```xml
<spacer height="10mm" />
```

### `<invoice-table>`

Sąskaitos eilučių lentelė. Tai pagrindinis elementas, skirtas sąskaitos
prekėms ir paslaugoms su stulpeliais ir suvestinės sekcija.

```xml
<invoice-table row-style="minimal" cell-padding="0mm"
       separator-after-header="true" separator-after-items="true"
       separator-color="#aaaaaa" separator-width="0.5mm">
  <col name="id"     label="{{t.invoice.lineItemNo}}"     width="10mm" align="left" />
  <col name="name"   label="{{t.invoice.lineItemName}}"   width="80mm" align="left" />
  <col name="unit"   label="{{t.invoice.lineItemUnit}}"   width="20mm" align="right" />
  <col name="amount" label="{{t.invoice.lineItemAmount}}" width="20mm" align="right" />
  <col name="price"  label="{{priceColumnLabel}}"         width="20mm" align="right" />
  <col name="total"  label="{{t.invoice.lineItemSum}}"    width="20mm" align="right" />

  <summary>
    <row label="{{t.invoice.total}}" value="{{total}}" />
  </summary>
</invoice-table>
```

#### Lentelės atributai

| Atributas                | Aprašymas                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------- |
| `row-style`              | Eilučių stilius: `minimal`, `striped`, `bordered` arba `colored-header`.              |
| `cell-padding`           | Užpildas celės viduje.                                                                |
| `separator-after-header` | Rodyti liniją po antraštės eilute (`true`/`false`).                                   |
| `separator-after-items`  | Rodyti liniją po visomis eilutėmis (`true`/`false`).                                  |
| `separator-color`        | Skiriamųjų linijų spalva.                                                            |
| `separator-width`        | Skiriamųjų linijų storis.                                                            |
| `stripe-color`           | Kaitaliojamų eilučių fono spalva (naudojant `striped` stilių).                        |
| `header-bg-color`        | Antraštės fono spalva (naudojant `colored-header` stilių).                            |
| `header-text-color`      | Antraštės teksto spalva (naudojant `colored-header` stilių).                          |
| `header-extra-padding`   | Papildomas antraštės eilutės užpildas.                                                |

#### Stulpelių apibrėžimai

Kiekvienas `<col>` apibrėžia lentelės stulpelį:

| Atributas | Aprašymas                                                                                 |
| --------- | ----------------------------------------------------------------------------------------- |
| `name`    | Stulpelio identifikatorius: `id`, `name`, `unit`, `amount`, `price`, `vat`, `vat_sum`, `total`. |
| `label`   | Stulpelio antraštės tekstas (naudokite šablono kintamuosius vertimams).                   |
| `width`   | Stulpelio plotis.                                                                         |
| `align`   | Teksto lygiavimas: `left`, `right` arba `center`.                                         |

PVM mokėtojams paprastai pridedami papildomi `vat` ir `vat_sum` stulpeliai.
Naudokite `{{#if vatpayer}}` sąlyginiam jų rodymui.

#### Suvestinės eilutės

`<summary>` sekcija apibrėžia sumas, rodomas po lentele:

```xml
<summary>
  {{#if vatpayer}}
    <row label="{{t.invoice.total_without_vat}}" value="{{totalWithoutVat}}" />
    <row label="{{t.invoice.vat}}" value="{{vatTotal}}" />
  {{/if}}
  <row label="{{t.invoice.total}}" value="{{total}}" />
  {{#if alreadyPaid}}
    <row label="{{t.invoice.alreadyPaid}}" value="{{alreadyPaidFormatted}}" />
    <row label="{{t.invoice.sumToPay}}" value="{{sumToPay}}" />
  {{/if}}
</summary>
```

## Šablono kintamieji

InML naudoja [Handlebars](https://handlebarsjs.com/) sintaksę dinaminiam
turiniui. Kintamieji įterpiami su `{{kintamojoVardas}}`, o sąlyginiai blokai
su `{{#if kintamojoVardas}}...{{/if}}`.

### Galimi kintamieji

#### Sąskaitos duomenys

| Kintamasis            | Aprašymas                                                      |
| --------------------- | -------------------------------------------------------------- |
| `invoiceTitle`        | Sąskaitos pavadinimas pagal tipą ir PVM mokėtojo statusą.      |
| `seriesName`          | Sąskaitos serijos pavadinimas.                                 |
| `seriesId`            | Sąskaitos numeris serijoje.                                    |
| `formattedDate`       | Suformatuota sąskaitos data.                                   |
| `seller`              | Pardavėjo informacija.                                         |
| `buyer`               | Pirkėjo informacija.                                           |
| `issuer`              | Sąskaitą išrašęs asmuo.                                        |
| `extra`               | Papildomos informacijos tekstas.                                |

#### Kainų laukai

| Kintamasis            | Aprašymas                                                      |
| --------------------- | -------------------------------------------------------------- |
| `total`               | Bendra sąskaitos suma (suformatuota).                          |
| `totalWithoutVat`     | Suma be PVM (suformatuota).                                    |
| `vatTotal`            | PVM suma (suformatuota).                                       |
| `alreadyPaid`         | Jau sumokėta suma (skaičius, naudokite su `{{#if}}`).          |
| `alreadyPaidFormatted`| Jau sumokėta suma (suformatuota eilutė).                       |
| `sumToPay`            | Likusi mokėtina suma (suformatuota).                           |
| `priceInWords`        | Bendra suma žodžiais (jei galima).                             |
| `priceColumnLabel`    | Kainos stulpelio etiketė (keičiasi PVM mokėtojams).           |

#### Požymiai

| Kintamasis  | Aprašymas                                                              |
| ----------- | ---------------------------------------------------------------------- |
| `vatpayer`  | `true`, jei pardavėjas yra PVM mokėtojas. Naudokite su `{{#if vatpayer}}`. |

#### Spalvos

| Kintamasis                 | Aprašymas                                      |
| -------------------------- | ---------------------------------------------- |
| `colors.headerBackground`  | Antraštės fono spalva (numatytoji `#f1f5f9`).  |
| `colors.primaryAccent`     | Pagrindinė akcentinė spalva (numatytoji `#238c83`). |

#### Paveikslėliai

| Kintamasis  | Aprašymas                                                    |
| ----------- | ------------------------------------------------------------ |
| `logo`      | Įmonės logotipo duomenys. Naudokite su `{{#if logo}}`.      |
| `logoRatio` | Logotipo proporcijų santykis (`<logo ratio="...">`).         |
| `background`| Fono paveikslėlio duomenys. Naudokite su `{{#if background}}`. |

#### Vertimo eilutės

Visos etiketės pasiekiamos per `t` objektą. Dažniausiai naudojamos:

| Kintamasis                       | Aprašymas                    |
| -------------------------------- | ---------------------------- |
| `t.invoice.seller`               | „Pardavėjas" etiketė        |
| `t.invoice.buyer`                | „Pirkėjas" etiketė          |
| `t.invoice.no`                   | „Nr." etiketė               |
| `t.invoice.total`                | „Iš viso" etiketė           |
| `t.invoice.total_without_vat`    | „Iš viso be PVM"            |
| `t.invoice.vat`                  | „PVM" etiketė               |
| `t.invoice.lineItemNo`           | „Eil. nr." stulpelio antraštė |
| `t.invoice.lineItemName`         | „Pavadinimas" stulpelio antraštė |
| `t.invoice.lineItemUnit`         | „Mato vnt." stulpelio antraštė |
| `t.invoice.lineItemAmount`       | „Kiekis" stulpelio antraštė |
| `t.invoice.lineItemPrice`        | „Kaina" stulpelio antraštė  |
| `t.invoice.lineItemPriceWithoutVAT` | „Kaina (be PVM)"         |
| `t.invoice.lineItemVat`          | „PVM %" antraštė            |
| `t.invoice.lineItemVatSum`       | „PVM suma" antraštė         |
| `t.invoice.lineItemSum`          | „Suma" stulpelio antraštė   |
| `t.invoice.alreadyPaid`          | „Jau sumokėta" etiketė      |
| `t.invoice.sumToPay`             | „Mokėtina suma" etiketė     |
| `t.invoice.sumInWords`           | „Suma žodžiais" etiketė     |
| `t.invoice.invoiceIssuedBy`      | „Sąskaitą išrašė"           |
| `t.metadata.series`              | „Serija" etiketė            |

## Integruoti stiliai

„Haiku.lt" turi penkis integruotus stilius, kuriuos galite naudoti kaip
pradinį tašką:

- **minimalist** — švarus dizainas su centruota antrašte ir minimaliais skirtukais
- **modern-accent** — spalvota antraštės juosta su akcentinėmis spalvomis
- **left-aligned** — kairėn lygiuotas išdėstymas su paprasta struktūra
- **bordered** — lentelės eilutės ir sekcijos su rėmeliais
- **split-column** — dviejų stulpelių išdėstymas pardavėjo ir pirkėjo informacijai

Pasirinkite integruotą stilių sąskaitos nustatymuose, tada perjunkite į
pasirinktinį InML, kad galėtumėte jį modifikuoti.

## Pilnas pavyzdys

Supaprastintas šablonas, rodantis pagrindinius InML konceptus:

```xml
<inml version="1.0" page-size="A4" margin="20mm"
      font-regular="Roboto-Light" font-bold="Roboto-Medium">
  <page>
    {{#if background}}
      <image src="{{background}}" x="0mm" y="0mm" width="210mm" height="297mm" />
    {{/if}}
  </page>
  <layout>
    {{#if logo}}
      <region id="logo" flow="absolute">
        <logo src="{{logo}}" width="50mm" ratio="{{logoRatio}}" />
        <spacer height="10mm" />
      </region>
    {{/if}}

    <region id="title-block" flow="absolute" min-height="40mm">
      <title font="bold" font-size="14" align="center">{{invoiceTitle}}</title>
      <text font="bold" font-size="12" align="center" margin-top="8mm">
        {{t.metadata.series}} {{seriesName}} {{t.invoice.no}} {{seriesId}}
      </text>
      <text font="regular" font-size="12" align="center" margin-top="16mm">
        {{formattedDate}}
      </text>
    </region>

    <region id="parties" flow="sequential" min-height="30mm">
      <columns>
        <column width="50%" align="left">
          <text font="bold" font-size="12">{{t.invoice.seller}}</text>
          <text font="regular" font-size="12" margin-top="5mm">{{seller}}</text>
        </column>
        <column width="50%" align="right">
          <text font="bold" font-size="12">{{t.invoice.buyer}}</text>
          <text font="regular" font-size="12" margin-top="5mm">{{buyer}}</text>
        </column>
      </columns>
    </region>

    <region id="table" flow="sequential" margin-top="20mm">
      <invoice-table row-style="minimal" cell-padding="0mm"
             separator-after-header="true" separator-after-items="true"
             separator-color="#aaaaaa" separator-width="0.5mm">
        <col name="id"     label="{{t.invoice.lineItemNo}}"     width="10mm" align="left" />
        <col name="name"   label="{{t.invoice.lineItemName}}"   width="80mm" align="left" />
        <col name="unit"   label="{{t.invoice.lineItemUnit}}"   width="20mm" align="right" />
        <col name="amount" label="{{t.invoice.lineItemAmount}}" width="20mm" align="right" />
        <col name="price"  label="{{priceColumnLabel}}"         width="20mm" align="right" />
        <col name="total"  label="{{t.invoice.lineItemSum}}"    width="20mm" align="right" />

        <summary>
          <row label="{{t.invoice.total}}" value="{{total}}" />
        </summary>
      </invoice-table>
    </region>

    <region id="footer" flow="sequential">
      {{#if extra}}
        <text font="regular" font-size="12">{{extra}}</text>
        <spacer height="10mm" />
      {{/if}}
      <text font="regular" font-size="12">
        {{t.invoice.invoiceIssuedBy}} {{issuer}}
      </text>
    </region>
  </layout>
</inml>
```
