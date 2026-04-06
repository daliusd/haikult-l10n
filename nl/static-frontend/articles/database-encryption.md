---
title: 'Uw gegevens zijn versleuteld: Waarom het belangrijk is'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Elke Haiku.lt-gebruikersdatabase is in rust versleuteld. Hier lees je wat dat eigenlijk betekent en waarom je er iets om zou geven.

## Wat encryptie betekent (eenvoudig)

Stel je facturen en klantgegevens voor als een dagboek. Encryptie vergrendelt dat dagboek en vervormt elk woord in willekeurige wartaal. Zonder de sleutel ziet iemand die het dagboek vasthoudt niets anders dan ruis — `X7k#mQ2$pL9@vR4...` — volledig onleesbaar.

De database van elke gebruiker krijgt een unieke sleutel en Haiku.lt slaat die sleutel nooit op in platte tekst.

## Het back-upscenario

Haiku.lt maakt regelmatig back-ups om gegevensverlies te voorkomen. Stel je nu een worst-case scenario voor: een hacker krijgt op de een of andere manier een van die back-upbestanden in handen.

Wat hebben ze dan? Een bestand vol vervormd gebrabbel. Zonder de encryptiesleutel is de back-up waardeloos voor hen. Ze kunnen de namen van je klanten, factuurbedragen of andere gegevens niet lezen.

## Hoe sterk is «versleuteld»?

Haiku.lt gebruikt AES-256-encryptie — dezelfde standaard die wereldwijd door banken en overheden wordt gebruikt. Om een AES-256-sleutel te brute-forcen, zou een aanvaller 2²⁵⁶ mogelijke combinaties moeten proberen.

Ter vergelijking: zelfs als elke computer op aarde op volle snelheid draait, zou het kraken van een enkele AES-256-sleutel langer duren dan de huidige leeftijd van het universum. Het is geen praktische aanval.

## De conclusie

Als de back-ups van Haiku.lt ooit gestolen zouden worden, zouden je gegevens beschermd blijven. De versleuteling zorgt ervoor dat fysiek bezit van een back-upbestand zinloos is zonder de versleutelingssleutel.

Uw facturen zijn uw zaken. Ze moeten van u blijven.
