---
title: 'Afsendelse af fakturaer'
date: '2021-04-15'
modified: '2026-03-28'
---

Efter oprettelse af en faktura skal du levere den til køberen.
En praktisk metode er at sende PDF'en via e-mail, og Haiku.lt
kan hjælpe med dette.

Haiku.lt understøtter to måder at sende e-mails på:

## 1. Vælg en metode til e-mailafsendelse

### Gmail (OAuth)

Hvis du er logget ind med Google, kan Haiku.lt sende e-mails direkte
fra din Gmail-konto ved hjælp af sikker OAuth — ingen deling af adgangskode kræves.
Når du logger ind, skal du give tilladelse til at sende e-mails på dine vegne.
Hvis du ikke gjorde dette oprindeligt, skal du logge ud og logge ind igen.

### SMTP

Du kan også sende e-mails via enhver SMTP-server. Dette fungerer med enhver
e-mailudbyder og er den eneste mulighed for ikke-Gmail-brugere.

For at konfigurere SMTP, gå til [Indstillinger → E-mailudbyder-indstillinger](/app/settings/email-provider):

1. Hvis du bruger Gmail-login, vælg **SMTP** som din afsendelsesmetode.
2. Vælg en **udbyder-forudindstilling** for automatisk at udfylde serverindstillingerne:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun eller Brugerdefineret
3. Udfyld SMTP-oplysningerne:
   - **Vært** — SMTP-serveradresse (f.eks. `smtp.gmail.com`)
   - **Port** — typisk 587 (STARTTLS) eller 465 (SSL/TLS)
   - **Sikkerhed** — STARTTLS opgraderer en almindelig forbindelse til krypteret; SSL/TLS er krypteret fra starten
   - **Brugernavn** — din e-mailadresse
   - **Adgangskode** — din e-mail-adgangskode eller app-specifik adgangskode
   - **Fra-adresse** — afsenderadressen vist til modtagere (f.eks. `Virksomhedsnavn <dig@example.com>`)
4. Klik på **Test forbindelse** for at verificere dine indstillinger før gemning.
5. Klik på **Gem SMTP-indstillinger**.

## 2. E-mailindstillinger

I [Indstillinger](/app/settings) kan du konfigurere:

### E-mailemne

Tilpas e-mailens emnelinje, så den passer til dine behov. Du kan bruge disse variabler:
- `{{invoiceNo}}` - fakturanummer (f.eks. INV/001)
- `{{buyer}}` - købers navn
- `{{seller}}` - sælgers navn
- `{{price}}` - fakturabeløb med valuta
- `{{invoiceDate}}` - fakturadato

### E-mailskabeloner

Vælg mellem disse skabeloner:

**Ren tekst** - simpelt tekstformat, der fungerer perfekt i alle e-mailklienter.

**Simpel HTML** - smukt formateret HTML-e-mail ved hjælp af [MJML](https://mjml.io/)-teknologi.

**Med logo** - HTML-skabelon med dit firmalogo øverst.

**Med logo og pris** - viser yderligere fakturabeløbet i e-mailen.

**Med logo, pris og yderligere info** - viser også yderligere information.

**Med logo, pris og e-mailnote** - inkluderer en valgfri note, du kan skrive inden afsendelse.

**Med linjeelementer** - viser en fuld tabel over fakturaens linjeelementer (navn, antal, enhedspris, total) samt det samlede beløb.

HTML-skabeloner bruger [MJML](https://mjml.io/)-formatet, som sikrer, at e-mails
ser fantastiske ud på tværs af alle e-mailklienter. Hvis du vil oprette din egen skabelon
eller ændre en eksisterende, kan du bede AI om hjælp - beskriv blot, hvordan du
vil have din e-mail til at se ud, og AI kan generere MJML-koden for dig.

### Skabelonvariabler

I alle skabeloner kan du bruge disse værdier:

**Grundlæggende information:**
- `{{issuer}}` - person, der oprettede fakturaen
- `{{invoiceNo}}` - fakturanummer
- `{{buyer}}` - køber
- `{{seller}}` - sælger
- `{{price}}` - fakturabeløb
- `{{extra}}` - yderligere information
- `{{userNote}}` - din note
- `{{emailNote}}` - note i e-mailen (indtastet under afsendelse)
- `{{email}}` - købers e-mail

**Datoer:**
- `{{invoiceDate}}` - fakturadato
- `{{created}}` - fakturaoprettelsesdato (samme som invoiceDate)

**Fakturadetaljer:**
- `{{seriesName}}` - fakturaserienavn (f.eks. "INV")
- `{{seriesId}}` - nummer i serien (f.eks. "001")
- `{{language}}` - fakturasprog ("lt" eller "en")

**Logo:**
- `{{logoUrl}}` - logo-URL

**Brandfarver:**
- `{{brandPrimary}}` - primær farve
- `{{brandSecondary}}` - sekundær farve
- `{{brandText}}` - tekstfarve
- `{{brandTextSecondary}}` - sekundær tekstfarve
- `{{brandBackground}}` - baggrundsfarve
- `{{bodyBackground}}` - sidebaggrundsfarve
- `{{backgroundSecondary}}` - sekundær baggrundsfarve

### Linjeelementer

Du kan gennemløbe fakturaens linjeelementer med Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Hvert linjeelement eksponerer:
- `{{name}}` - varenavn
- `{{amount}}` - antal
- `{{unit}}` - rå UN/ECE-enhedskode (f.eks. `H87`)
- `{{unitName}}` - enhedens lange form, lokaliseret (f.eks. "styk", "kilogram")
- `{{unitSymbol}}` - enhedens korte form, lokaliseret (f.eks. "stk", "kg")
- `{{unitPrice}}` - formateret pris per enhed (f.eks. "€10,00")
- `{{formattedPrice}}` - formateret linjetotal — antal × enhedspris (f.eks. "€30,00")
- `{{vat}}` - momsprocent (hvis angivet)
- `{{vatcode}}` - momskode (hvis angivet)

### Betingede skabeloner

Du kan bruge Handlebars-betingelser til at vise indhold kun, når en værdi findes:

```
{{#if extra}}
  <mj-text>Yderligere information: {{extra}}</mj-text>
{{/if}}
```

Dette er især nyttigt, når du vil vise en yderligere informationsblok
kun når den faktisk er udfyldt.

### Brandfarver og logo

I indstillinger kan du også:
- Uploade dit logo
- Ændre brandfarver

## 3. Afsendelse af fakturaen

1. Angiv køberens e-mailadresse på fakturaen
2. Klik på knappen "Send faktura"
3. Fakturaen vil blive markeret som låst og sendt

Fakturaen sendes fra din Gmail-konto ved hjælp af den valgte skabelon.
