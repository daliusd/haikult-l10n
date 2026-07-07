---
title: 'Masinis sąskaitų redagavimas'
date: '2026-05-24'
modified: '2026-05-24'
---

Kai reikia atlikti veiksmą su daug sąskaitų iš karto — išsiųsti, išsaugoti PDF Google Drive, pažymėti kelias kaip apmokėtas, pakeisti sumas — **Multi-Edit** vedlys paleidžia operaciją masiškai su vienu peržiūros žingsniu.

## Vedlio atidarymas

![Multi-Edit puslapis](/screenshots/batch-edit-invoices/lt/step-1-multi-edit.png)

Sąskaitų puslapyje paspauskite **Multi-Edit**. Vedlys atsidaro adresu **/invoices/multi-edit**.

## 1 žingsnis — Operacijos pasirinkimas ir filtravimas

Pirmame žingsnyje rodomi suvestiniai skaičiai (iš viso, neišsiųstos, neapmokėtos ir kt.) ir galima filtruoti sąrašą pagal datų intervalą ir sąskaitos tipą. Pasirinkite operaciją:

- **Kurti naujas sąskaitas masiškai** — atidaro kūrimo iš kalendoriaus srautą.
- **Siųsti neišsiųstas sąskaitas** — el. paštu išsiunčia PDF ir nuorodas klientams.
- **Pažymėti kaip apmokėtas** — nustato apmokėjimo žymą ir (pasirinktinai) apmokėjimo datą.
- **Saugoti PDF į Google Drive** — įkelia į jūsų Drive aplanką.
- **Trinti iš Google Drive** — pašalina PDF kopiją (sąskaita lieka Haiku sistemoje).
- **Keisti sumą** — pritaiko procentinę ar fiksuotą korekciją eilutėms.
- **Trinti iš sistemos** — galutinai pašalina pasirinktas sąskaitas.

## 2 žingsnis — Sąskaitų pasirinkimas

Pasirodo filtruotas sąrašas su žymės langeliais. Pažymėkite norimas įtraukti eilutes arba pasinaudokite antraštės žymės langeliu pažymėti viską. Užrakintos sąskaitos negali būti redaguojamos ar joms keičiamos sumos — toms operacijoms jos automatiškai praleidžiamos.

## 3 žingsnis — Operacijos konfigūravimas

Kiekviena operacija turi savo konfigūravimo formą:

- **Siųsti**: pasirinkite el. laiško šabloną, pagal poreikį pakeiskite temą / tekstą.
- **Pažymėti kaip apmokėtas**: pasirinkite apmokėjimo datą.
- **Saugoti į Drive**: patvirtinkite tikslinį aplanką (pagal nutylėjimą `Haiku.lt/Invoices/YYYY/`).
- **Keisti sumą**: įveskite procentą arba fiksuotą skirtumą ir pažymėkite, ar įtraukti PVM.
- **Trinti**: patvirtinkite.

Paspauskite **Pritaikyti**, kad operacija būtų vykdoma. Eigos juosta rodo, kaip apdorojama kiekviena sąskaita.

## 4 žingsnis — Rezultatai

Suvestinėje rodomos sėkmingos ir nepavykusios eilutės. Prie nepavykusių nurodoma priežastis (užrakinta sąskaita, nėra el. pašto, baigėsi Drive autorizacija ir pan.), kad galėtumėte ištaisyti ir paleisti dar kartą.

## Ko negalima keisti masiškai

- **Užrakintos sąskaitos** — užrakinimas yra sąmoningas signalas, kad sąskaita galutinė. Atrakinkite po vieną.
- **Pirkėjo ar pardavėjo duomenys** — kiekvienai sąskaitai individualūs ir nerodomi masiniam redagavimui, kad nebūtų netyčia perrašyti.
- **Sąskaitų numeriai ir serijos** — valdomi per [sąskaitų serijas ir numeraciją](/lt/invoice-series-and-numbering).

## Sąveika su Auto programomis

Jei naudojate [papildomos informacijos programavimą](/lt/extra-info-programming), bet kuri programa su `// AUTO` viršuje bus paleista iš naujo masinio redagavimo metu ir perskaičiuos papildomos informacijos lauką kiekvienai sąskaitai pakete. Tai tinkamiausia vieta vienu metu perskaičiuoti dinaminį turinį (pvz. atnaujintas mokėjimo sąlygas) visoms mėnesio sąskaitoms.
