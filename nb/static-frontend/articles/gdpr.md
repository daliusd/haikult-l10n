---
title: 'GDPR - Dine datarettigheter'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt er forpliktet til å beskytte dine personopplysninger og respektere dine personvernrettigheter under General Data Protection Regulation (GDPR). Denne siden forklarer dine rettigheter og hvordan vi håndterer dine data.

## Dine datarettigheter

Under GDPR har du følgende rettigheter angående dine personopplysninger:

### Rett til tilgang

Du har rett til å få tilgang til alle personopplysninger vi har om deg. Du kan eksportere dine data når som helst:

- **Full databaseeksport**: Last ned din komplette database inkludert alle fakturaer, innstillinger og revisjonslogger fra kontoinnstillingene dine.
- **Fakturaeksport**: Eksporter fakturaene dine som CSV-format, filtrert etter datointervall og serienavn.

### Rett til sletting (Rett til å bli glemt)

Du har rett til å be om sletting av dine personopplysninger. Du kan slette hele kontoen din og alle tilhørende data når som helst gjennom kontoinnstillingene dine. Denne handlingen er permanent og kan ikke angres.

### Rett til dataportabilitet

Du kan eksportere dine data i maskinlesbare formater:

- SQLite-databaseformat (komplett dataeksport)
- CSV-format (fakturadataeksport)

Dette lar deg overføre dine data til en annen tjeneste hvis du velger det.

### Rett til retting

Du har rett til å korrigere unøyaktige eller ufullstendige personopplysninger. Du kan redigere alle dine data direkte i applikasjonen, inkludert:

- Fakturadetaljer
- Kjøper- og selgerinformasjon
- Dine personlige preferanser og innstillinger

### Rett til begrensning av behandling

Du har rett til å be om begrensning av behandlingen av dine personopplysninger under visse omstendigheter. Kontakt oss ved hjelp av e-postadressen nedenfor for å utøve denne rettigheten.

### Rett til å protestere

Du har rett til å protestere mot behandlingen av dine personopplysninger for spesifikke formål. Siden Haiku.lt behandler dine data utelukkende for å tilby faktureringstjenesten du ba om, vil protest mot behandling hindre oss i å tilby tjenesten.

## Dataoppbevaring

Dine data beholdes **til du sletter kontoen din**. Vi sletter ikke inaktive kontoer automatisk. Du har full kontroll over når dine data fjernes.

Når du sletter kontoen din, fjernes alle dine data permanent fra våre systemer.

## Dataansvarlig

Dataansvarlig for Haiku.lt er:

**Dalius Dobravolskas**

For personvernrelaterte spørsmål eller for å utøve dine datarettigheter, kontakt:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Serverplassering

Alle Haiku.lt-servere og datalagring er lokalisert i **Den europeiske union, spesifikt i Tyskland**. Dine data forlater ikke EU med mindre du eksplisitt autoriserer tredjepartsintegrasjoner (se underdatabehandlere nedenfor).

## Rettslig grunnlag for behandling

Vi behandler dine personopplysninger basert på:

- **Kontraktsoppfyllelse**: For å tilby faktureringstjenesten du registrerte deg for
- **Legitim interesse**: For å opprettholde tjenestesikkerhet, forhindre svindel og forbedre tjenesten
- **Samtykke**: For valgfrie funksjoner som Google Drive og Gmail-integrasjon

## Underdatabehandlere

Haiku.lt bruker følgende tredjepartstjenester for å tilby vår funksjonalitet:

### Google LLC

**Tjenester som brukes**: OAuth 2.0-autentisering, Google Drive API, Gmail API, Google Calendar API

**Data som deles**: E-postadresse, navn, OAuth-tokener (kun når du autoriserer Google-integrasjon)

**Formål**: For å gjøre det mulig for deg å:
- **Autentisere** med din Google-konto ved hjelp av OAuth 2.0
- **Google Drive** (omfang: `drive.file`): Lagre faktura-PDF-er til din Drive i organiserte mapper (Haiku.lt/Invoices/Year). Vi kan kun få tilgang til filer opprettet av applikasjonen vår, ikke dine andre Drive-filer. Vi lagrer Drive-fil-ID-er for å spore lagrede fakturaer.
- **Gmail** (omfang: `gmail.send`): Sende faktura-e-poster til kjøpere på dine vegne. Vi leser ikke din innboks eller eksisterende e-poster. Sendte e-poster vises i din Gmails "Sendt"-mappe.
- **Google Calendar** (omfang: `calendar.readonly`, valgfritt): Lese kalenderhendelsestitler, datoer, tider og deltakerstatus for å hjelpe med å opprette fakturaer. Disse dataene hentes midlertidig og lagres ikke permanent.

**Dataoppbevaring**:
- Drive-fil-ID-er: Lagret i vår database til du sletter fakturaen eller kobler fra Google-kontoen din
- Kalenderdata: Ikke lagret (hentes kun på forespørsel)
- Gmail-data: Ikke lagret (e-poster forblir i din Gmail-konto)
- OAuth-tokener: Kryptert og lagret til du kobler fra kontoen din

**Personvernerklæring**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Plassering**: USA (med samsvar med EU-US Data Privacy Framework)

### Stripe, Inc.

**Tjenester som brukes**: Betalingsbehandling for abonnementer

**Data som deles**: E-postadresse, betalingsinformasjon (håndteres direkte av Stripe)

**Formål**: For å behandle abonnementsbetalinger for premiumfunksjoner

**Personvernerklæring**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Plassering**: USA (med samsvar med EU-US Data Privacy Framework)

### Brevo (Sendinblue)

**Tjenester som brukes**: Levering av transaksjonell e-post

**Data som deles**: Mottakerens e-postadresse, e-postinnhold (tokens for magisk lenke-innlogging; fakturaopplysninger ved sending av fakturaer via Brevo)

**Formål**: For å levere autentiserings-e-poster (innlogging med magisk lenke) og faktura-e-poster til kjøpere

**Dataoppbevaring**: Brevo kan oppbevare logger over sendte e-poster i en begrenset periode i henhold til deres policy. Vi lagrer ikke e-postinnhold på våre servere utover hva som er nødvendig for å sende det.

**Personvernerklæring**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Plassering**: Den europeiske union (Frankrike)

## Datasikkerhet

Vi tar passende tekniske og organisatoriske tiltak for å beskytte dine personopplysninger:

- Kryptering av sensitive data (OAuth-tokener, oppdateringstokener)
- Sikre HTTPS-tilkoblinger
- HTTP-only, sikre autentiseringsinformasjonskapsler
- Regelmessige programvareoppdateringer
- Isolasjon av database per bruker
- Revisjonslogging for sporing av kontotilgang

## Varsel om databrudd

I det usannsynlige tilfellet av et databrudd som utgjør en risiko for dine rettigheter og friheter, vil vi varsle deg og relevant tilsynsmyndighet innen 72 timer som kreves av GDPR.

## Tilsynsmyndighet

Hvis du har bekymringer om hvordan vi håndterer dine personopplysninger, har du rett til å klage til din lokale datatilsynsmyndighet.

For brukere i Litauen er tilsynsmyndigheten:

**State Data Protection Inspectorate**
Nettsted: [https://vdai.lrv.lt](https://vdai.lrv.lt)

## Oppdateringer av denne policyen

Vi kan oppdatere denne GDPR-informasjonssiden fra tid til annen. "Modified"-datoen øverst på denne siden indikerer når den sist ble oppdatert.

For generell personverninformasjon, se vår [Personvernerklæring](/nb/privacy).
