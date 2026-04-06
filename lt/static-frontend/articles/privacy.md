---
title: 'Privatumo politika'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Čia aprašyta "Haiku.lt" privatumo politika - kokius duomenis mes
renkame ir ką vėliau darome su tai duomenimis.

* Mes renkame šiuo duomenis:

  * IP adresas, data ir laikas, naršyklės informacija.

  * El. pašto adresas.

  * Duomenis, kuriuos jūs įvedate į sistemą ją naudodami.

## Slapukai ir naršyklės saugykla

Mes naudojame slapukus ir naršyklės saugyklą, kad suteiktume pagrindinį
funkcionalumą:

### Slapukai

- **Autentifikacijos slapukas (auth_token)**: Saugus, HTTP-only slapukas,
  naudojamas jūsų prisijungimo sesijai palaikyti. Šis slapukas yra būtinas
  paslaugai veikti ir galioja maždaug 2 mėnesius. Be šio slapuko jūs
  negalite naudotis Haiku.lt.

### Naršyklės vietinė saugykla (Local Storage)

Mes saugome šiuos duomenis jūsų naršyklės vietinėje saugykloje:

- **Kalbos nuostata**: Jūsų pasirinkta sąsajos kalba (lietuvių arba anglų),
  kad užtikrintume greitą UI atvaizdavimą.

- **Pranešimų atmetimas**: Užfiksuojame, ar jūs atmetėte tam tikrus
  pranešimus, kad jų neparodytume pakartotinai.

- **Paskyrų perjungimo sinchronizacija**: Laikini duomenys (ištrinami po
  1 sekundės), naudojami paskyrų perjungimo sinchronizavimui tarp kelių
  naršyklės skirtukų.

### Naršyklės sesijos saugykla (Session Storage)

- **Apsilankymo sekimas**: Tik sesijai skirtas žymeklis, naudojamas
  nukreipimų kilpoms pradiniame puslapyje išvengti. Šie duomenys
  ištrinami uždarant naršyklę.

### Jokių trečiųjų šalių sekimo priemonių

Mes nenaudojame jokių analitikos, reklamos ar trečiųjų šalių sekimo
slapukų. Visi slapukai ir saugykla yra griežtai būtini paslaugai veikti.

## Trečiųjų šalių paslaugos

* **Google paslaugos**: Mes integruojamės su Google paslaugomis, kai prisijungiate per Google OAuth:

  * **Google Drive** (pasirinktinai): Jei suteikiate Google Drive leidimą, mes prieiname:
    * **Ką prieiname**: Haiku.lt sukurtus failus jūsų Google Drive. Naudojame `drive.file` apimtį, kuri suteikia prieigą tik prie mūsų programos sukurtų failų - mes nematome ir neprieiname jokių kitų failų jūsų Drive.
    * **Kaip naudojame**: Kad išsaugotume sąskaitų faktūrų PDF failus jūsų Google Drive organizuotoje aplankų struktūroje (Haiku.lt/Invoices/Metai). Kai naudojate funkciją „Išsaugoti į Drive", mes kuriame arba atnaujiname PDF failus.
    * **Kaip saugome**: Mes saugome Google Drive failo ID mūsų duomenų bazėje, kad galėtume sekti, kurios sąskaitos faktūros buvo išsaugotos ir galėtume atnaujinti esamus failus. Tikrasis PDF turinys nesaugomas mūsų serveriuose - jis egzistuoja tik jūsų Google Drive.
    * **Kaip dalinamės**: Google Drive failų ID niekada nesidalijami su trečiosiomis šalimis, niekada neparduodami duomenų brokeriams ir niekada nenaudojami reklamai, rinkodarai, dirbtinio intelekto mokymui ar bet kokiam kitam tikslui, išskyrus jūsų sąskaitų faktūrų PDF valdymą jūsų Drive.
    * **Kaip valdyti**: Galite valdyti Drive leidimus per savo [Google paskyros leidimus](https://myaccount.google.com/permissions). Failai lieka jūsų Drive ir jūsų kontrolėje. Galite juos ištrinti bet kada. Leidimo atšaukimas sustabdo mūsų galimybę kurti naujus failus ar atnaujinti esamus.
  
  * **Gmail** (pasirinktinai): Jei suteikiate Gmail leidimą, mes prieiname:
    * **Ką prieiname**: Leidimą siųsti el. laiškus per jūsų Gmail paskyrą. Naudojame `gmail.send` apimtį, kuri leidžia siųsti el. laiškus jūsų vardu. Mes neskaitome jūsų esamų el. laiškų ir neprieiname jūsų gautų laiškų.
    * **Kaip naudojame**: Kad išsiųstume sąskaitų faktūrų el. laiškus jūsų pirkėjams, kai naudojate funkciją „Siųsti sąskaitą faktūrą". El. laiškai apima sąskaitos faktūros PDF kaip priedą ir pasirinktinai papildomus priedus (pvz., CII XML e-sąskaitoms).
    * **Kaip saugome**: Mes nesaugome el. laiškų turinio ar išsiųstų pranešimų duomenų. Išsiųsti el. laiškai atsiranda jūsų Gmail „Išsiųsti" aplanke ir lieka jūsų kontrolėje.
    * **Kaip dalinamės**: El. laiškų siuntimo galimybė niekada nesidalijama su trečiosiomis šalimis, niekada neparduodama ir niekada nenaudojama reklamai, rinkodarai, šlamštui ar bet kokiam kitam tikslui, išskyrus sąskaitų faktūrų, kurias aiškiai pasirenkate siųsti, siuntimą.
    * **Kaip valdyti**: Galite valdyti Gmail leidimus per savo [Google paskyros leidimus](https://myaccount.google.com/permissions). Išsiųsti el. laiškai lieka jūsų Gmail paskyroje. Leidimo atšaukimas sustabdo mūsų galimybę siųsti el. laiškus jūsų vardu.
  
  * **Google Calendar** (pasirinktinai, tik skaitymui): Jei suteikiate kalendoriaus leidimą, mes prieiname:
    * **Ką prieiname**: Jūsų kalendorių pavadinimus, įvykių pavadinimus, įvykių datas/laikus ir dalyvavimo būseną (kad išfiltruotume atmestus įvykius). Naudojame Google Calendar API apimtį `calendar.readonly`, kuri suteikia tik skaitymo prieigą.
    * **Kaip naudojame**: Išimtinai tam, kad padėtume jums kurti sąskaitas faktūras pagal kalendoriaus įvykius naudojant funkciją „Kurti iš kalendoriaus". Įvykių pavadinimai tampa sąskaitos faktūros eilutės aprašymais, o įvykių datos padeda nustatyti sąskaitos faktūros datų intervalus.
    * **Kaip saugome**: Kalendoriaus duomenys **nesaugomi ilgalaikiai** mūsų duomenų bazėse. Jie gaunami pagal poreikį tik tada, kai naudojate kalendoriaus sąskaitų faktūrų funkciją ir egzistuoja laikinai jūsų naršyklės atmintyje sąskaitos faktūros kūrimo proceso metu.
    * **Kaip dalinamės**: Kalendoriaus duomenys **niekada nesidalijami** su trečiosiomis šalimis, **niekada neparduodami** duomenų brokeriams ir **niekada nenaudojami** reklamai, rinkodarai, dirbtinio intelekto mokymui ar bet kokiam kitam tikslui, išskyrus sąskaitų faktūrų kūrimą jums.
    * **Kaip valdyti**: Galite valdyti kalendoriaus leidimus nepriklausomai per savo [Google paskyros leidimus](https://myaccount.google.com/permissions). Leidimo atšaukimas nedelsiant sustabdo duomenų prieigą. Taip pat galite atjungti visą savo Google paskyrą per Haiku.lt nustatymus.
    
  Visi Google OAuth leidimai reikalauja jūsų aiškaus įgaliojimo. Jūs kontroliuojate, kuriuos leidimus suteikti, ir galite juos bet kada atšaukti.

* **Stripe**: Mes naudojame Stripe mokėjimų apdorojimui už mokamas prenumeratas.
  Stripe saugiai tvarko visą mokėjimo informaciją pagal jų privatumo politiką.
  Mes gauname tik patvirtinimą apie sėkmingus mokėjimus.

* **Brevo (Sendinblue)**: Mes naudojame Brevo transakcinių el. laiškų pristatymui, įskaitant magiškos nuorodos prisijungimo el. laiškus ir sąskaitų faktūrų el. laiškus. Brevo gauna gavėjo el. pašto adresą ir el. laiško turinį, reikalingą šiems pranešimams pristatyti. Brevo yra ES (Prancūzija). Žr. jų [Privatumo politiką](https://www.brevo.com/legal/privacypolicy/).

## Duomenų apsauga

Tam kad apsaugotumėme surinktus duomenis imamės šių priemonių:

* Atnaujiname serverio programinę įrangą kiek įmanoma dažniau.

* Atnaujiname haiku.lt programinę įrangą kiek įmanoma dažniau.

* Tinkamai sukonfigūruoti serveriai.

## Jūsų teisės

Išsamesnei informacijai apie jūsų duomenų teises pagal BDAR, įskaitant teisę
pasiekti, ištrinti ir eksportuoti savo duomenis, žiūrėkite mūsų
[BDAR puslapį](/lt/gdpr).
