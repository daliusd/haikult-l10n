---
title: 'Skicka fakturor'
date: '2021-04-15'
modified: '2026-03-28'
---

Efter att ha skapat en faktura måste du leverera den till köparen.
En bekväm metod är att skicka PDF:en via e-post, och Haiku.lt
kan hjälpa till med detta.

Haiku.lt stöder två sätt att skicka e-post:

## 1. Välj en metod för e-postsändning

### Gmail (OAuth)

Om du är inloggad med Google kan Haiku.lt skicka e-post direkt
från ditt Gmail-konto med säker OAuth — ingen lösenordsdelning krävs.
När du loggar in måste du ge tillstånd att skicka e-post å dina vägnar.
Om du inte gjorde detta initialt, logga ut och logga in igen.

### SMTP

Du kan också skicka e-post via valfri SMTP-server. Det fungerar med vilken
e-postleverantör som helst och är det enda alternativet för icke-Gmail-användare.

För att konfigurera SMTP, gå till [Inställningar → E-postleverantörsinställningar](/app/settings/email-provider):

1. Om du använder Gmail-inloggning, välj **SMTP** som din sändningsmetod.
2. Välj en **leverantörsförinställning** för att automatiskt fylla i serverinställningarna:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun eller Anpassad
3. Fyll i SMTP-detaljerna:
   - **Värd** — SMTP-serveradress (t.ex. `smtp.gmail.com`)
   - **Port** — vanligtvis 587 (STARTTLS) eller 465 (SSL/TLS)
   - **Säkerhet** — STARTTLS uppgraderar en okrypterad anslutning till krypterad; SSL/TLS är krypterat från start
   - **Användarnamn** — din e-postadress
   - **Lösenord** — ditt e-postlösenord eller app-specifikt lösenord
   - **Från-adress** — avsändaradressen som visas för mottagare (t.ex. `Företagsnamn <du@example.com>`)
4. Klicka på **Testa anslutning** för att verifiera dina inställningar innan du sparar.
5. Klicka på **Spara SMTP-inställningar**.

## 2. E-postinställningar

I [Inställningar](/app/settings) kan du konfigurera:

### E-postämne

Anpassa e-postämnesraden för att passa dina behov. Du kan använda dessa variabler:
- `{{invoiceNo}}` - fakturanummer (t.ex. FAK/001)
- `{{buyer}}` - köparnamn
- `{{seller}}` - säljarnamn
- `{{price}}` - fakturabelopp med valuta
- `{{invoiceDate}}` - fakturadatum

### E-postmallar

Välj bland dessa mallar:

**Enkel text** - enkelt textformat som fungerar perfekt i alla e-postklienter.

**Enkel HTML** - vackert formaterad HTML-e-post med [MJML](https://mjml.io/)-teknologi.

**Med logotyp** - HTML-mall med din företagslogotyp överst.

**Med logotyp och pris** - visar dessutom fakturabeloppet i e-postmeddelandet.

**Med logotyp, pris och ytterligare info** - visar även ytterligare information.

**Med logotyp, pris och e-postnotering** - innehåller en valfri notering som du kan skriva innan du skickar.

**Med radartiklar** - visar en fullständig tabell över fakturans radartiklar (namn, antal, enhetspris, totalt) tillsammans med totalsumman.

HTML-mallar använder [MJML](https://mjml.io/)-formatet, vilket säkerställer att e-postmeddelanden
ser bra ut i alla e-postklienter. Om du vill skapa din egen mall
eller modifiera en befintlig kan du be AI om hjälp - beskriv bara hur du
vill att din e-post ska se ut, och AI kan generera MJML-koden åt dig.

### Mallvariabler

I alla mallar kan du använda dessa värden:

**Grundläggande information:**
- `{{issuer}}` - person som skapade fakturan
- `{{invoiceNo}}` - fakturanummer
- `{{buyer}}` - köpare
- `{{seller}}` - säljare
- `{{price}}` - fakturabelopp
- `{{extra}}` - ytterligare information
- `{{userNote}}` - din anteckning
- `{{emailNote}}` - anteckning i e-postmeddelandet (anges vid sändning)
- `{{email}}` - köparens e-postadress

**Datum:**
- `{{invoiceDate}}` - fakturadatum
- `{{created}}` - fakturans skapandedatum (samma som invoiceDate)

**Fakturadetaljer:**
- `{{seriesName}}` - fakturaserienamn (t.ex. "FAK")
- `{{seriesId}}` - nummer i serie (t.ex. "001")
- `{{language}}` - fakturaspråk ("lt" eller "en")

**Logotyp:**
- `{{logoUrl}}` - logotyp-URL

**Varumärkesfärger:**
- `{{brandPrimary}}` - primär färg
- `{{brandSecondary}}` - sekundär färg
- `{{brandText}}` - textfärg
- `{{brandTextSecondary}}` - sekundär textfärg
- `{{brandBackground}}` - bakgrundsfärg
- `{{bodyBackground}}` - sidbakgrundsfärg
- `{{backgroundSecondary}}` - sekundär bakgrundsfärg

### Radartiklar

Du kan loopa över fakturans radartiklar med Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Varje radartikel exponerar:
- `{{name}}` - artikelnamn
- `{{amount}}` - antal
- `{{unit}}` - rå UN/ECE-enhetskod (t.ex. `H87`)
- `{{unitName}}` - enhetens långa form, lokaliserad (t.ex. "styck", "kilogram")
- `{{unitSymbol}}` - enhetens korta form, lokaliserad (t.ex. "st", "kg")
- `{{unitPrice}}` - formaterat pris per enhet (t.ex. "€10,00")
- `{{formattedPrice}}` - formaterad radtotal — antal × enhetspris (t.ex. "€30,00")
- `{{vat}}` - momsprocent (om angiven)
- `{{vatcode}}` - momskod (om angiven)

### Villkorliga mallar

Du kan använda Handlebars-villkor för att visa innehåll endast när ett värde finns:

```
{{#if extra}}
  <mj-text>Ytterligare information: {{extra}}</mj-text>
{{/if}}
```

Detta är särskilt användbart när du vill visa ett ytterligare informationsblock
endast när det faktiskt är ifyllt.

### Varumärkesfärger och logotyp

I inställningar kan du också:
- Ladda upp din logotyp
- Ändra varumärkesfärger

## 3. Skicka fakturan

1. Ange köparens e-postadress i fakturan
2. Klicka på knappen "Skicka faktura"
3. Fakturan kommer att markeras som låst och skickas

Fakturan kommer att skickas från ditt Gmail-konto med den valda mallen.
