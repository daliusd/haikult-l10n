---
title: 'GDPR - Dina datarättigheter'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt är engagerad i att skydda dina personuppgifter och respektera dina integritetsrättigheter enligt den allmänna dataskyddsförordningen (GDPR). Denna sida förklarar dina rättigheter och hur vi hanterar dina data.

## Dina datarättigheter

Enligt GDPR har du följande rättigheter gällande dina personuppgifter:

### Rätt till tillgång

Du har rätt att få tillgång till alla personuppgifter vi har om dig. Du kan exportera dina data när som helst:

- **Fullständig databasexport**: Ladda ner din kompletta databas inklusive alla fakturor, inställningar och revisionsloggar från dina kontoinställningar.
- **Fakturaexport**: Exportera dina fakturor som CSV-format, filtrerat efter datumintervall och serienamn.

### Rätt till radering (Rätt att bli glömd)

Du har rätt att begära radering av dina personuppgifter. Du kan radera hela ditt konto och alla associerade data när som helst genom dina kontoinställningar. Denna åtgärd är permanent och kan inte ångras.

### Rätt till dataportabilitet

Du kan exportera dina data i maskinläsbara format:

- SQLite-databasformat (fullständig dataexport)
- CSV-format (fakturdataexport)

Detta gör att du kan överföra dina data till en annan tjänst om du väljer.

### Rätt till rättelse

Du har rätt att korrigera felaktiga eller ofullständiga personuppgifter. Du kan redigera alla dina data direkt i applikationen, inklusive:

- Fakturadetaljer
- Köpar- och säljarinformation
- Dina personliga preferenser och inställningar

### Rätt till begränsning av behandling

Du har rätt att begära begränsning av behandlingen av dina personuppgifter under vissa omständigheter. Kontakta oss via e-postadressen nedan för att utöva denna rättighet.

### Rätt att göra invändningar

Du har rätt att invända mot behandlingen av dina personuppgifter för specifika ändamål. Eftersom Haiku.lt endast behandlar dina data för att tillhandahålla den faktureringstjänst du begärt, skulle invändning mot behandling hindra oss från att tillhandahålla tjänsten.

## Datalagring

Dina data sparas **tills du raderar ditt konto**. Vi raderar inte automatiskt inaktiva konton. Du har full kontroll över när dina data tas bort.

När du raderar ditt konto tas alla dina data permanent bort från våra system.

## Personuppgiftsansvarig

Personuppgiftsansvarig för Haiku.lt är:

**Dalius Dobravolskas**

För integritetsrelaterade frågor eller för att utöva dina datarättigheter, kontakta:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Serverplats

Alla Haiku.lt-servrar och datalagring finns i **Europeiska unionen, specifikt i Tyskland**. Dina data lämnar inte EU såvida du inte uttryckligen auktoriserar tredjepartsintegrationer (se Personuppgiftsbiträden nedan).

## Rättslig grund för behandling

Vi behandlar dina personuppgifter baserat på:

- **Fullgörande av avtal**: För att tillhandahålla den faktureringstjänst du registrerade dig för
- **Berättigat intresse**: För att upprätthålla tjänstesäkerhet, förhindra bedrägerier och förbättra tjänsten
- **Samtycke**: För valfria funktioner som Google Drive- och Gmail-integration

## Personuppgiftsbiträden

Haiku.lt använder följande tredjepartstjänster för att tillhandahålla vår funktionalitet:

### Google LLC

**Tjänster som används**: OAuth 2.0-autentisering, Google Drive API, Gmail API, Google Calendar API

**Data som delas**: E-postadress, namn, OAuth-tokens (endast när du auktoriserar Google-integration)

**Syfte**: För att möjliggöra för dig att:
- **Autentisera** med ditt Google-konto med OAuth 2.0
- **Google Drive** (omfattning: `drive.file`): Spara faktura-PDF:er till din Drive i organiserade mappar (Haiku.lt/Fakturor/År). Vi kan endast få åtkomst till filer skapade av vår applikation, inte dina andra Drive-filer. Vi lagrar Drive-fil-ID:n för att spåra sparade fakturor.
- **Gmail** (omfattning: `gmail.send`): Skicka faktura-e-postmeddelanden till köpare å dina vägnar. Vi läser inte din inkorg eller befintliga e-postmeddelanden. Skickade e-postmeddelanden visas i din Gmail-mapp "Skickat".
- **Google Calendar** (omfattning: `calendar.readonly`, valfritt): Läs kalenderhändelsers titlar, datum, tider och deltagandestatus för att hjälpa till att skapa fakturor. Denna data hämtas tillfälligt och lagras inte permanent.

**Datalagring**:
- Drive-fil-ID:n: Lagras i vår databas tills du raderar fakturan eller kopplar från ditt Google-konto
- Kalenderdata: Lagras inte (hämtas endast på begäran)
- Gmail-data: Lagras inte (e-postmeddelanden förblir i ditt Gmail-konto)
- OAuth-tokens: Krypteras och lagras tills du kopplar från ditt konto

**Integritetspolicy**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Plats**: USA (med EU-US Data Privacy Framework-efterlevnad)

### Stripe, Inc.

**Tjänster som används**: Betalningshantering för abonnemang

**Data som delas**: E-postadress, betalningsinformation (hanteras direkt av Stripe)

**Syfte**: För att behandla abonnemangsbetalningar för premiumfunktioner

**Integritetspolicy**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Plats**: USA (med EU-US Data Privacy Framework-efterlevnad)

### Brevo (Sendinblue)

**Tjänster som används**: Leverans av transaktionella e-postmeddelanden

**Data som delas**: Mottagarens e-postadress, e-postinnehåll (tokens för magisk länk-inloggning; fakturauppgifter vid sändning av fakturor via Brevo)

**Syfte**: För att leverera autentiseringsmeddelanden (inloggning med magisk länk) och fakturameddelanden till köpare

**Datalagring**: Brevo kan behålla loggar över skickade e-postmeddelanden under en begränsad period enligt deras policy. Vi lagrar inte e-postinnehåll på våra servrar utöver vad som behövs för att skicka det.

**Integritetspolicy**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Plats**: Europeiska unionen (Frankrike)

## Datasäkerhet

Vi vidtar lämpliga tekniska och organisatoriska åtgärder för att skydda dina personuppgifter:

- Kryptering av känsliga data (OAuth-tokens, uppdateringstokens)
- Säkra HTTPS-anslutningar
- HTTP-only, säkra autentiseringscookies
- Regelbundna programvaruuppdateringar
- Per-användare databasisolering
- Revisionsloggning för kontots åtkomstspårning

## Anmälan om dataintrång

I det osannolika fallet av ett dataintrång som utgör en risk för dina rättigheter och friheter kommer vi att meddela dig och relevant tillsynsmyndighet inom 72 timmar enligt GDPR-krav.

## Tillsynsmyndighet

Om du har farhågor om hur vi hanterar dina personuppgifter har du rätt att lämna in ett klagomål till din lokala tillsynsmyndighet för dataskydd.

För användare i Litauen är tillsynsmyndigheten:

**State Data Protection Inspectorate**
Webbplats: [https://vdai.lrv.lt](https://vdai.lrv.lt)

## Uppdateringar av denna policy

Vi kan uppdatera denna GDPR-informationssida från tid till annan. Datumet "modified" överst på denna sida indikerar när den senast uppdaterades.

För allmän integritetsinformation, se vår [Integritetspolicy](/sv/privacy).
