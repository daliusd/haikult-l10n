---
title: 'Integritetspolicy'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Denna integritetspolicy beskriver hur Haiku.lt samlar in och använder data.

## Data vi samlar in

- IP-adress, datum och tid, webbläsarinformation.

- E-postadress.

- Data du anger i systemet medan du använder det.

## Cookies och webbläsarlagring

Vi använder cookies och webbläsarlagring för att tillhandahålla väsentlig funktionalitet:

### Cookies

- **Autentiseringscookie (auth_token)**: En säker, HTTP-only-cookie som används för att
  upprätthålla din inloggningssession. Denna cookie är nödvändig för att tjänsten ska
  fungera och upphör efter cirka 2 månader. Utan denna cookie
  kan du inte använda Haiku.lt.

### Webbläsarens lokala lagring

Vi lagrar följande data i din webbläsares lokala lagring:

- **Språkpreferens**: Ditt valda gränssnittsspråk (engelska eller litauiska)
  för att tillhandahålla omedelbar UI-rendering.

- **Notifieringsavstängning**: Registrerar om du har stängt av vissa
  notifieringar för att undvika att visa dem upprepade gånger.

- **Kontoväxlingssynkronisering**: Tillfälliga data (raderas efter 1 sekund) som används för att
  synkronisera kontoväxling mellan flera webbläsarflikar.

### Webbläsarens sessionslagring

- **Besöksspårning**: En sessions-only-flagga för att förhindra oändliga omdirigeringsslöjfor på
  landningssidan. Denna data raderas när du stänger din webbläsare.

### Ingen tredjepartsspårning

Vi använder inte några analys-, annonserings- eller tredjepartsspårningscookies.
Alla cookies och lagring är strikt nödvändiga för att tjänsten ska fungera.

## Tredjepartstjänster

- **Google-tjänster**: Vi integrerar med Google-tjänster när du ansluter via Google OAuth:

  - **Google Drive** (valfritt): Om du ger Google Drive-behörighet får vi åtkomst till:
    - **Vad vi får åtkomst till**: Filer skapade av Haiku.lt i din Google Drive. Vi använder `drive.file`-omfattningen som ger åtkomst endast till filer skapade av vår applikation - vi kan inte se eller få åtkomst till några andra filer i din Drive.
    - **Hur vi använder det**: För att spara faktura-PDF:er till din Google Drive i en organiserad mappstruktur (Haiku.lt/Fakturor/År). När du använder funktionen "Spara till Drive" skapar eller uppdaterar vi PDF-filer.
    - **Hur vi lagrar det**: Vi lagrar Google Drive-fil-ID:t i vår databas för att spåra vilka fakturor som har sparats och för att möjliggöra uppdateringar av befintliga filer. Det faktiska PDF-innehållet lagras inte på våra servrar - det finns endast i din Google Drive.
    - **Hur vi delar det**: Google Drive-fil-ID:n delas aldrig med tredje part, säljs aldrig till datamäklare och används aldrig för annonsering, marknadsföring, AI-träning eller något annat syfte än att hantera dina faktura-PDF:er i din Drive.
    - **Hur du kontrollerar det**: Du kan hantera Drive-behörigheter genom dina [Google-kontobehörigheter](https://myaccount.google.com/permissions). Filer förblir i din Drive under din kontroll. Du kan radera dem när som helst. Återkallande av åtkomst stoppar vår förmåga att skapa nya filer eller uppdatera befintliga.

  - **Gmail** (valfritt): Om du ger Gmail-behörighet får vi åtkomst till:
    - **Vad vi får åtkomst till**: Behörighet att skicka e-post genom ditt Gmail-konto. Vi använder `gmail.send`-omfattningen som tillåter sändning av e-post å dina vägnar. Vi läser inte dina befintliga e-postmeddelanden eller får åtkomst till din inkorg.
    - **Hur vi använder det**: För att skicka faktura-e-postmeddelanden till dina köpare när du använder funktionen "Skicka faktura". E-postmeddelanden inkluderar faktura-PDF:en som bilaga och valfria ytterligare bilagor (som CII XML för e-fakturering).
    - **Hur vi lagrar det**: Vi lagrar inte e-postinnehåll eller skickade meddelandedata. Skickade e-postmeddelanden visas i din Gmail-mapp "Skickat" under din kontroll.
    - **Hur vi delar det**: E-postsändningsförmåga delas aldrig med tredje part, säljs aldrig och används aldrig för annonsering, marknadsföring, spam eller något annat syfte än att skicka fakturor du uttryckligen väljer att skicka.
    - **Hur du kontrollerar det**: Du kan hantera Gmail-behörigheter genom dina [Google-kontobehörigheter](https://myaccount.google.com/permissions). Skickade e-postmeddelanden förblir i ditt Gmail-konto. Återkallande av åtkomst stoppar vår förmåga att skicka e-post å dina vägnar.

  - **Google Calendar** (valfritt, skrivskyddad): Om du ger kalenderbehörighet får vi åtkomst till:
    - **Vad vi får åtkomst till**: Dina kalendernamn, händelsetitlar, händelsedatum/-tider och deltagandestatus (för att filtrera bort avböjda händelser). Vi använder Google Calendar API-omfattningen `calendar.readonly` som ger skrivskyddad åtkomst.
    - **Hur vi använder det**: Uteslutande för att hjälpa dig skapa fakturor baserat på kalenderhändelser genom funktionen "Skapa från kalender". Händelsetitlar blir fakturaradspositionsbeskrivningar, och händelsedatum hjälper till att ställa in fakturadatumintervall.
    - **Hur vi lagrar det**: Kalenderdata lagras **inte permanent** i våra databaser. Det hämtas på begäran endast när du använder kalenderfakturafunktionen och finns tillfälligt i din webbläsares minne under fakturaskapandeprocessen.
    - **Hur vi delar det**: Kalenderdata delas **aldrig** med tredje part, **säljs aldrig** till datamäklare och **används aldrig** för annonsering, marknadsföring, AI-träning eller något annat syfte än att skapa fakturor för dig.
    - **Hur du kontrollerar det**: Du kan hantera kalenderbehörigheter självständigt genom dina [Google-kontobehörigheter](https://myaccount.google.com/permissions). Återkallande av åtkomst stoppar dataåtkomst omedelbart. Du kan också koppla från hela ditt Google-konto genom Haiku.lt-inställningar.

  Alla Google OAuth-behörigheter kräver ditt uttryckliga godkännande. Du kontrollerar vilka behörigheter som ska ges och kan återkalla dem när som helst.

- **Stripe**: Vi använder Stripe för betalningshantering av premiumabonnemang.
  Stripe hanterar all betalningsinformation säkert enligt deras integritetspolicy. Vi får endast bekräftelse på lyckade betalningar.

- **Brevo (Sendinblue)**: Vi använder Brevo för att leverera transaktionella e-postmeddelanden, inklusive e-postmeddelanden för inloggning med magisk länk och fakturameddelanden. Brevo tar emot mottagarens e-postadress och e-postinnehåll som behövs för att leverera dessa meddelanden. Brevo finns i EU (Frankrike). Se deras [Integritetspolicy](https://www.brevo.com/legal/privacypolicy/).

## Dataskydd

För att skydda insamlade data vidtar vi följande åtgärder:

- Uppdatera serverprogramvara så ofta som möjligt.

- Uppdatera Haiku.lt-programvara så ofta som möjligt.

- Konfigurera servrar på rätt sätt.

## Dina rättigheter

För detaljerad information om dina datarättigheter enligt GDPR, inklusive rätten
att få åtkomst till, radera och exportera dina data, se vår [GDPR-sida](/sv/gdpr).
