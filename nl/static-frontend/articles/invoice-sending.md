---
title: 'Facturen Versturen'
date: '2021-04-15'
modified: '2026-03-28'
---

Na het aanmaken van een factuur moet u deze aan de koper bezorgen.
Een handige methode is om de PDF via e-mail te versturen, en Haiku.lt
kan u hierbij helpen.

Haiku.lt ondersteunt twee manieren om e-mails te versturen:

## 1. Kies een E-mailverzendmethode

### Gmail (OAuth)

Als u bent ingelogd met Google, kan Haiku.lt e-mails rechtstreeks
verzenden vanuit uw Gmail-account via veilige OAuth — geen wachtwoord delen vereist.
Bij het inloggen moet u toestemming geven om e-mails namens u te versturen.
Als u dit aanvankelijk niet heeft gedaan, meld u dan af en opnieuw aan.

### SMTP

U kunt ook e-mails versturen via een willekeurige SMTP-server. Dit werkt met elke
e-mailprovider en is de enige optie voor niet-Gmail-gebruikers.

Om SMTP te configureren, ga naar [Instellingen → E-mailprovider-instellingen](/app/settings/email-provider):

1. Als u Gmail-login gebruikt, selecteer dan **SMTP** als uw verzendmethode.
2. Kies een **provider-voorinstelling** om de serverinstellingen automatisch in te vullen:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun of Aangepast
3. Vul de SMTP-gegevens in:
   - **Host** — SMTP-serveradres (bijv. `smtp.gmail.com`)
   - **Poort** — doorgaans 587 (STARTTLS) of 465 (SSL/TLS)
   - **Beveiliging** — STARTTLS upgradet een gewone verbinding naar versleuteld; SSL/TLS is versleuteld vanaf het begin
   - **Gebruikersnaam** — uw e-mailadres
   - **Wachtwoord** — uw e-mailwachtwoord of app-specifiek wachtwoord
   - **Van-adres** — het afzenderadres dat aan ontvangers wordt getoond (bijv. `Bedrijfsnaam <u@example.com>`)
4. Klik op **Verbinding testen** om uw instellingen te verifiëren voor het opslaan.
5. Klik op **SMTP-instellingen opslaan**.

## 2. E-mailinstellingen

In [Instellingen](/app/settings) kunt u configureren:

### E-mail Onderwerp

Pas de onderwerpregel van de e-mail aan naar uw behoeften. U kunt deze variabelen gebruiken:
- `{{invoiceNo}}` - factuurnummer (bijv. INV/001)
- `{{buyer}}` - kopernaam
- `{{seller}}` - verkopernaam
- `{{price}}` - factuurbedrag met valuta
- `{{invoiceDate}}` - factuurdatum

### E-mailsjablonen

Kies uit deze sjablonen:

**Platte tekst** - eenvoudig tekstformaat dat perfect werkt in alle e-mailclients.

**Eenvoudige HTML** - mooi opgemaakte HTML-e-mail met [MJML](https://mjml.io/) technologie.

**Met logo** - HTML-sjabloon met uw bedrijfslogo bovenaan.

**Met logo en prijs** - toont daarnaast het factuurbedrag in de e-mail.

**Met logo, prijs en extra info** - toont ook aanvullende informatie.

**Met logo, prijs en e-mailnotitie** - bevat een optionele notitie die u voor het verzenden kunt typen.

**Met regelitems** - toont een volledige tabel van factuurregelitems (naam, hoeveelheid, eenheidsprijs, totaal) samen met het eindtotaal.

HTML-sjablonen gebruiken het [MJML](https://mjml.io/) formaat, wat ervoor zorgt dat e-mails
er in alle e-mailclients geweldig uitzien. Als u uw eigen sjabloon wilt maken
of een bestaand sjabloon wilt aanpassen, kunt u AI om hulp vragen - beschrijf gewoon hoe u
wilt dat uw e-mail eruitziet, en AI kan de MJML-code voor u genereren.

### Sjabloonvariabelen

In alle sjablonen kunt u deze waarden gebruiken:

**Basisinformatie:**
- `{{issuer}}` - persoon die de factuur heeft gemaakt
- `{{invoiceNo}}` - factuurnummer
- `{{buyer}}` - koper
- `{{seller}}` - verkoper
- `{{price}}` - factuurbedrag
- `{{extra}}` - extra informatie
- `{{userNote}}` - uw notitie
- `{{emailNote}}` - notitie in de e-mail (ingevoerd tijdens verzending)
- `{{email}}` - e-mailadres van de koper

**Datums:**
- `{{invoiceDate}}` - factuurdatum
- `{{created}}` - aanmaakdatum factuur (hetzelfde als invoiceDate)

**Factuurdetails:**
- `{{seriesName}}` - serienaam factuur (bijv. "INV")
- `{{seriesId}}` - nummer in serie (bijv. "001")
- `{{language}}` - factuurtaal ("lt" of "en")

**Logo:**
- `{{logoUrl}}` - logo-URL

**Merkenkleuren:**
- `{{brandPrimary}}` - primaire kleur
- `{{brandSecondary}}` - secundaire kleur
- `{{brandText}}` - tekstkleur
- `{{brandTextSecondary}}` - secundaire tekstkleur
- `{{brandBackground}}` - achtergrondkleur
- `{{bodyBackground}}` - pagina achtergrondkleur
- `{{backgroundSecondary}}` - secundaire achtergrondkleur

### Regelitems

U kunt over factuurregelitems lopen met Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Elk regelitem stelt het volgende beschikbaar:
- `{{name}}` - artikelnaam
- `{{amount}}` - hoeveelheid
- `{{unit}}` - ruwe UN/ECE-eenheidscode (bijv. `H87`)
- `{{unitName}}` - lange vorm van de eenheid, gelokaliseerd (bijv. "stuk", "kilogram")
- `{{unitSymbol}}` - korte vorm van de eenheid, gelokaliseerd (bijv. "st", "kg")
- `{{unitPrice}}` - opgemaakte prijs per eenheid (bijv. "€10,00")
- `{{formattedPrice}}` - opgemaakt regeltotaal — hoeveelheid × eenheidsprijs (bijv. "€30,00")
- `{{vat}}` - btw-percentage (indien ingesteld)
- `{{vatcode}}` - btw-code (indien ingesteld)

### Voorwaardelijke Sjablonen

U kunt Handlebars-voorwaarden gebruiken om inhoud alleen weer te geven wanneer een waarde bestaat:

```
{{#if extra}}
  <mj-text>Extra informatie: {{extra}}</mj-text>
{{/if}}
```

Dit is vooral handig wanneer u een extra informatieblok
alleen wilt weergeven wanneer het daadwerkelijk is ingevuld.

### Merkenkleuren en Logo

In instellingen kunt u ook:
- Uw logo uploaden
- Merkenkleuren wijzigen

## 3. De Factuur Versturen

1. Specificeer het e-mailadres van de koper in de factuur
2. Klik op de knop "Factuur versturen"
3. De factuur wordt gemarkeerd als vergrendeld en verstuurd

De factuur wordt verstuurd vanuit uw Gmail-account met het geselecteerde sjabloon.
