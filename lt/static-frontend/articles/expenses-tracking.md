---
title: 'Išlaidų sekimas'
date: '2026-03-22'
modified: '2026-05-24'
---

Haiku seka verslo išlaidas šalia jūsų sąskaitų. Įkelkite sąskaitą ar kvitą, leiskite sistemai automatiškai išskaityti duomenis, kai įmanoma, ir laikykite failus tvarkingai Haiku sistemoje ir (arba) Google Drive.

## Išlaidų puslapis

![Išlaidų puslapis](/screenshots/expenses-tracking/lt/step-1-expenses-list.png)

**Išlaidų** puslapis rodo visas užfiksuotas išlaidas su greita prieiga prie redagavimo, trynimo, saugomo failo atidarymo ar originalo atsisiuntimo.

Filtravimas:

- **Datų intervalas** — pasirinkite konkretų mėnesį, ketvirtį ar pasirinktinį laikotarpį.
- **Paieška pagal aprašymą** — raskite išlaidą pagal raktinį žodį.
- **Bendra suma** — pagal dabartinį filtrą atitinkančių išlaidų skaičius ir suma puslapio viršuje.

Kiekviena kortelė rodo aprašymą, pardavėją, sumą, datą ir saugojimo būseną (Haiku, Drive ar abu).

## Išlaidos pridėjimas

Išlaidų puslapyje paspauskite **Nauja išlaida**. Atsidaro 4 žingsnių vedlys.

### 1 žingsnis — Įkelkite dokumentą

Nutempkite arba pasirinkite failą. Palaikomi formatai: **PDF**, **JPEG**, **PNG**, **XML** — tinka skenuotiems kvitams ir elektroninėms sąskaitoms.

### 2 žingsnis — Automatinis duomenų nuskaitymas

Jei failas yra standartinė elektroninė sąskaita (Factur-X PDF, paplitęs Prancūzijoje ir Vokietijoje; e-invoice XML), Haiku išskaitys:

- Sąskaitos numerį
- Pardavėjo pavadinimą
- Eilutes
- Bendrą sumą
- Išrašymo datą

Skenuotiems vaizdams ar nestruktūruotiems PDF forma atsidaro tuščia ir duomenis įvedate patys.

### 3 žingsnis — Peržiūra, redagavimas ir saugojimo pasirinkimas

Atsiranda iš anksto užpildyta forma. Pataisykite, kas netiksli, tada pasirinkite, kur saugoti failą:

- **Įkelti į Haiku** — iki 2 MB, saugiai laikoma jūsų paskyroje.
- **Įkelti į Google Drive** — į specialų aplanką jūsų Drive (reikia autorizacijos — žr. [Google Drive integracija](/lt/google-drive-integration)).

Galite pasirinkti vieną, abu arba nieką. Pati išlaidos kortelė visada išsaugoma, nepriklausomai nuo to, kur eina failas.

### 4 žingsnis — Išsaugota

Patvirtinimas. Iš čia galite pridėti kitą išlaidą arba grįžti į sąrašą.

## Redagavimas ir trynimas

Kiekviena išlaida turi **Redaguoti** mygtuką, leidžiantį atnaujinti bet kurį lauką — aprašymą, pardavėją, sumą, datą, eilutes, saugojimo pasirinkimą. **Trinti** mygtukas pašalina įrašą po patvirtinimo.

Išlaidos trynimas neištrina Google Drive failo. Jei norite pašalinti ir debesyje esančią kopiją, pirmiausia kortelėje paspauskite **Trinti iš Drive**.

## Išmanus sąskaitų nuskaitymas

Haiku skaito sąskaitas standartiniais elektroniniais formatais, naudojamais visoje Europoje:

- **Factur-X / ZUGFeRD** PDF — paplitę pas Vokietijos ir Prancūzijos tiekėjus.
- **UBL / Peppol / EN 16931** XML — ES elektroninio sąskaitų išrašymo standartas.

Nepalaikomiems formatams ar nuotraukoms 3 žingsnio laukai lieka tušti ir užpildomi rankomis.
