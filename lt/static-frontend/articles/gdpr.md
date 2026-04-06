---
title: 'BDAR - Jūsų duomenų teisės'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

„Haiku.lt" įsipareigoja apsaugoti Jūsų asmens duomenis ir gerbti Jūsų privatumo teises pagal Bendrąjį duomenų apsaugos reglamentą (BDAR). Šis puslapis paaiškina Jūsų teises ir kaip mes tvarkome Jūsų duomenis.

## Jūsų duomenų teisės

Pagal BDAR, Jūs turite šias teises susijusias su Jūsų asmens duomenimis:

### Teisė į prieigą

Jūs turite teisę gauti prieigą prie visų asmens duomenų, kuriuos mes saugome apie Jus. Galite eksportuoti savo duomenis bet kuriuo metu:

- **Pilnas duomenų bazės eksportas**: Atsisiųskite visą duomenų bazę, įskaitant visas sąskaitas faktūras, nustatymus ir audito įrašus iš savo paskyros nustatymų.
- **Sąskaitų faktūrų eksportas**: Eksportuokite sąskaitas faktūras CSV formatu, filtruojant pagal datos intervalą ir serijos pavadinimą.

### Teisė būti pamirštam (ištrynimo teisė)

Jūs turite teisę reikalauti ištrinti savo asmens duomenis. Galite bet kuriuo metu ištrinti visą savo paskyrą ir visus susijusius duomenis per paskyros nustatymus. Šis veiksmas yra galutinis ir negali būti atšauktas.

### Teisė į duomenų perkeliamumą

Galite eksportuoti savo duomenis mašininiu būdu skaitomais formatais:

- SQLite duomenų bazės formatu (pilnas duomenų eksportas)
- CSV formatu (sąskaitų faktūrų duomenų eksportas)

Tai leidžia perkelti savo duomenis į kitą paslaugą, jei pasirinksite.

### Teisė į ištaisymą

Jūs turite teisę ištaisyti netikslią ar neišsamią asmeninę informaciją. Galite redaguoti visus savo duomenis tiesiogiai programoje, įskaitant:

- Sąskaitų faktūrų detales
- Pirkėjo ir pardavėjo informaciją
- Savo asmeninius nustatymus ir parinktis

### Teisė į duomenų tvarkymo apribojimą

Jūs turite teisę reikalauti apriboti savo asmens duomenų tvarkymą tam tikrais atvejais. Susisiekite su mumis naudodami žemiau nurodytą el. paštą, kad įgyvendintumėte šią teisę.

### Teisė nesutikti

Jūs turite teisę nesutikti su savo asmens duomenų tvarkymu tam tikrais tikslais. Kadangi „Haiku.lt" tvarko Jūsų duomenis tik tam, kad suteiktų Jūsų prašomą sąskaitų faktūrų valdymo paslaugą, nesutikimas su tvarkymu neleis mums teikti paslaugos.

## Duomenų saugojimas

Jūsų duomenys saugomi **kol Jūs ištrinsite savo paskyrą**. Mes automatiškai neištriname neaktyvių paskyrų. Jūs visiškai kontroliuojate, kada Jūsų duomenys pašalinami.

Kai ištrinsite savo paskyrą, visi Jūsų duomenys yra visam laikui pašalinami iš mūsų sistemų.

## Duomenų valdytojas

„Haiku.lt" duomenų valdytojas yra:

**Dalius Dobravolskas**

Privatumo klausimais arba norėdami įgyvendinti savo duomenų teises, susisiekite:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Serverio vieta

Visi „Haiku.lt" serveriai ir duomenų saugykla yra **Europos Sąjungoje, tiksliau Vokietijoje**. Jūsų duomenys nepalieka ES, nebent aiškiai įgaliosite trečiųjų šalių integraciją (žiūrėkite Duomenų tvarkytojai žemiau).

## Teisinis pagrindas duomenų tvarkymui

Mes tvarkome Jūsų asmens duomenis pagal:

- **Sutarties vykdymą**: Kad suteiktume sąskaitų faktūrų valdymo paslaugą, kuriai užsiregistravote
- **Teisėtą interesą**: Kad išlaikytume paslaugos saugumą, užkirstume kelią sukčiavimui ir pagerintume paslaugą
- **Sutikimą**: Papildomoms funkcijoms, tokioms kaip „Google Drive" ir „Gmail" integracija

## Duomenų tvarkytojai

„Haiku.lt" naudoja šias trečiųjų šalių paslaugas savo funkcionalumui teikti:

### Google LLC

**Naudojamos paslaugos**: OAuth 2.0 autentifikacija, Google Drive API, Gmail API, Google Calendar API

**Bendrinami duomenys**: El. pašto adresas, vardas, OAuth žetonai (tik kai įgaliojate Google integraciją)

**Tikslas**: Kad galėtumėte:
- **Autentifikuotis** su savo Google paskyra naudojant OAuth 2.0
- **Google Drive** (apimtis: `drive.file`): Išsaugoti sąskaitų faktūrų PDF failus jūsų Drive organizuotuose aplankuose (Haiku.lt/Invoices/Metai). Mes galime prieiti tik prie mūsų programos sukurtų failų, ne prie kitų jūsų Drive failų. Mes saugome Drive failų ID, kad galėtume sekti išsaugotas sąskaitas faktūras.
- **Gmail** (apimtis: `gmail.send`): Siųsti sąskaitų faktūrų el. laiškus pirkėjams jūsų vardu. Mes neskaitome jūsų gautų laiškų ar esamų el. laiškų. Išsiųsti el. laiškai atsiranda jūsų Gmail „Išsiųsti" aplanke.
- **Google Calendar** (apimtis: `calendar.readonly`, pasirinktinai): Skaityti kalendoriaus įvykių pavadinimus, datas, laikus ir dalyvavimo būseną, kad padėtume kurti sąskaitas faktūras. Šie duomenys gaunami laikinai ir nesaugomi ilgalaikiai.

**Duomenų saugojimas**: 
- Drive failų ID: Saugomi mūsų duomenų bazėje, kol ištrinate sąskaitą faktūrą arba atjungiate savo Google paskyrą
- Kalendoriaus duomenys: Nesaugomi (gaunami tik pagal poreikį)
- Gmail duomenys: Nesaugomi (el. laiškai lieka jūsų Gmail paskyroje)
- OAuth žetonai: Užšifruoti ir saugomi, kol atjungiate savo paskyrą

**Privatumo politika**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Vieta**: Jungtinės Amerikos Valstijos (su ES-JAV duomenų privatumo programos atitikimu)

### Stripe, Inc.

**Naudojamos paslaugos**: Mokėjimų apdorojimas prenumeratoms

**Bendrinami duomenys**: El. pašto adresas, mokėjimo informacija (tvarkoma tiesiogiai per Stripe)

**Tikslas**: Apdoroti prenumeratos mokėjimus už premium funkcijas

**Privatumo politika**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Vieta**: Jungtinės Amerikos Valstijos (su ES-JAV duomenų privatumo programos atitikimu)

### Brevo (Sendinblue)

**Naudojamos paslaugos**: Transakcinių el. laiškų pristatymas

**Bendrinami duomenys**: Gavėjo el. pašto adresas, el. laiško turinys (prisijungimo magiškos nuorodos žetonai; sąskaitos faktūros detalės siunčiant sąskaitas faktūras per Brevo)

**Tikslas**: Pristatyti autentifikacijos el. laiškus (magiškos nuorodos prisijungimas) ir sąskaitų faktūrų el. laiškus pirkėjams

**Duomenų saugojimas**: Brevo gali saugoti išsiųstų el. laiškų žurnalus ribotą laikotarpį pagal jų politiką. Mes nesaugome el. laiško turinio savo serveriuose ilgiau, nei reikia jį išsiųsti.

**Privatumo politika**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Vieta**: Europos Sąjunga (Prancūzija)

## Duomenų saugumas

Imamės atitinkamų techninių ir organizacinių priemonių Jūsų asmens duomenims apsaugoti:

- Jautrių duomenų šifravimas (OAuth žetonai, atnaujinimo žetonai)
- Saugus HTTPS ryšys
- HTTP-only, saugūs autentifikacijos slapukai
- Reguliarūs programinės įrangos atnaujinimai
- Kiekvieno vartotojo duomenų bazės izoliacija
- Audito įrašai paskyros prieigos sekimui

## Pranešimas apie duomenų pažeidimus

Mažai tikėtinu duomenų pažeidimo atveju, kuris kelia riziką Jūsų teisėms ir laisvėms, mes praneškime Jums ir atitinkamai priežiūros institucijai per 72 valandas, kaip reikalauja BDAR.

## Priežiūros institucija

Jei turite nuogąstavimų dėl to, kaip mes tvarkome Jūsų asmens duomenis, turite teisę pateikti skundą savo vietinei duomenų apsaugos priežiūros institucijai.

Lietuvos vartotojams priežiūros institucija yra:

**Valstybinė duomenų apsaugos inspekcija**  
Interneto svetainė: [https://vdai.lrv.lt](https://vdai.lrv.lt)

## Šios politikos atnaujinimai

Mes galime laikas nuo laiko atnaujinti šį BDAR informacijos puslapį. „Pakeista" data šio puslapio viršuje nurodo, kada jis buvo paskutinį kartą atnaujintas.

Bendrąjai privatumo informacijai žiūrėkite mūsų [Privatumo politiką](/lt/privacy).
