---
title: 'Personvernerklæring'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Denne personvernerklæringen beskriver hvordan Haiku.lt samler inn og bruker data.

## Data vi samler inn

- IP-adresse, dato og tid, nettleserinformasjon.

- E-postadresse.

- Data du legger inn i systemet mens du bruker det.

## Informasjonskapsler og nettleserlagring

Vi bruker informasjonskapsler og nettleserlagring for å tilby essensiell funksjonalitet:

### Informasjonskapsler

- **Autentiseringsinformasjonskapsel (auth_token)**: En sikker, HTTP-only informasjonskapsel brukt til
  å opprettholde påloggingsøkten din. Denne informasjonskapselen er essensiell for at tjenesten skal
  fungere og utløper etter omtrent 2 måneder. Uten denne informasjonskapselen kan du ikke bruke Haiku.lt.

### Nettleserens lokal lagring

Vi lagrer følgende data i nettleserens lokale lagring:

- **Språkpreferanse**: Ditt valgte grensesnittspråk (engelsk eller litauisk)
  for å gi umiddelbar UI-rendering.

- **Varselbekreftelse**: Registrerer om du har avvist visse
  varsler for å unngå å vise dem gjentatte ganger.

- **Kontobytte-synkronisering**: Midlertidige data (slettet etter 1 sekund) brukt til
  å synkronisere kontobytte på tvers av flere nettleserfaner.

### Nettleserens øktlagring

- **Besøkssporing**: Et kun-øktflagg for å forhindre omdirigering på
  landingssiden. Disse dataene slettes når du lukker nettleseren.

### Ingen tredjeparts sporing

Vi bruker ingen analyse-, annonserings- eller tredjepartssporingsinformasjonskapsler.
Alle informasjonskapsler og lagring er strengt nødvendige for at tjenesten skal fungere.

## Tredjepartstjenester

- **Google-tjenester**: Vi integrerer med Google-tjenester når du kobler til via Google OAuth:

  - **Google Drive** (valgfritt): Hvis du gir Google Drive-tillatelse, får vi tilgang til:
    - **Hva vi får tilgang til**: Filer opprettet av Haiku.lt i din Google Drive. Vi bruker `drive.file`-omfanget som gir tilgang kun til filer opprettet av applikasjonen vår - vi kan ikke se eller få tilgang til andre filer i din Drive.
    - **Hvordan vi bruker det**: For å lagre faktura-PDF-er til din Google Drive i en organisert mappestruktur (Haiku.lt/Invoices/Year). Når du bruker "Lagre til Drive"-funksjonen, oppretter eller oppdaterer vi PDF-filer.
    - **Hvordan vi lagrer det**: Vi lagrer Google Drive-fil-ID-en i databasen vår for å spore hvilke fakturaer som er lagret og for å muliggjøre oppdateringer av eksisterende filer. Selve PDF-innholdet lagres ikke på våre servere - det eksisterer kun i din Google Drive.
    - **Hvordan vi deler det**: Google Drive-fil-ID-er deles aldri med tredjeparter, selges aldri til datameglere, og brukes aldri til annonsering, markedsføring, AI-trening, eller noe annet formål enn å administrere faktura-PDF-ene dine i din Drive.
    - **Hvordan du kontrollerer det**: Du kan administrere Drive-tillatelser gjennom dine [Google-kontotillatelser](https://myaccount.google.com/permissions). Filene forblir i din Drive under din kontroll. Du kan slette dem når som helst. Tilbakekalling av tilgang stopper vår mulighet til å opprette nye filer eller oppdatere eksisterende.

  - **Gmail** (valgfritt): Hvis du gir Gmail-tillatelse, får vi tilgang til:
    - **Hva vi får tilgang til**: Tillatelse til å sende e-poster gjennom din Gmail-konto. Vi bruker `gmail.send`-omfanget som tillater sending av e-poster på dine vegne. Vi leser ikke dine eksisterende e-poster eller får tilgang til innboksen din.
    - **Hvordan vi bruker det**: For å sende faktura-e-poster til dine kjøpere når du bruker "Send faktura"-funksjonen. E-poster inkluderer faktura-PDF-en som vedlegg og valgfrie ekstra vedlegg (som CII XML for e-fakturering).
    - **Hvordan vi lagrer det**: Vi lagrer ikke e-postinnhold eller sendte meldingsdata. Sendte e-poster vises i din Gmails "Sendt"-mappe under din kontroll.
    - **Hvordan vi deler det**: E-postsendingsmulighet deles aldri med tredjeparter, selges aldri, og brukes aldri til annonsering, markedsføring, spam, eller noe annet formål enn å sende fakturaer du eksplisitt velger å sende.
    - **Hvordan du kontrollerer det**: Du kan administrere Gmail-tillatelser gjennom dine [Google-kontotillatelser](https://myaccount.google.com/permissions). Sendte e-poster forblir i din Gmail-konto. Tilbakekalling av tilgang stopper vår mulighet til å sende e-poster på dine vegne.

  - **Google Calendar** (valgfritt, kun lesing): Hvis du gir kalendertillatelse, får vi tilgang til:
    - **Hva vi får tilgang til**: Dine kalendernavn, hendelsestitler, hendelsesdatoer/-tider, og deltakerstatus (for å filtrere ut avslåtte hendelser). Vi bruker Google Calendar API-omfanget `calendar.readonly` som gir kun lesetilgang.
    - **Hvordan vi bruker det**: Utelukkende for å hjelpe deg med å opprette fakturaer basert på kalenderhendelser gjennom "Opprett fra kalender"-funksjonen. Hendelsestitler blir fakturalinjebeskrivelser, og hendelsesdatoer hjelper med å angi fakturadatointervall.
    - **Hvordan vi lagrer det**: Kalenderdata lagres **ikke permanent** i våre databaser. Det hentes på forespørsel kun når du bruker kalenderfakturafunksjonen og eksisterer midlertidig i nettleserens minne under fakturaopprettelsesprosessen.
    - **Hvordan vi deler det**: Kalenderdata **deles aldri** med tredjeparter, **selges aldri** til datameglere, og **brukes aldri** til annonsering, markedsføring, AI-trening, eller noe annet formål enn å opprette fakturaer for deg.
    - **Hvordan du kontrollerer det**: Du kan administrere kalendertillatelser uavhengig gjennom dine [Google-kontotillatelser](https://myaccount.google.com/permissions). Tilbakekalling av tilgang stopper datatilgang umiddelbart. Du kan også koble fra hele Google-kontoen din gjennom Haiku.lt-innstillingene.

  Alle Google OAuth-tillatelser krever din eksplisitte autorisasjon. Du kontrollerer hvilke tillatelser som skal gis og kan tilbakekalle dem når som helst.

- **Stripe**: Vi bruker Stripe for betalingsbehandling av premiumabonnementer.
  Stripe håndterer all betalingsinformasjon sikkert i henhold til deres personvernerklæring. Vi mottar kun bekreftelse på vellykkede betalinger.

- **Brevo (Sendinblue)**: Vi bruker Brevo for å levere transaksjonell e-post, inkludert e-poster for innlogging med magisk lenke og faktura-e-poster. Brevo mottar mottakerens e-postadresse og e-postinnhold som er nødvendig for å levere disse meldingene. Brevo er lokalisert i EU (Frankrike). Se deres [Personvernerklæring](https://www.brevo.com/legal/privacypolicy/).

## Databeskyttelse

For å beskytte innsamlede data tar vi følgende tiltak:

- Oppdatere serverprogramvare så ofte som mulig.

- Oppdatere Haiku.lt-programvare så ofte som mulig.

- Konfigurere servere på riktig måte.

## Dine rettigheter

For detaljert informasjon om dine datarettigheter under GDPR, inkludert retten
til å få tilgang til, slette og eksportere dine data, vennligst se vår [GDPR-side](/nb/gdpr).
