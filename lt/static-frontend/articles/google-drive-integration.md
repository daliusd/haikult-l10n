---
title: 'Google Drive integracija'
date: '2026-05-24'
modified: '2026-05-24'
---

Haiku gali tiesiogiai išsaugoti sąskaitų PDF ir išlaidų failus į jūsų Google Drive nuosekliai sutvarkytoje aplankų struktūroje su aiškiais failų pavadinimais — viskas susitvarko be rankinio rūšiavimo.

## Drive autorizavimas

1. Eikite į **Nustatymai → Google Drive**.
2. Paspauskite **Prijungti Google Drive** ir užbaikite Google autorizacijos langą.
3. Atsiranda patvirtinimas, kai Haiku gauna leidimą kurti failus specialiame Haiku aplanke.

Haiku rašo tik į savo aplanko medį. Sistema neskaitys ir nematys kitų jūsų Drive aplankų.

## Aplankų struktūra

Failai dedami po pagrindiniu `Haiku.lt` aplanku, suskirstyti pagal tipą ir metus:

```
Haiku.lt
  ├── Invoices
  │     └── 2026
  │           └── INV-2026-045.pdf
  └── Expenses
        └── 2026
              └── 2026-05-12-acme-supplies.pdf
```

Metų aplankas sukuriamas automatiškai pirmą kartą įkeliant failą tiems metams.

## Failų pavadinimai

**Sąskaitos** — failas pavadinamas pagal serijos ir numerio derinį (pvz. `INV-2026-045.pdf`). Užrakinimas ir pakartotinis išsaugojimas perrašo esamą failą, o ne sukuria dublikatą.

**Išlaidos** — failai pavadinami pagal datą ir pardavėjo arba aprašymo sutrumpinimą (pvz. `2026-05-12-acme-supplies.pdf`), kad būtų lengva rasti neatidarant.

## Kada failai atsiduria Drive

| Veiksmas | Įkeliama į Drive? |
|---|---|
| Sukurti sąskaitą | Ne — rankiniu būdu per **Saugoti PDF į Drive** arba masiškai per Multi-Edit |
| Užrakinti sąskaitą | Ne — užrakinimas nepriklauso nuo Drive |
| Siųsti sąskaitą el. paštu | Ne — saugojimas į Drive yra atskiras veiksmas |
| Pridėti išlaidą su pažymėtu „Įkelti į Drive" | Taip — įkeliama 3 žingsnyje |
| Multi-Edit → Saugoti PDF į Drive | Taip — pasirinktos sąskaitos įkeliamos masiškai |
| Trinti išlaidą | Ne — failas lieka Drive; naudokite **Trinti iš Drive** kortelėje |

Toks atskyrimas yra sąmoningas: užrakinimas ir siuntimas susiję su apskaitos būsena, o Drive saugojimas — su archyvavimu. Tai gali vykti skirtingu laiku.

## Masiniai veiksmai

Norėdami iš karto perkelti viso mėnesio sąskaitas į Drive, naudokite [masinio redagavimo vedlį](/lt/batch-edit-invoices) — jis turi tiek **Saugoti PDF į Google Drive**, tiek **Trinti iš Google Drive** operacijas.

## Prieigos atšaukimas

Atjungti Drive: **Nustatymai → Google Drive → Atjungti**. Esami failai Drive lieka — atjungimas tik sustabdo naujų failų įkėlimą.

Taip pat galite atšaukti prieigą tiesiogiai per Google: [myaccount.google.com/permissions](https://myaccount.google.com/permissions). Haiku atpažins atšaukimą kito įkėlimo metu ir paragins prisijungti iš naujo.
