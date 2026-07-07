---
title: 'El. pašto nustatymai: Gmail (OAuth)'
date: '2026-05-23'
modified: '2026-05-23'
---

Jei prisijungiate prie „Haiku.lt“ per Google paskyrą, sąskaitas faktūras galite siųsti tiesiogiai iš savo Gmail adreso naudodami OAuth. Klientai pašto dėžutėje mato įprastą jūsų adresą, atsakymai grįžta į tą patį Gmail susirašinėjimą, o Gmail autentifikacija (SPF, DKIM, DMARC) veikia teisingai, nes laiškas tikrai siunčiamas iš jūsų paskyros. „Haiku.lt“ niekada negauna jūsų slaptažodžio, o leidimą galite bet kada atšaukti.

## Ką OAuth reiškia jums

OAuth – tai šiuolaikinis ir saugus būdas vienai programai veikti kitos vardu. Užuot atidavę „Haiku.lt“ savo Gmail slaptažodį, suteikiate vieną aiškiai apibrėžtą leidimą – *siųsti laiškus jūsų vardu* – per pačios Google sutikimo langą. „Haiku.lt“ slaptažodžio nemato, o leidimą galima panaikinti bet kuriuo metu.

## Suteikite Gmail prieigą

Prisijungdami prie „Haiku.lt“ per Google, pamatysite leidimų sąrašą, kurio „Haiku.lt“ prašo. Tarp jų yra leidimas siųsti laiškus jūsų vardu. Paspauskite **Leisti**, kad jį suteiktumėte. Tai vienkartinis veiksmas – kartą leidus, „Haiku.lt“ galės siųsti sąskaitas faktūras iš jūsų Gmail paskyros, kai tik paspausite **Siųsti sąskaitą faktūrą**.

## Jei nesuteikėte leidimo

Jei prisijungėte, bet praleidote arba atmetėte el. laiškų siuntimo leidimą, „Haiku.lt“ negalės siųsti per Gmail. Sprendimas paprastas: **atsijunkite ir prisijunkite iš naujo** per Google. Sutikimo lange įsitikinkite, kad leidimas siųsti laiškus liktų pažymėtas, ir paspauskite **Leisti**.

## Prieigos atšaukimas

Jūs visada kontroliuojate leidimą. Norėdami panaikinti „Haiku.lt“ galimybę siųsti iš jūsų Gmail paskyros, atidarykite [Google paskyros saugos nustatymus](https://myaccount.google.com/permissions), suraskite „Haiku.lt“ susietų programų sąraše ir paspauskite **Pašalinti prieigą**. Vėliau galite prisijungti iš naujo ir leidimą suteikti dar kartą.

## Kada rinktis SMTP

Gmail OAuth – paprasčiausias ir saugiausias variantas Google paskyrų naudotojams. Jei Gmail nenaudojate arba pageidaujate siųsti per kitą tiekėją (Outlook, savo domeno pašto serverį, SendGrid, Mailgun ir pan.), rinkitės SMTP. Žr. [El. pašto nustatymai: SMTP](/lt/email-setup-smtp), kur aprašyti visi konfigūravimo žingsniai.
