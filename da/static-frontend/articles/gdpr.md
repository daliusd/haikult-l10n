---
title: 'GDPR - Dine datarettigheder'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt er forpligtet til at beskytte dine personoplysninger og respektere dine privatlivsrettigheder i henhold til den generelle databeskyttelsesforordning (GDPR). Denne side forklarer dine rettigheder, og hvordan vi håndterer dine data.

## Dine datarettigheder

I henhold til GDPR har du følgende rettigheder vedrørende dine personoplysninger:

### Ret til indsigt

Du har ret til at få adgang til alle personoplysninger, vi opbevarer om dig. Du kan eksportere dine data til enhver tid:

- **Fuld databaseeksport**: Download din komplette database, inklusive alle fakturaer, indstillinger og revisionslogfiler fra dine kontoindstillinger.
- **Fakturaeksport**: Eksporter dine fakturaer som CSV-format, filtreret efter datointerval og serienavn.

### Ret til sletning (ret til at blive glemt)

Du har ret til at anmode om sletning af dine personoplysninger. Du kan til enhver tid slette hele din konto og alle tilknyttede data gennem dine kontoindstillinger. Denne handling er permanent og kan ikke fortrydes.

### Ret til dataportabilitet

Du kan eksportere dine data i maskinlæsbare formater:

- SQLite-databaseformat (komplet dataeksport)
- CSV-format (fakturaeksport)

Dette giver dig mulighed for at overføre dine data til en anden tjeneste, hvis du ønsker det.

### Ret til berigtigelse

Du har ret til at rette unøjagtige eller ufuldstændige personoplysninger. Du kan redigere alle dine data direkte i applikationen, inklusive:

- Fakturadetaljer
- Køber- og sælgerinformation
- Dine personlige præferencer og indstillinger

### Ret til begrænsning af behandling

Du har ret til at anmode om begrænsning af behandlingen af dine personoplysninger under visse omstændigheder. Kontakt os ved hjælp af e-mailen nedenfor for at udøve denne ret.

### Ret til indsigelse

Du har ret til at gøre indsigelse mod behandlingen af dine personoplysninger til specifikke formål. Da Haiku.lt behandler dine data udelukkende for at levere den faktureringstjeneste, du har anmodet om, vil indsigelse mod behandling forhindre os i at levere tjenesten.

## Dataopbevaring

Dine data opbevares **indtil du sletter din konto**. Vi sletter ikke automatisk inaktive konti. Du har fuld kontrol over, hvornår dine data fjernes.

Når du sletter din konto, fjernes alle dine data permanent fra vores systemer.

## Dataansvarlig

Den dataansvarlige for Haiku.lt er:

**Dalius Dobravolskas**

For privatlivsrelaterede spørgsmål eller for at udøve dine datarettigheder, kontakt:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Serverplacering

Alle Haiku.lt-servere og datalagring er placeret i **Den Europæiske Union, specifikt i Tyskland**. Dine data forlader ikke EU, medmindre du udtrykkeligt autoriserer tredjepartsintegrationer (se Databehandlere nedenfor).

## Retsgrundlag for behandling

Vi behandler dine personoplysninger baseret på:

- **Kontraktopfyldelse**: For at levere den faktureringstjeneste, du tilmeldte dig
- **Legitim interesse**: For at opretholde tjenesteens sikkerhed, forhindre bedrageri og forbedre tjenesten
- **Samtykke**: Til valgfrie funktioner som Google Drive og Gmail-integration

## Databehandlere

Haiku.lt bruger følgende tredjepartstjenester til at levere vores funktionalitet:

### Google LLC

**Anvendte tjenester**: OAuth 2.0-godkendelse, Google Drive API, Gmail API, Google Calendar API

**Delte data**: E-mailadresse, navn, OAuth-tokens (kun når du autoriserer Google-integration)

**Formål**: For at gøre det muligt for dig at:
- **Godkende** med din Google-konto ved hjælp af OAuth 2.0
- **Google Drive** (omfang: `drive.file`): Gem faktura-PDF'er på din Drive i organiserede mapper (Haiku.lt/Invoices/År). Vi kan kun få adgang til filer oprettet af vores applikation, ikke dine andre Drive-filer. Vi gemmer Drive-fil-ID'er for at spore gemte fakturaer.
- **Gmail** (omfang: `gmail.send`): Send faktura-e-mails til købere på dine vegne. Vi læser ikke din indbakke eller eksisterende e-mails. Sendte e-mails vises i din Gmail "Sendt"-mappe.
- **Google Calendar** (omfang: `calendar.readonly`, valgfrit): Læs kalenderbegivenhedstitler, datoer, tidspunkter og deltagerstatus for at hjælpe med at oprette fakturaer. Disse data hentes midlertidigt og gemmes ikke permanent.

**Dataopbevaring**:
- Drive-fil-ID'er: Gemt i vores database, indtil du sletter fakturaen eller afbryder din Google-konto
- Kalenderdata: Ikke gemt (hentes kun on-demand)
- Gmail-data: Ikke gemt (e-mails forbliver på din Gmail-konto)
- OAuth-tokens: Krypteret og gemt, indtil du afbryder din konto

**Fortrolighedspolitik**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Placering**: USA (med EU-US Data Privacy Framework-overholdelse)

### Stripe, Inc.

**Anvendte tjenester**: Betalingsbehandling til abonnementer

**Delte data**: E-mailadresse, betalingsinformation (håndteret direkte af Stripe)

**Formål**: At behandle abonnementsbetalinger for premium-funktioner

**Fortrolighedspolitik**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Placering**: USA (med EU-US Data Privacy Framework-overholdelse)

### Brevo (Sendinblue)

**Anvendte tjenester**: Levering af transaktionelle e-mails

**Delte data**: Modtagerens e-mailadresse, e-mailindhold (magisk link-tokens til login; fakturaoplysninger ved afsendelse af fakturaer via Brevo)

**Formål**: At levere godkendelses-e-mails (magisk link-login) og faktura-e-mails til købere

**Dataopbevaring**: Brevo kan opbevare sendte e-maillogfiler i en begrænset periode i henhold til deres politik. Vi gemmer ikke e-mailindhold på vores servere ud over hvad der er nødvendigt for at sende det.

**Fortrolighedspolitik**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Placering**: Den Europæiske Union (Frankrig)

## Datasikkerhed

Vi træffer passende tekniske og organisatoriske foranstaltninger for at beskytte dine personoplysninger:

- Kryptering af følsomme data (OAuth-tokens, refresh-tokens)
- Sikre HTTPS-forbindelser
- HTTP-only, sikre godkendelsescookies
- Regelmæssige softwareopdateringer
- Per-bruger databaseisolering
- Revisionslogning til sporing af kontoadgang

## Underretning om databrud

I det usandsynlige tilfælde af et databrud, der udgør en risiko for dine rettigheder og frihedsrettigheder, vil vi underrette dig og den relevante tilsynsmyndighed inden for 72 timer som krævet af GDPR.

## Tilsynsmyndighed

Hvis du har bekymringer om, hvordan vi håndterer dine personoplysninger, har du ret til at indgive en klage til din lokale tilsynsmyndighed for databeskyttelse.

For brugere i Danmark er tilsynsmyndigheden:

**Datatilsynet**
Hjemmeside: [https://www.datatilsynet.dk](https://www.datatilsynet.dk)

## Opdateringer til denne politik

Vi kan opdatere denne GDPR-informationsside fra tid til anden. "Ændret"-datoen øverst på denne side angiver, hvornår den sidst blev opdateret.

For generel privatlivsinformation, se vores [Privatlivspolitik](/da/privacy).
