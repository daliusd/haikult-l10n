---
title: 'Dine data er krypterede: Hvorfor det er vigtigt'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Hver Haiku.lt-brugerdatabase er krypteret i hvile. Her er, hvad det faktisk betyder, og hvorfor du bør bekymre dig om det.

## Hvad kryptering betyder (ganske enkelt)

Forestil dig dine fakturaer og kundedata som en dagbog. Kryptering låser dagbogen og forvrænger hvert ord til tilfældigt volapyk. Uden nøglen ser en person, der holder dagbogen, ikke andet end støj — `X7k#mQ2$pL9@vR4...` — helt ulæseligt.

Hver brugers database får en unik nøgle, og Haiku.lt gemmer aldrig denne nøgle i almindelig tekst.

## Backup-scenariet

Haiku.lt laver regelmæssige sikkerhedskopier for at beskytte mod datatab. Forestil dig nu det værst tænkelige scenarie: En hacker får på en eller anden måde fat i en af disse backup-filer.

Hvad har de så? En fil fuld af krypteret volapyk. Uden krypteringsnøglen er sikkerhedskopien værdiløs for dem. De kan ikke læse dine kundenavne, fakturabeløb eller andre data.

## Hvor stærk er "krypteret"?

Haiku.lt bruger AES-256-kryptering — den samme standard, som bruges af banker og regeringer verden over. For at bryde en AES-256-nøgle skal en angriber prøve 2²⁵⁶ mulige kombinationer.

For at sætte det i perspektiv: Selv hvis alle computere på jorden kørte med fuld hastighed, ville det tage længere tid at knække en enkelt AES-256-nøgle end universets nuværende alder. Det er ikke et praktisk angreb.

## Den korteste konklusion

Hvis Haiku.lt's sikkerhedskopier nogensinde blev stjålet, ville dine data forblive beskyttet. Krypteringen sikrer, at fysisk besiddelse af en backup-fil er meningsløs uden krypteringsnøglen.

Dine fakturaer er din forretning. De bør forblive dine.
