---
title: 'AVG - Uw Gegevensrechten'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt zet zich in voor het beschermen van uw persoonlijke gegevens en het respecteren van uw privacyrechten onder de Algemene Verordening Gegevensbescherming (AVG). Deze pagina legt uw rechten uit en hoe wij met uw gegevens omgaan.

## Uw Gegevensrechten

Onder de AVG heeft u de volgende rechten met betrekking tot uw persoonlijke gegevens:

### Recht op Toegang

U heeft het recht om toegang te krijgen tot alle persoonlijke gegevens die wij over u bewaren. U kunt uw gegevens op elk moment exporteren:

- **Volledige database-export**: Download uw complete database inclusief alle facturen, instellingen en auditlogboeken vanuit uw accountinstellingen.
- **Factuur-export**: Exporteer uw facturen in CSV-formaat, gefilterd op datumbereik en serienaam.

### Recht op Verwijdering (Recht om Vergeten te Worden)

U heeft het recht om verwijdering van uw persoonlijke gegevens te verzoeken. U kunt uw volledige account en alle bijbehorende gegevens op elk moment verwijderen via uw accountinstellingen. Deze actie is permanent en kan niet ongedaan worden gemaakt.

### Recht op Gegevensportabiliteit

U kunt uw gegevens exporteren in machine-leesbare formaten:

- SQLite database formaat (volledige gegevens-export)
- CSV-formaat (factuurgegevens export)

Hierdoor kunt u uw gegevens naar een andere dienst overbrengen indien u dat wenst.

### Recht op Rectificatie

U heeft het recht om onjuiste of onvolledige persoonlijke gegevens te corrigeren. U kunt al uw gegevens rechtstreeks in de applicatie bewerken, inclusief:

- Factuurdetails
- Koper- en verkoperinformatie
- Uw persoonlijke voorkeuren en instellingen

### Recht op Beperking van Verwerking

U heeft het recht om in bepaalde omstandigheden beperking van de verwerking van uw persoonlijke gegevens te verzoeken. Neem contact met ons op via onderstaand e-mailadres om dit recht uit te oefenen.

### Recht van Bezwaar

U heeft het recht om bezwaar te maken tegen de verwerking van uw persoonlijke gegevens voor specifieke doeleinden. Omdat Haiku.lt uw gegevens alleen verwerkt om de door u gevraagde facturatiedienst te leveren, zou bezwaar maken tegen de verwerking betekenen dat wij de dienst niet kunnen leveren.

## Gegevensbewaring

Uw gegevens worden bewaard **totdat u uw account verwijdert**. Wij verwijderen niet automatisch inactieve accounts. U heeft volledige controle over wanneer uw gegevens worden verwijderd.

Wanneer u uw account verwijdert, worden al uw gegevens permanent uit onze systemen verwijderd.

## Verwerkingsverantwoordelijke

De verwerkingsverantwoordelijke voor Haiku.lt is:

**Dalius Dobravolskas**

Voor privacy-gerelateerde vragen of om uw gegevensrechten uit te oefenen, neem contact op met:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Serverlocatie

Alle Haiku.lt servers en gegevensopslag bevinden zich in de **Europese Unie, specifiek in Duitsland**. Uw gegevens verlaten de EU niet, tenzij u expliciet toestemming geeft voor integraties met derden (zie Subverwerkers hieronder).

## Rechtsgrondslag voor Verwerking

Wij verwerken uw persoonlijke gegevens op basis van:

- **Contractuitvoering**: Om de facturatiedienst te leveren waarvoor u zich heeft aangemeld
- **Gerechtvaardigd belang**: Om de beveiliging van de dienst te handhaven, fraude te voorkomen en de dienst te verbeteren
- **Toestemming**: Voor optionele functies zoals Google Drive en Gmail-integratie

## Subverwerkers

Haiku.lt maakt gebruik van de volgende diensten van derden om onze functionaliteit te bieden:

### Google LLC

**Gebruikte diensten**: OAuth 2.0 Authenticatie, Google Drive API, Gmail API, Google Agenda API

**Gedeelde gegevens**: E-mailadres, naam, OAuth-tokens (alleen wanneer u Google-integratie autoriseert)

**Doel**: Om u in staat te stellen om:
- **Authenticeren** met uw Google-account via OAuth 2.0
- **Google Drive** (scope: `drive.file`): Factuur-PDF's opslaan in uw Drive in georganiseerde mappen (Haiku.lt/Invoices/Year). Wij hebben alleen toegang tot bestanden die door onze applicatie zijn gemaakt, niet tot uw andere Drive-bestanden. Wij bewaren Drive-bestands-ID's om opgeslagen facturen bij te houden.
- **Gmail** (scope: `gmail.send`): Factuuremails namens u verzenden naar kopers. Wij lezen uw inbox of bestaande emails niet. Verzonden emails verschijnen in uw Gmail "Verzonden" map.
- **Google Agenda** (scope: `calendar.readonly`, optioneel): Agenda-evenement titels, data, tijden en aanwezigheidsstatus lezen om facturen aan te maken. Deze gegevens worden tijdelijk opgehaald en niet permanent opgeslagen.

**Gegevensbewaring**:
- Drive-bestands-ID's: Opgeslagen in onze database totdat u de factuur verwijdert of uw Google-account loskoppelt
- Agendagegevens: Niet opgeslagen (alleen on-demand opgehaald)
- Gmail-gegevens: Niet opgeslagen (emails blijven in uw Gmail-account)
- OAuth-tokens: Versleuteld en opgeslagen totdat u uw account loskoppelt

**Privacybeleid**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Locatie**: Verenigde Staten (met naleving van EU-VS Data Privacy Framework)

### Stripe, Inc.

**Gebruikte diensten**: Betalingsverwerking voor abonnementen

**Gedeelde gegevens**: E-mailadres, betalingsinformatie (rechtstreeks verwerkt door Stripe)

**Doel**: Om abonnementsbetalingen voor premium functies te verwerken

**Privacybeleid**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Locatie**: Verenigde Staten (met naleving van EU-VS Data Privacy Framework)

### Brevo (Sendinblue)

**Gebruikte diensten**: Bezorging van transactionele e-mails

**Gedeelde gegevens**: E-mailadres van de ontvanger, e-mailinhoud (magische link-tokens voor inloggen; factuurgegevens bij het verzenden van facturen via Brevo)

**Doel**: Om authenticatie-e-mails (magische link-inloggen) en factuur-e-mails aan kopers te bezorgen

**Gegevensbewaring**: Brevo kan verzonden e-maillogboeken voor een beperkte periode bewaren volgens hun beleid. Wij slaan e-mailinhoud niet langer op onze servers op dan nodig is om het te verzenden.

**Privacybeleid**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Locatie**: Europese Unie (Frankrijk)

## Gegevensbeveiliging

Wij nemen passende technische en organisatorische maatregelen om uw persoonlijke gegevens te beschermen:

- Versleuteling van gevoelige gegevens (OAuth-tokens, refresh tokens)
- Beveiligde HTTPS-verbindingen
- HTTP-only, beveiligde authenticatiecookies
- Regelmatige software-updates
- Isolatie van databases per gebruiker
- Auditlogboeken voor het bijhouden van accounttoegang

## Melding van Datalekken

In het onwaarschijnlijke geval van een datalek dat een risico vormt voor uw rechten en vrijheden, zullen wij u en de relevante toezichthoudende autoriteit binnen 72 uur op de hoogte stellen zoals vereist door de AVG.

## Toezichthoudende Autoriteit

Als u zorgen heeft over hoe wij uw persoonlijke gegevens verwerken, heeft u het recht om een klacht in te dienen bij uw lokale toezichthoudende autoriteit voor gegevensbescherming.

Voor gebruikers in Nederland is de toezichthoudende autoriteit:

**Autoriteit Persoonsgegevens**
Website: [https://autoriteitpersoonsgegevens.nl](https://autoriteitpersoonsgegevens.nl)

## Updates van dit Beleid

Wij kunnen deze AVG-informatiepagina van tijd tot tijd bijwerken. De "gewijzigd" datum bovenaan deze pagina geeft aan wanneer deze voor het laatst is bijgewerkt.

Voor algemene privacy-informatie, zie ons [Privacybeleid](/nl/privacy).
