---
title: 'Prekės ženklo nustatymai'
date: '2026-05-24'
modified: '2026-05-24'
---

„Haiku.lt" leidžia suasmeninti sąskaitų faktūrų el. laiškus — ir sąskaitų PDF peržiūras — savo logotipu ir spalvų palete. Sukonfigūravus, reikšmės automatiškai pasiekiamos visuose šablonuose, kurie jas palaiko, todėl vienas atnaujinimas pakeičia kiekvieną siunčiamą sąskaitą.

## Logotipas

![Logotipo įkėlimo skiltis prekės ženklo nustatymų puslapyje](/screenshots/brand-customization/lt/step-1-logo.png)

Atidarykite **Nustatymai → Prekės ženklas** ir įkelkite savo įmonės logotipą. Geriausiai tinka PNG arba SVG su skaidriu fonu. Logotipas pasiekiamas el. laiškų šablonuose kaip `{{logoUrl}}`, o **Su logotipu** šablonai jį atvaizduoja laiško viršuje. Logotipą bet kada galite pakeisti arba pašalinti — pakeitimas taikomas vėlesnėms siunčiamoms sąskaitoms.

## Prekės ženklo spalvos

![Prekės ženklo spalvų redaktorius prekės ženklo nustatymų puslapyje](/screenshots/brand-customization/lt/step-2-brand-colors.png)

Po logotipu yra spalvų redaktorius, leidžiantis nustatyti HTML el. laiškų šablonuose naudojamą paletę: pagrindinę ir antraeilę spalvas, teksto ir antraeilę teksto spalvas bei fono spalvas. Keičiant spalvą, tame pačiame puslapyje esanti laiško peržiūra atvaizduojama iš naujo — taip iš karto matote pakeitimo rezultatą prieš išsaugant.

Spalvos pasiekiamos el. laiškų šablonuose kaip `{{brandPrimary}}`, `{{brandSecondary}}`, `{{brandText}}`, `{{brandTextSecondary}}`, `{{brandBackground}}`, `{{bodyBackground}}` ir `{{backgroundSecondary}}` — kaip jas naudoti pasirinktame MJML šablone, skaitykite [El. laiškų šablonai ir kintamieji](/lt/email-templates-and-variables).

## Kada pakeitimai įsigalioja

Prekės ženklo nustatymai nuskaitomi siuntimo metu. Kita siunčiama sąskaita naudos esamas logotipo ir spalvų reikšmes. Jau išsiųstos sąskaitos lieka su tomis reikšmėmis, su kuriomis buvo išsiųstos — pakartotinai siųsti nereikia.

Taip pat žr.: [El. laiškų šablonai ir kintamieji](/lt/email-templates-and-variables).
