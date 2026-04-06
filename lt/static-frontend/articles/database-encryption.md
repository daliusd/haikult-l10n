---
title: 'Jūsų duomenys yra užšifruoti: Kodėl tai svarbu'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Kiekviena Haiku.lt naudotojų duomenų bazė yra šifruojama. Štai ką tai iš tikrųjų reiškia ir kodėl jums tai turėtų rūpėti.

## Ką reiškia šifravimas (paprastai)

Įsivaizduokite savo sąskaitas faktūras ir klientų duomenis kaip dienoraštį. Šifravimas užrakina šį dienoraštį ir kiekvieną žodį paverčia atsitiktine abrakadabra. Be rakto žmogus, turintis dienoraštį, mato tik triukšmą — `X7k#mQ2$pL9@vR4...` — visiškai neįskaitomą.

Kiekvieno naudotojo duomenų bazė gauna unikalų raktą, ir Haiku.lt niekada nesaugo šio rakto atviru tekstu.

## Atsarginės kopijos scenarijus

Haiku.lt reguliariai daro atsargines kopijas, kad apsisaugotų nuo duomenų praradimo. Dabar įsivaizduokite blogiausią scenarijų: įsilaužėlis kažkokiu būdu gauna vieną iš tų atsarginių kopijų failų.

Ką jie turi? Failą, pilną užšifruotų beprasmybių. Be šifravimo rakto atsarginė kopija jiems yra bevertė. Jie negali perskaityti jūsų klientų vardų, sąskaitų faktūrų sumų ar kitų duomenų.

## Kaip stipriai užšifruota?

Haiku.lt naudoja AES-256 šifravimą — tą patį standartą, kurį naudoja bankai ir vyriausybės visame pasaulyje. Norėdamas nulaužti AES-256 raktą, užpuolikas turėtų išbandyti 2²⁵⁶ galimų kombinacijų.

Perspektyva: net ir naudojant visus Žemėje veikiančius kompiuterius visu pajėgumu, vieno AES-256 rakto nulaužimas užtruktų ilgiau nei dabartinis visatos amžius. Tai nepraktiška ataka.

## Apibendrinimas

Jei Haiku.lt atsarginės kopijos kada nors būtų pavogtos, jūsų duomenys liktų apsaugoti. Šifravimas užtikrina, kad fizinis atsarginės kopijos failo turėjimas be šifravimo rakto būtų beprasmis.

Jūsų sąskaitos faktūros yra jūsų verslas. Jos turėtų likti jūsų.
