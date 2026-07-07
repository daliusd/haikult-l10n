---
title: 'Masinis sąskaitų kūrimas iš Google Calendar'
date: '2026-05-24'
modified: '2026-05-24'
---

„Kurti iš kalendoriaus" vedlys per keturis žingsnius paverčia Google Calendar įvykius sąskaitomis. Kiekvienas unikalus įvykio pavadinimas tampa atskira sąskaita, o pasikartojimų skaičius — kiekiu.

## Kaip įvykiai tampa sąskaitomis

Vedlys grupuoja įvykius pagal pavadinimą ir taiko šią logiką:

- Visi to paties pavadinimo įvykiai sugrupuojami į vieną sąskaitą.
- Susitikimų skaičius tampa kiekiu.
- Įvykiai be pavadinimo ir atmesti susitikimai praleidžiami.
- Pasikartojantys įvykiai išskleidžiami — kiekvienas pasikartojimas skaičiuojamas atskirai.
- Pirkėjo duomenys (el. paštas, šalis, mokesčių kodas, kalba, paskutinė kaina) automatiškai užpildomi iš ankstesnių to vardo sąskaitų.

## Ko reikia

- Haiku.lt paskyros (nemokamai iki 500 sąskaitų).
- Google Calendar su susitikimais — naudokite nuoseklius įvykių pavadinimus, paprastai kliento vardą.
- Google Calendar leidimo, suteikiamo prisijungiant per Google.

Kalendoriaus turinys nuskaitomas tik laikinai, kol veikia vedlys, ir niekur nesaugomas.

## 1 žingsnis — Atidarykite vedlį

![Kurti iš kalendoriaus vedlys](/screenshots/bulk-create-from-calendar/lt/step-1-wizard.png)

Valdymo skydelyje paspauskite **Kurti iš kalendoriaus**. Atsidaro keturių žingsnių vedlys.

## 2 žingsnis — Sukonfigūruokite importą

| Laukas | Ką įvesti |
|---|---|
| Kalendorius | Kurį Google kalendorių skaityti. Pagrindinis pažymėtas „(Pagrindinis)". |
| Datų intervalas | Laikotarpis, už kurį išrašyti. Pagal nutylėjimą — einamasis mėnuo. Vedlys rodo gyvai įvykių skaičių tame intervale. |
| Sąskaitų serija | Serijos kodas (pvz. `TERAPIJA`, `KOUCINGAS`). Pasiūlymai iš jūsų paskutinių serijų. |
| Pardavėjas | Jūsų pardavėjo blokas — automatiškai paimamas iš paskutinės šios serijos sąskaitos. |
| Išrašė | Pasirašantis asmuo arba pareigos — taip pat automatiškai užpildoma. |
| Eilutės pavadinimas | Už ką išrašoma (pvz. „Terapijos sesija"). Pradėkite rašyti — pasirodys pasiūlymai iš istorijos. |
| Numatytoji kaina | Standartinis įkainis. Naudojamas klientams be ankstesnės kainos. |
| PVM % | Rodomas tik jei PVM įjungtas nustatymuose. |
| Vienetas | Pagal nutylėjimą „vnt."; iš sąrašo galima rinktis „val." ar kitus. |

Kai užpildomi privalomi laukai ir vedlys randa bent vieną įvykį, mygtukas **Toliau** tampa aktyvus.

## 3 žingsnis — Peržiūra ir redagavimas

Atsiranda lentelė su viena eilute kiekvienam unikaliam įvykio pavadinimui. Visi stulpeliai redaguojami:

- **Pirkėjo vardas** — įvykio pavadinimas, koreguokite, jei kalendoriuje vardai neformalūs.
- **Kiekis** — rastas susitikimų skaičius.
- **El. paštas**, **šalis**, **mokesčių kodas** — automatiškai paimama iš sąskaitų istorijos, jei yra.
- **Sąskaitos kalba** — 39 variantai; pagal nutylėjimą paskutinė pirkėjui naudota kalba.
- **Kaina** — paimama iš paskutinės sąskaitos tam pirkėjui + eilutės deriniui; jei nėra — naudojama numatytoji.

Galite:

- Pašalinti eilutę, kad praleistumėte klientą šį kartą.
- Pridėti pirkėją rankomis mygtuku **+ Pridėti pirkėją** (pvz. sesija už kalendoriaus ribų).
- Pakoreguoti bet kurią ląstelę vienkartiniam atvejui ištaisyti.

Kai lentelė teisinga, paspauskite **Sukurti N sąskaitų**.

## 4 žingsnis — Kūrimas ir rezultatai

Eigos juosta rodo „Kuriama sąskaita X iš Y…" kuriant kiekvieną sąskaitą. Daugumai paketų tai užtrunka gerokai mažiau nei dvi minutes.

Rezultatų lange rodoma:

- **Pavyko** — sukurtos sąskaitos su serija, numeriu ir nuoroda „Žiūrėti".
- **Nepavyko** — eilutės, kurių sukurti nepavyko, su priežastimi (validacija, plano limitas ir pan.).

Iš čia galite grįžti į valdymo skydelį, paleisti vedlį dar kartą arba pereiti į **Multi-Edit**, kad masiškai išsiųstumėte, išsaugotumėte PDF Google Drive, užrakintumėte ar pažymėtumėte apmokėtas — žr. [Sąskaitų siuntimas ir PDF saugojimas Google Drive](/lt/google-drive-integration).

## Patarimai

- **Svarbi įvykių pavadinimų nuoseklumas** — „Marie Dubois" ir „marie dubois" laikomi skirtingais klientais.
- **Naudokite atskirą atsiskaitymo kalendorių**, kad asmeniniai įvykiai nesimaišytų.
- **Atmeskite įvykius, kurių nereikia išrašyti** — atmesti įvykiai automatiškai praleidžiami.
- **Paleiskite vedlį po vieną kartą kiekvienam paslaugos tipui**, jei skirtingas paslaugas išrašote skirtingais įkainiais (pvz. individualios ir grupinės sesijos).
