---
title: 'Dine data er kryptert: Hvorfor det er viktig'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Alle Haiku.lt-brukerdatabaser er kryptert i hvile. Her er hva det faktisk betyr, og hvorfor du bør bry deg om det.

## Hva kryptering betyr (enkelt)

Se for deg fakturaer og kundedata som en dagbok. Kryptering låser dagboken og forvrenger hvert eneste ord til tilfeldig kaudervelsk. Uten nøkkelen vil den som holder dagboken, ikke se annet enn støy — `X7k#mQ2$pL9@vR4...` — helt uleselig.

Hver brukers database får en unik nøkkel, og Haiku.lt lagrer aldri denne nøkkelen i klartekst.

## Sikkerhetskopieringsscenarioet

Haiku.lt tar regelmessige sikkerhetskopier for å beskytte mot tap av data. Forestill deg det verste scenarioet: En hacker får på en eller annen måte tak i en av disse sikkerhetskopifilene.

Hva har de da? En fil full av kryptert volapyk. Uten krypteringsnøkkelen er sikkerhetskopien verdiløs for dem. De kan ikke lese kundenavn, fakturabeløp eller andre data.

## Hvor sterk er «kryptert»?

Haiku.lt bruker AES-256-kryptering — den samme standarden som brukes av banker og myndigheter over hele verden. For å bryte seg inn i en AES-256-nøkkel må en angriper prøve 2²⁵⁶ mulige kombinasjoner.

For å sette det i perspektiv: Selv om alle datamaskiner på jorden kjørte for fullt, ville det å knekke en enkelt AES-256-nøkkel ta lengre tid enn universets nåværende alder. Det er ikke et praktisk angrep.

## Oppsummering

Hvis Haiku.lt's sikkerhetskopier noen gang skulle bli stjålet, vil dataene dine forbli beskyttet. Krypteringen sikrer at fysisk besittelse av en sikkerhetskopifil er meningsløs uten krypteringsnøkkelen.

Fakturaene dine er din virksomhet. De bør forbli dine.
