---
title: 'Laskujen lähettäminen'
date: '2021-04-15'
modified: '2026-03-28'
---

Kun olet luonut laskun, sinun täytyy toimittaa se ostajalle. Yksi kätevä tapa on lähettää PDF sähköpostilla, ja Haiku.lt voi auttaa tässä.

Haiku.lt tukee kahta tapaa lähettää sähköposteja:

## 1. Valitse sähköpostin lähetystapa

### Gmail (OAuth)

Jos kirjauduit sisään Googlella, Haiku.lt voi lähettää sähköposteja suoraan
Gmail-tililtäsi turvallisen OAuth:n avulla — salasanan jakamista ei tarvita.
Kirjautuessasi sinun tulee myöntää lupa lähettää sähköposteja puolestasi.
Jos et tehnyt tätä aluksi, kirjaudu ulos ja kirjaudu uudelleen sisään.

### SMTP

Voit myös lähettää sähköposteja minkä tahansa SMTP-palvelimen kautta. Tämä toimii
minkä tahansa sähköpostipalveluntarjoajan kanssa ja on ainoa vaihtoehto ei-Gmail-käyttäjille.

Määritä SMTP menemällä [Asetukset → Sähköpostipalveluntarjoajan asetukset](/app/settings/email-provider):

1. Jos käytät Gmail-kirjautumista, valitse **SMTP** lähetystavaksi.
2. Valitse **palveluntarjoajan esiasetus** palvelinasetuksien automaattista täyttämistä varten:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun tai Mukautettu
3. Täytä SMTP-tiedot:
   - **Palvelin** — SMTP-palvelimen osoite (esim. `smtp.gmail.com`)
   - **Portti** — yleensä 587 (STARTTLS) tai 465 (SSL/TLS)
   - **Suojaus** — STARTTLS päivittää salaamattoman yhteyden salatuksi; SSL/TLS on salattu alusta alkaen
   - **Käyttäjätunnus** — sähköpostiosoitteesi
   - **Salasana** — sähköpostisalasanasi tai sovelluskohtainen salasana
   - **Lähettäjän osoite** — vastaanottajille näytettävä lähettäjän osoite (esim. `Yrityksen nimi <sinä@example.com>`)
4. Napsauta **Testaa yhteys** vahvistaaksesi asetukset ennen tallentamista.
5. Napsauta **Tallenna SMTP-asetukset**.

## 2. Sähköpostiasetukset

[Asetuksissa](/app/settings) voit määrittää:

### Sähköpostin aihe

Mukauta sähköpostin aiherivi tarpeisiisi. Voit käyttää näitä muuttujia:
- `{{invoiceNo}}` - laskun numero (esim. INV/001)
- `{{buyer}}` - ostajan nimi
- `{{seller}}` - myyjän nimi
- `{{price}}` - laskun summa valuutalla
- `{{invoiceDate}}` - laskun päivämäärä

### Sähköpostimallit

Valitse näistä malleista:

**Pelkkä teksti** - yksinkertainen tekstimuoto, joka toimii täydellisesti kaikissa sähköpostiohjelmissa.

**Yksinkertainen HTML** - kauniisti muotoiltu HTML-sähköposti käyttäen [MJML](https://mjml.io/)-teknologiaa.

**Logolla** - HTML-malli, jossa yrityksesi logo ylhäällä.

**Logolla ja hinnalla** - näyttää lisäksi laskun summan sähköpostissa.

**Logolla, hinnalla ja lisätiedoilla** - näyttää myös lisätiedot.

**Logolla, hinnalla ja sähköpostihuomautuksella** - sisältää valinnaisen huomautuksen, jonka voit kirjoittaa ennen lähettämistä.

**Rivinimikkeillä** - näyttää täydellisen taulukon laskun rivinimikkeistä (nimi, määrä, yksikköhinta, yhteensä) sekä kokonaissumman.

HTML-mallit käyttävät [MJML](https://mjml.io/)-muotoa, joka varmistaa että sähköpostit näyttävät hyvältä kaikissa sähköpostiohjelmissa. Jos haluat luoda oman mallin tai muokata olemassa olevaa, voit pyytää apua AI:lta - kuvaile miltä haluat sähköpostisi näyttävän, ja AI voi luoda MJML-koodin puolestasi.

### Mallimuuttujat

Kaikissa malleissa voit käyttää näitä arvoja:

**Perustiedot:**
- `{{issuer}}` - laskun luoja
- `{{invoiceNo}}` - laskun numero
- `{{buyer}}` - ostaja
- `{{seller}}` - myyjä
- `{{price}}` - laskun summa
- `{{extra}}` - lisätiedot
- `{{userNote}}` - muistiinpanosi
- `{{emailNote}}` - huomautus sähköpostissa (syötetty lähetettäessä)
- `{{email}}` - ostajan sähköposti

**Päivämäärät:**
- `{{invoiceDate}}` - laskun päivämäärä
- `{{created}}` - laskun luontipäivämäärä (sama kuin invoiceDate)

**Laskun tiedot:**
- `{{seriesName}}` - laskun sarjan nimi (esim. "INV")
- `{{seriesId}}` - numero sarjassa (esim. "001")
- `{{language}}` - laskun kieli ("fi" tai "en")

**Logo:**
- `{{logoUrl}}` - logon URL

**Brändivärit:**
- `{{brandPrimary}}` - ensisijainen väri
- `{{brandSecondary}}` - toissijainen väri
- `{{brandText}}` - tekstin väri
- `{{brandTextSecondary}}` - toissijainen tekstin väri
- `{{brandBackground}}` - taustaväri
- `{{bodyBackground}}` - sivun taustaväri
- `{{backgroundSecondary}}` - toissijainen taustaväri

### Rivinimikkeet

Voit käydä laskun rivinimikkeet läpi Handlebars-komennolla `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Jokainen rivinimike sisältää:
- `{{name}}` - nimikkeen nimi
- `{{amount}}` - määrä
- `{{unit}}` - raaka UN/ECE-yksikkökoodi (esim. `H87`)
- `{{unitName}}` - yksikön pitkä muoto, lokalisoitu (esim. "kappale", "kilogramma")
- `{{unitSymbol}}` - yksikön lyhyt muoto, lokalisoitu (esim. "kpl", "kg")
- `{{unitPrice}}` - muotoiltu hinta per yksikkö (esim. "€10,00")
- `{{formattedPrice}}` - muotoiltu rivitotal — määrä × yksikköhinta (esim. "€30,00")
- `{{vat}}` - ALV-prosentti (jos asetettu)
- `{{vatcode}}` - ALV-koodi (jos asetettu)

### Ehdolliset mallit

Voit käyttää Handlebars-ehtoja näyttääksesi sisältöä vain kun arvo on olemassa:

```
{{#if extra}}
  <mj-text>Lisätiedot: {{extra}}</mj-text>
{{/if}}
```

Tämä on erityisen hyödyllistä kun haluat näyttää lisätietolohkon vain kun se on todella täytetty.

### Brändivärit ja logo

Asetuksissa voit myös:
- Ladata logosi
- Muuttaa brändivärejä

## 3. Laskun lähettäminen

1. Määritä ostajan sähköpostiosoite laskussa
2. Klikkaa "Lähetä lasku" -painiketta
3. Lasku merkitään lukituksi ja lähetetään

Lasku lähetetään Gmail-tililtäsi käyttäen valittua mallia.
