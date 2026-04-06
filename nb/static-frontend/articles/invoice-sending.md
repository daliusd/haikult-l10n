---
title: 'Sende fakturaer'
date: '2021-04-15'
modified: '2026-03-28'
---

Etter å ha opprettet en faktura, må du levere den til kjøperen.
En praktisk metode er å sende PDF-en via e-post, og Haiku.lt
kan hjelpe med dette.

Haiku.lt støtter to måter å sende e-post på:

## 1. Velg en metode for e-postsending

### Gmail (OAuth)

Hvis du er logget inn med Google, kan Haiku.lt sende e-poster direkte
fra din Gmail-konto ved hjelp av sikker OAuth — ingen deling av passord kreves.
Når du logger inn, må du gi tillatelse til å sende e-poster på dine vegne.
Hvis du ikke gjorde dette i utgangspunktet, logg ut og logg inn igjen.

### SMTP

Du kan også sende e-poster via en hvilken som helst SMTP-server. Dette fungerer med enhver
e-postleverandør og er det eneste alternativet for ikke-Gmail-brukere.

For å konfigurere SMTP, gå til [Innstillinger → E-postleverandørinnstillinger](/app/settings/email-provider):

1. Hvis du bruker Gmail-innlogging, velg **SMTP** som sendingsmetode.
2. Velg en **leverandørforhåndsinnstilling** for å fylle inn serverinnstillingene automatisk:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun eller Egendefinert
3. Fyll inn SMTP-detaljene:
   - **Vert** — SMTP-serveradresse (f.eks. `smtp.gmail.com`)
   - **Port** — vanligvis 587 (STARTTLS) eller 465 (SSL/TLS)
   - **Sikkerhet** — STARTTLS oppgraderer en ukryptert tilkobling til kryptert; SSL/TLS er kryptert fra starten
   - **Brukernavn** — din e-postadresse
   - **Passord** — ditt e-postpassord eller app-spesifikt passord
   - **Fra-adresse** — avsenderadressen som vises til mottakere (f.eks. `Firmanavn <deg@example.com>`)
4. Klikk på **Test tilkobling** for å verifisere innstillingene dine før lagring.
5. Klikk på **Lagre SMTP-innstillinger**.

## 2. E-postinnstillinger

I [Innstillinger](/app/settings) kan du konfigurere:

### E-postemne

Tilpass e-postemnelinje for å passe dine behov. Du kan bruke disse variablene:
- `{{invoiceNo}}` - fakturanummer (f.eks. INV/001)
- `{{buyer}}` - kjøpernavn
- `{{seller}}` - selgernavn
- `{{price}}` - fakturabeløp med valuta
- `{{invoiceDate}}` - fakturadato

### E-postmaler

Velg fra disse malene:

**Ren tekst** - enkelt tekstformat som fungerer perfekt i alle e-postklienter.

**Enkel HTML** - vakkert formatert HTML-e-post ved hjelp av [MJML](https://mjml.io/)-teknologi.

**Med logo** - HTML-mal med bedriftslogoen din øverst.

**Med logo og pris** - viser i tillegg fakturabeløpet i e-posten.

**Med logo, pris og tilleggsinformasjon** - viser også tilleggsinformasjon.

**Med logo, pris og e-postnotat** - inkluderer et valgfritt notat du kan skrive før sending.

**Med linjeartikler** - viser en fullstendig tabell over fakturaens linjeartikler (navn, antall, enhetspris, total) sammen med totalbeløpet.

HTML-maler bruker [MJML](https://mjml.io/)-formatet, som sikrer at e-poster
ser flotte ut på tvers av alle e-postklienter. Hvis du ønsker å opprette din egen mal
eller endre en eksisterende, kan du be AI om hjelp - bare beskriv hvordan du
ønsker at e-posten din skal se ut, og AI kan generere MJML-koden for deg.

### Malvariabler

I alle maler kan du bruke disse verdiene:

**Grunnleggende informasjon:**
- `{{issuer}}` - personen som opprettet fakturaen
- `{{invoiceNo}}` - fakturanummer
- `{{buyer}}` - kjøper
- `{{seller}}` - selger
- `{{price}}` - fakturabeløp
- `{{extra}}` - tilleggsinformasjon
- `{{userNote}}` - ditt notat
- `{{emailNote}}` - notat i e-posten (lagt inn under sending)
- `{{email}}` - kjøperens e-post

**Datoer:**
- `{{invoiceDate}}` - fakturadato
- `{{created}}` - fakturaopprettelsesdato (samme som invoiceDate)

**Fakturadetaljer:**
- `{{seriesName}}` - fakturaserienavn (f.eks. "INV")
- `{{seriesId}}` - nummer i serie (f.eks. "001")
- `{{language}}` - fakturaspråk ("lt" eller "en")

**Logo:**
- `{{logoUrl}}` - logo-URL

**Merkefarger:**
- `{{brandPrimary}}` - primærfarge
- `{{brandSecondary}}` - sekundærfarge
- `{{brandText}}` - tekstfarge
- `{{brandTextSecondary}}` - sekundær tekstfarge
- `{{brandBackground}}` - bakgrunnsfarge
- `{{bodyBackground}}` - sidebakgrunnsfarge
- `{{backgroundSecondary}}` - sekundær bakgrunnsfarge

### Linjeartikler

Du kan gå gjennom fakturaens linjeartikler med Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Hver linjeartikkel eksponerer:
- `{{name}}` - varenavn
- `{{amount}}` - antall
- `{{unit}}` - rå UN/ECE-enhetskode (f.eks. `H87`)
- `{{unitName}}` - enhetens lange form, lokalisert (f.eks. "stykk", "kilogram")
- `{{unitSymbol}}` - enhetens korte form, lokalisert (f.eks. "stk", "kg")
- `{{unitPrice}}` - formatert pris per enhet (f.eks. "€10,00")
- `{{formattedPrice}}` - formatert linjetotal — antall × enhetspris (f.eks. "€30,00")
- `{{vat}}` - MVA-prosent (hvis angitt)
- `{{vatcode}}` - MVA-kode (hvis angitt)

### Betingede maler

Du kan bruke Handlebars-betingelser for å vise innhold kun når en verdi eksisterer:

```
{{#if extra}}
  <mj-text>Tilleggsinformasjon: {{extra}}</mj-text>
{{/if}}
```

Dette er spesielt nyttig når du ønsker å vise en tilleggsinformasjons-
blokk kun når den faktisk er fylt ut.

### Merkefarger og logo

I innstillinger kan du også:
- Laste opp logoen din
- Endre merkefarger

## 3. Sende fakturaen

1. Spesifiser kjøperens e-postadresse i fakturaen
2. Klikk på "Send faktura"-knappen
3. Fakturaen vil bli merket som låst og sendt

Fakturaen vil bli sendt fra din Gmail-konto ved hjelp av den valgte malen.
