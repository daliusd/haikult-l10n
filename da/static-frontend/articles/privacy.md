---
title: 'Privatlivspolitik'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Denne privatlivspolitik beskriver, hvordan Haiku.lt indsamler og bruger data.

## Data vi indsamler

- IP-adresse, dato og tid, browserinformation.

- E-mailadresse.

- Data du indtaster i systemet, mens du bruger det.

## Cookies og browserlager

Vi bruger cookies og browserlager til at levere essentiel funktionalitet:

### Cookies

- **Godkendelsescookie (auth_token)**: En sikker, HTTP-only cookie, der bruges til at
  vedligeholde din login-session. Denne cookie er essentiel for, at tjenesten kan
  fungere og udløber efter cirka 2 måneder. Uden denne cookie kan
  du ikke bruge Haiku.lt.

### Browser lokalt lager

Vi gemmer følgende data i din browsers lokale lager:

- **Sprogpræference**: Dit valgte grænsefladesprog (engelsk eller litauisk)
  for at levere øjeblikkelig UI-rendering.

- **Notifikationsafvisning**: Registrerer, om du har afvist visse
  notifikationer for at undgå at vise dem gentagne gange.

- **Kontoskift-synkronisering**: Midlertidige data (slettet efter 1 sekund), der bruges til at
  synkronisere kontoskift på tværs af flere browserfaner.

### Browser sessionslager

- **Besøgssporing**: Et kun-session flag for at forhindre redirect-loops på
  landingssiden. Disse data slettes, når du lukker din browser.

### Ingen tredjeparts-sporing

Vi bruger ikke nogen analyse-, reklame- eller tredjeparts-sporingscookies.
Alle cookies og lager er strengt nødvendige for, at tjenesten kan fungere.

## Tredjepartstjenester

- **Google-tjenester**: Vi integrerer med Google-tjenester, når du forbinder via Google OAuth:

  - **Google Drive** (valgfrit): Hvis du giver Google Drive-tilladelse, får vi adgang til:
    - **Hvad vi får adgang til**: Filer oprettet af Haiku.lt i din Google Drive. Vi bruger `drive.file`-omfanget, som kun giver adgang til filer oprettet af vores applikation - vi kan ikke se eller få adgang til andre filer i din Drive.
    - **Hvordan vi bruger det**: For at gemme faktura-PDF'er til din Google Drive i en organiseret mappestruktur (Haiku.lt/Invoices/År). Når du bruger "Gem til Drive"-funktionen, opretter eller opdaterer vi PDF-filer.
    - **Hvordan vi gemmer det**: Vi gemmer Google Drive-fil-ID'et i vores database for at spore, hvilke fakturaer der er blevet gemt og for at muliggøre opdateringer af eksisterende filer. Det faktiske PDF-indhold gemmes ikke på vores servere - det eksisterer kun i din Google Drive.
    - **Hvordan vi deler det**: Google Drive-fil-ID'er deles aldrig med tredjeparter, sælges aldrig til datamæglere og bruges aldrig til annoncering, markedsføring, AI-træning eller noget formål andet end at administrere dine faktura-PDF'er i din Drive.
    - **Hvordan du kontrollerer det**: Du kan administrere Drive-tilladelser gennem dine [Google-kontotilladelser](https://myaccount.google.com/permissions). Filer forbliver i din Drive under din kontrol. Du kan slette dem når som helst. Tilbagekaldelse af adgang stopper vores evne til at oprette nye filer eller opdatere eksisterende.

  - **Gmail** (valgfrit): Hvis du giver Gmail-tilladelse, får vi adgang til:
    - **Hvad vi får adgang til**: Tilladelse til at sende e-mails gennem din Gmail-konto. Vi bruger `gmail.send`-omfanget, som tillader afsendelse af e-mails på dine vegne. Vi læser ikke dine eksisterende e-mails eller får adgang til din indbakke.
    - **Hvordan vi bruger det**: For at sende faktura-e-mails til dine købere, når du bruger "Send faktura"-funktionen. E-mails inkluderer faktura-PDF'en som en vedhæftet fil og valgfrie yderligere vedhæftede filer (såsom CII XML til e-fakturering).
    - **Hvordan vi gemmer det**: Vi gemmer ikke e-mailindhold eller sendte meddelelsesdata. Sendte e-mails vises i din Gmail "Sendt"-mappe under din kontrol.
    - **Hvordan vi deler det**: E-mailafsendelseskapacitet deles aldrig med tredjeparter, sælges aldrig og bruges aldrig til annoncering, markedsføring, spam eller noget formål andet end at sende fakturaer, du udtrykkeligt vælger at sende.
    - **Hvordan du kontrollerer det**: Du kan administrere Gmail-tilladelser gennem dine [Google-kontotilladelser](https://myaccount.google.com/permissions). Sendte e-mails forbliver på din Gmail-konto. Tilbagekaldelse af adgang stopper vores evne til at sende e-mails på dine vegne.

  - **Google Calendar** (valgfrit, skrivebeskyttet): Hvis du giver kalendertilladelse, får vi adgang til:
    - **Hvad vi får adgang til**: Dine kalendernavne, begivenhedstitler, begivenhedsdatoer/-tidspunkter og deltagerstatus (for at filtrere afviste begivenheder fra). Vi bruger Google Calendar API-omfanget `calendar.readonly`, som giver skrivebeskyttet adgang.
    - **Hvordan vi bruger det**: Udelukkende for at hjælpe dig med at oprette fakturaer baseret på kalenderbegivenheder gennem "Opret fra kalender"-funktionen. Begivenhedstitler bliver fakturalinjebeskrivelser, og begivenhedsdatoer hjælper med at indstille fakturadatointervaller.
    - **Hvordan vi gemmer det**: Kalenderdata **gemmes ikke permanent** i vores databaser. Det hentes on-demand kun når du bruger kalenderfakturafunktionen og eksisterer midlertidigt i din browserhukommelse under fakturaoprettelsesprocessen.
    - **Hvordan vi deler det**: Kalenderdata **deles aldrig** med tredjeparter, **sælges aldrig** til datamæglere og **bruges aldrig** til annoncering, markedsføring, AI-træning eller noget formål andet end at oprette fakturaer for dig.
    - **Hvordan du kontrollerer det**: Du kan administrere kalendertilladelser uafhængigt gennem dine [Google-kontotilladelser](https://myaccount.google.com/permissions). Tilbagekaldelse af adgang stopper dataadgang øjeblikkeligt. Du kan også afbryde hele din Google-konto gennem Haiku.lt-indstillinger.

  Alle Google OAuth-tilladelser kræver din udtrykkelige autorisation. Du kontrollerer, hvilke tilladelser du giver, og kan tilbagekalde dem når som helst.

- **Stripe**: Vi bruger Stripe til betalingsbehandling af premium-abonnementer.
  Stripe håndterer al betalingsinformation sikkert i overensstemmelse med deres privatlivspolitik.
  Vi modtager kun bekræftelse på vellykkede betalinger.

- **Brevo (Sendinblue)**: Vi bruger Brevo til at levere transaktionelle e-mails, herunder magisk link-login e-mails og faktura-e-mails. Brevo modtager modtagerens e-mailadresse og e-mailindhold nødvendigt for at levere disse beskeder. Brevo er placeret i EU (Frankrig). Se deres [Privatlivspolitik](https://www.brevo.com/legal/privacypolicy/).

## Databeskyttelse

For at beskytte indsamlede data træffer vi følgende foranstaltninger:

- Opdater serversoftware så ofte som muligt.

- Opdater Haiku.lt-software så ofte som muligt.

- Korrekt konfigurer servere.

## Dine rettigheder

For detaljeret information om dine datarettigheder i henhold til GDPR, herunder retten
til at få adgang til, slette og eksportere dine data, se venligst vores [GDPR-side](/da/gdpr).
