---
title: 'Pigu integracija: nustatymas ir sąskaitų valdymas'
date: '2026-05-04'
modified: '2026-05-24'
---

Pigu integracija sujungia jūsų Haiku paskyrą su Pigu prekyvietės šeima — pigu.lt, 220.lv, kaup24.ee ir hobbyhall.fi — kad galėtumėte peržiūrėti užsakymus ir kurti sąskaitas faktūras nekeisdami sistemų.

---

## 1 žingsnis — Prisijunkite prie Pigu paskyros

![Pigu nustatymų puslapis](/screenshots/pigu-integration/lt/step-1-pigu-settings.png)

1. Eikite į **Nustatymai → Pigu**.
2. Įveskite Pigu pardavėjo **vartotojo vardą** ir **slaptažodį**, tada spauskite **Prisijungti**.
3. Atsiras žalias ženkliukas **Prisijungta**, rodantis parduotuvės pavadinimą ir sesijos galiojimo pabaigos datą.

Jūsų prisijungimo duomenys naudojami prieigos raktui gauti.

---

## 2 žingsnis — Sukonfigūruokite kiekvienos šalies kortelę

Po prisijungimo visos prekyvietės kanalai, kurie aktyvūs jūsų paskyroje, atsiranda kaip kortelės: **LT**, **LV**, **EE** arba **FI**. Atidarykite kiekvieną kortelę, kurioje parduodate, ir užpildykite žemiau esančius nustatymus.

### Sąskaitų numeracija

| Laukas | Ką įvesti |
|---|---|
| Sąskaitos serija | Standartinių sąskaitų serijos pavadinimas (pvz. `PIG`) |
| Išankstinių SF serija | Išankstinių sąskaitų serijos pavadinimas |
| Kreditinių SF serija | Kreditinių sąskaitų serijos pavadinimas |

### Pardavėjo informacija

| Laukas | Ką įvesti |
|---|---|
| Pardavėjas | Visas pardavėjo blokas — pavadinimas, adresas ir kt. — kaip turi atsirasti sąskaitose |
| Sąskaitą išrašė | Sąskaitą pasirašantis asmuo arba pareigos |
| Papildoma informacija | Bet koks tekstas, spausdinamas sąskaitos apačioje. Palaikomi Handlebars šablonai su užsakymo ir sąskaitos kintamaisiais. |
| Pardavėjo šalis | Jūsų registracijos šalis — pagal nutylėjimą atitinka kanalo šalį, keiskite tik jei skiriasi |
| PVM kodas | Automatiškai paimamas iš bendrųjų nustatymų; jei šiam kanalui reikia kito kodo — įveskite čia |
| Įmonės kodas | Automatiškai paimamas iš bendrųjų nustatymų; jei reikia — perrašykite |

Papildomos informacijos pavyzdys:

```
Order: {{app_name}}/{{external_id}}
{{#if invoice.invoiceReference}}Standard invoice reference: {{invoice.invoiceReference}}{{/if}}
{{#if invoice.buyerTaxId}}Reverse charge (Directive 2006/112/EC){{/if}}
```

### PVM nustatymai

Šie laukai rodomi tik kai nustatytas PVM kodas.

- **Kurti PVM sąskaitas faktūras** — įjunkite, kad sąskaitose būtų nurodytas PVM.
- **Nulinė PVM norma užsakymams** — įjunkite, jei kai kurie užsakymai apmokestinami nuline PVM norma (pvz. tarpvalstybiniai B2B pardavimai).

Po kiekvienos kortelės konfigūravimo spauskite **Išsaugoti**.

---

## 3 žingsnis — Pradėkite nuo rankinio sąskaitų kūrimo

> **Rekomendacija:** Iš pradžių palikite visą automatizavimą išjungtą.

Atidarykite **Pigu užsakymų** puslapį, keliems tikriems užsakymams sukurkite sąskaitas rankiniu būdu ir patikrinkite, ar serijų kodai, pardavėjo blokas ir PVM sumos atrodo tinkamai. Nustatymus daug lengviau koreguoti šiame etape nei po to, kai automatiškai sugeneruotos šimtai sąskaitų.

Kai būsite patenkinti rezultatu, pereikite prie 4 žingsnio.

---

## 4 žingsnis — Įjunkite automatizavimą (neprivaloma)

Kai būsite įsitikinę, kad konfigūracija teisinga, galite įjungti automatinį veikimą kiekvienam kanalui:

| Nustatymas | Ką daro |
|---|---|
| **Automatiškai kurti standartines SF** | Standartinė sąskaita kuriama automatiškai, kai užsakymas įvykdytas ir apmokėtas |
| **Automatiškai kurti kreditines SF** | Kreditinė sąskaita kuriama automatiškai, kai užsakymas grąžinamas arba atmetamas |
| **Automatiškai įkelti SF į Pigu** | Standartinės sąskaitos PDF automatiškai siunčiamas į Pigu po sukūrimo, kad pirkėjas galėtų jį matyti. Reikalauja, kad būtų įjungtas *Automatiškai kurti standartines SF* |
| **Siųsti kasdienį veiklos el. laišką** | Gaunate kasdienį el. laiškų suvestinę apie automatiškai sukurtas sąskaitas |

### Kaip veikia automatizavimas

Užduotis paleidžiama kartą per dieną **3:00 val. Vilniaus laiku**. Kiekvieno paleidimo metu gaunami per **paskutines 48 valandas** atnaujinti užsakymai iš visų jūsų aktyvių kanalų (LT, LV, EE, FI) — iki 5 000 užsakymų vienam kanalui. Išankstinės sąskaitos automatiškai nekuriamos — tik standartinės ir kreditinės.

> **Patarimas:** Pirmiausia įjunkite automatinį kūrimą ir stebėkite vieną dieną, prieš įjungdami automatinį įkėlimą. Tai suteikia galimybę pastebėti formatavimo problemas, kol pirkėjai dar nematė PDF failų.

---

## Užsakymų puslapis

Eikite į **Pigu užsakymai**, kad naršytumėte prekyvietės užsakymus ir rankiniu būdu valdytumėte sąskaitas.

### Filtrai

Susiaurinkite sąrašą pagal **kanalą**, **užsakymo ID**, **užsakymo būseną** (įvykdytas, grąžintas, atmestas) ir **datų intervalą** (atnaujinta nuo / iki). Pagal nutylėjimą rodoma paskutinių 24 valandų informacija.

### Veiksmai kiekvienam užsakymui

Kiekvienoje eilutėje rodomas pirkėjas, suma, užsakymo būsena, mokėjimo būsena ir visos jau sukurtos sąskaitos. Stulpelyje **Veiksmai**:

- **Sukurti sąskaitą** — sukuria tinkamo tipo sąskaitą. Mygtuko užrašas nurodo, kas bus sukurta: *Sukurti išankstinę SF*, *Sukurti standartinę SF* arba *Sukurti kreditinę SF*.
- **Įkelti PDF** — siunčia standartinės sąskaitos PDF į Pigu. Po įkėlimo mygtuką pakeičia tekstas *Įkelta į Pigu*.

### Masiniai veiksmai

Puslapio viršuje du masinių veiksmų mygtukai veikia su visais tinkamais užsakymais dabartiniame filtruotame rodinyje:

- **Masiškai kurti sąskaitas** — sukuria sąskaitas kiekvienam užsakymui, kuriam jos reikia.
- **Masiškai įkelti PDF** — įkelia PDF failus kiekvienai standartinei sąskaitai, kuri dar nebuvo išsiųsta.

Vykdant operaciją rodoma eigos juosta. Įvykus klaidai apdorojimas sustoja ir rodoma klaidos žinutė, kad galėtumėte ištirti problemą prieš bandydami dar kartą.
