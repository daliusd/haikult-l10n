---
title: 'Apmokėjimo terminai ir sąlygos'
date: '2026-05-23'
modified: '2026-05-23'
---

Beveik kiekvienoje sąskaitoje reikia nurodyti, iki kada ji turi būti apmokėta. „Haiku.lt“ saugo kiekvienos sąskaitos apmokėjimo terminą ir leidžia nustatyti, kaip jis turi būti skaičiuojamas pagal nutylėjimą. Šiame straipsnyje aptarsime apmokėjimo termino lauką sąskaitos formoje, numatytojo termino nustatymą ir kaip apmokėjimo sąlygas atvaizduoti išgeneruotame PDF dokumente, kuris siunčiamas pirkėjui.

## Apmokėjimo termino laukas

![Apmokėjimo termino laukas papildomoje naujos sąskaitos formos srityje](/screenshots/due-dates-and-payment-terms/lt/step-1-due-date-field.png)

**Apmokėjimo terminas** yra sąskaitos formos „Papildoma“ srityje, šalia išrašytojo ir pastabų laukų. Kuriant naują sąskaitą, „Haiku.lt“ šį lauką užpildo automatiškai pagal jūsų pasirinktą numatytąjį nustatymą (žr. žemiau). Reikšmę visada galite pakeisti konkrečiai sąskaitai — atidėti apmokėjimą tam tikram pirkėjui arba visai pašalinti terminą, jei jis netaikomas.

Sistemoje apmokėjimo terminas saugomas kaip įprasta kalendorinė data. „Haiku.lt“ pagal ją sąskaitų sąraše paryškina pradelstas sąskaitas, todėl tiksli reikšmė padeda greitai pastebėti vėluojančius mokėjimus.

## Numatytojo termino nustatymas

![Numatytojo apmokėjimo termino nustatymas sąskaitų nustatymų puslapyje](/screenshots/due-dates-and-payment-terms/lt/step-2-due-date-default.png)

Numatytasis apmokėjimo terminas nustatomas **Sąskaitų nustatymų** puslapyje. Galimi keturi variantai:

- **Nėra** — terminas automatiškai nenustatomas; jį kiekvieną kartą įveskite rankiniu būdu.
- **Dienų nuo sąskaitos datos** — prie sąskaitos datos pridedamas pastovus dienų skaičius (pagal nutylėjimą 30). Tai dažniausias pasirinkimas, jei taikote 14, 30 ar panašių dienų terminus.
- **Mėnesio diena** — pasirenkama konkreti mėnesio diena, pavyzdžiui, 10-oji. Jei sąskaitos data jau praleidusi šią dieną, terminas perkeliamas į tą pačią kito mėnesio dieną.
- **Mėnesio pabaiga** — paskutinė sąskaitos mėnesio diena.

Kad ir kurį režimą pasirinktumėte, gausite tik automatiškai užpildytą reikšmę — atskirose sąskaitose ją vis tiek galėsite redaguoti. Nustatymas pakeičia tik tai, kokia data parodoma sukūrus naują sąskaitą; jau išsaugotų sąskaitų terminai nesikeičia.

## Apmokėjimo sąlygų rodymas PDF dokumente

Apmokėjimo terminas saugomas kartu su sąskaita, tačiau PDF dokumente automatiškai nepasirodo. Norėdami atspausdinti eilutę „Prašome apmokėti iki 2026-06-22“ pačiame dokumente, naudokite sąskaitos lauką **Papildoma informacija**. Tekstą galite įvesti rankiniu būdu arba leisti „Haiku.lt“ jį užpildyti automatiškai naudodami papildomos informacijos programą.

Programa gali pasiekti kintamąjį `dueDate`, todėl trumpa iškarpa, pavyzdžiui:

```js
// AUTO
if (dueDate) {
  globalThis.result = `Prašome apmokėti sąskaitą iki ${formatDate(dueDate)}`;
}
```

apmokėjimo sąlygas kiekvienoje sąskaitoje sinchronizuos su apmokėjimo terminu. Išsamesnių pavyzdžių — įskaitant tekstą pagal kalbą ir derinimą su apmokėjimo būdais — rasite straipsnyje [Papildomos informacijos programavimas](/lt/extra-info-programming).
