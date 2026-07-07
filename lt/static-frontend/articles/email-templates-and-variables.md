---
title: 'El. laiškų šablonai ir kintamieji'
date: '2026-05-24'
modified: '2026-05-24'
---

Kai „Haiku.lt" siunčia sąskaitą faktūrą el. paštu, ir laiško tema, ir tekstas yra atvaizduojami iš šablonų, kuriuos jūs kontroliuojate. Šis straipsnis apima visas šios sistemos dalis: temos suasmeninimą, įdiegtuosius laiško teksto šablonus, pilną kintamųjų sąrašą ir kaip naudoti ciklus bei sąlygas savo MJML šablonui sukurti.

Jei dar nesusikonfigūravote el. pašto siuntimo, pradėkite nuo [El. pašto nustatymai: Gmail (OAuth)](/lt/email-setup-gmail) arba [El. pašto nustatymai: SMTP](/lt/email-setup-smtp).

## Kur konfigūruoti

Visi šablonų nustatymai yra [El. pašto nustatymų puslapyje](/app/settings/email). Ten rasite laiško temą, šablonų pasirinkimą, neprivalomą šablono teksto redagavimą bei logotipo ir prekės ženklo spalvų valdiklius (juos aprašome straipsnyje [Prekės ženklo nustatymai](/lt/brand-customization)).

## Laiško tema

Laiško tema gali būti tiek fiksuotas tekstas, tiek Handlebars stiliaus šablonas, naudojantis šiuos kintamuosius:

- `{{invoiceNo}}` — SF numeris (pvz., `SF/001`)
- `{{buyer}}` — pirkėjo pavadinimas
- `{{seller}}` — pardavėjo pavadinimas
- `{{price}}` — sąskaitos suma su valiuta
- `{{invoiceDate}}` — sąskaitos data

Pavyzdys: `Sąskaita {{invoiceNo}} nuo {{seller}} — {{price}}`.

## Įdiegtieji teksto šablonai

Pasirinkite šabloną pagal tai, kaip turtingai turi atrodyti laiškas:

- **Paprastas tekstas** — paprastas teksto formatas, puikiai veikia visuose el. pašto klientuose.
- **Paprastas HTML** — gražiai suformatuotas HTML laiškas, naudojantis [MJML](https://mjml.io/).
- **Su logotipu** — HTML šablonas su jūsų įmonės logotipu viršuje.
- **Su logotipu ir kaina** — papildomai rodo sąskaitos sumą.
- **Su logotipu, kaina ir papildoma informacija** — papildomai rodo papildomos informacijos lauką.
- **Su logotipu, kaina ir el. pašto pastaba** — apima neprivalomą pastabą, kurią galite įvesti prieš siunčiant.
- **Su eilutės elementais** — apima pilną sąskaitos eilučių lentelę (pavadinimas, kiekis, vieneto kaina, suma) kartu su bendra suma.

Visi HTML šablonai naudoja MJML formatą, kuris puikiai atvaizduoja laišką Gmail, Outlook, Apple Mail, mobiliuose klientuose ir kitur. Jei norite savo šablono, galite parašyti MJML kodą patys arba paprašyti AI įrankio sugeneruoti jį pagal jūsų aprašymą.

## Šablonų kintamieji

Kiekvienas šablonas — tiek įdiegtas, tiek savas — turi prieigą prie tų pačių kintamųjų.

**Pagrindinė informacija:**

- `{{issuer}}` — sąskaitą išrašęs asmuo
- `{{invoiceNo}}` — SF numeris
- `{{buyer}}` — pirkėjas
- `{{seller}}` — pardavėjas
- `{{price}}` — sąskaitos suma
- `{{extra}}` — papildomos informacijos laukas
- `{{userNote}}` — vidinė sąskaitos pastaba
- `{{emailNote}}` — pastaba, įvedama siuntimo metu
- `{{email}}` — pirkėjo el. paštas

**Datos:**

- `{{invoiceDate}}` — sąskaitos data
- `{{created}}` — sąskaitos sukūrimo data (ta pati reikšmė kaip `invoiceDate`)

**Sąskaitos detalės:**

- `{{seriesName}}` — serijos pavadinimas (pvz., `SF`)
- `{{seriesId}}` — numeris serijoje (pvz., `001`)
- `{{language}}` — sąskaitos kalba (`lt`, `en` ir t. t.)

**Logotipas:**

- `{{logoUrl}}` — jūsų įkelto logotipo URL

**Prekės ženklo spalvos:**

- `{{brandPrimary}}`, `{{brandSecondary}}` — pagrindinė ir antraeilė prekės ženklo spalvos
- `{{brandText}}`, `{{brandTextSecondary}}` — teksto ir antraeilė teksto spalvos
- `{{brandBackground}}`, `{{bodyBackground}}`, `{{backgroundSecondary}}` — fono spalvos

Apie šių spalvų nustatymą skaitykite [Prekės ženklo nustatymai](/lt/brand-customization).

## Eilutės elementų ciklas

Norėdami laiške išvardyti sąskaitos eilutes, naudokite Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Kiekvienoje iteracijoje galima naudoti:

- `{{name}}` — prekės pavadinimas
- `{{amount}}` — kiekis
- `{{unit}}` — neapdorotas UN/ECE vieneto kodas (pvz., `H87`)
- `{{unitName}}` — vieneto forma, lokalizuota (pvz., "vienetas", "kilogramas")
- `{{unitSymbol}}` — trumpa vieneto forma, lokalizuota (pvz., "vnt", "kg")
- `{{unitPrice}}` — suformatuota kaina už vienetą (pvz., `€10,00`)
- `{{formattedPrice}}` — suformatuota eilutės suma (kiekis × vieneto kaina)
- `{{vat}}` — PVM procentas, jei nustatytas
- `{{vatcode}}` — PVM kodas, jei nustatytas

## Sąlyginiai blokai

Naudokite Handlebars `{{#if}}`, kad blokas būtų atvaizduojamas tik tada, kai reikšmė užpildyta:

```
{{#if extra}}
  <mj-text>Papildoma informacija: {{extra}}</mj-text>
{{/if}}
```

Tai ypač naudinga neprivalomiems laukams, tokiems kaip `extra`, `userNote`, `emailNote`, kad laiškas atrodytų tvarkingai, kad ir kuris laukas užpildytas.

Taip pat žr.: [El. pašto nustatymai: Gmail (OAuth)](/lt/email-setup-gmail), [El. pašto nustatymai: SMTP](/lt/email-setup-smtp), [Prekės ženklo nustatymai](/lt/brand-customization).
