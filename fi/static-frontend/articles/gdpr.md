---
title: 'GDPR - Tietojesi oikeudet'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt on sitoutunut suojelemaan henkilötietojasi ja kunnioittamaan yksityisyysoikeuksiasi yleisen tietosuoja-asetuksen (GDPR) mukaisesti. Tämä sivu selittää oikeutesi ja miten käsittelemme tietojasi.

## Tietojesi oikeudet

GDPR:n mukaan sinulla on seuraavat oikeudet henkilötietoihisi liittyen:

### Oikeus päästä tietoihin

Sinulla on oikeus päästä kaikkiin hallussamme oleviin henkilötietoihisi. Voit viedä tietosi milloin tahansa:

- **Täysi tietokannan vienti**: Lataa koko tietokantasi sisältäen kaikki laskut, asetukset ja lokitiedot tilisi asetuksista.
- **Laskujen vienti**: Vie laskusi CSV-muodossa, suodatettuna päivämäärävälin ja sarjan nimen mukaan.

### Oikeus poistamiseen (oikeus tulla unohdetuksi)

Sinulla on oikeus pyytää henkilötietojesi poistamista. Voit poistaa koko tilisi ja kaikki siihen liittyvät tiedot milloin tahansa tilisi asetuksista. Tämä toimenpide on pysyvä eikä sitä voi perua.

### Oikeus tietojen siirrettävyyteen

Voit viedä tietosi koneluettavissa muodoissa:

- SQLite-tietokantamuoto (täydellinen tietojen vienti)
- CSV-muoto (laskutietojen vienti)

Tämä mahdollistaa tietojesi siirtämisen toiseen palveluun halutessasi.

### Oikeus oikaisuun

Sinulla on oikeus korjata virheelliset tai puutteelliset henkilötiedot. Voit muokata kaikkia tietojasi suoraan sovelluksessa, mukaan lukien:

- Laskujen tiedot
- Ostajan ja myyjän tiedot
- Henkilökohtaiset asetuksesi ja mieltymyksesi

### Oikeus käsittelyn rajoittamiseen

Sinulla on oikeus pyytää henkilötietojesi käsittelyn rajoittamista tietyissä olosuhteissa. Ota yhteyttä käyttäen alla olevaa sähköpostiosoitetta käyttääksesi tätä oikeutta.

### Oikeus vastustaa

Sinulla on oikeus vastustaa henkilötietojesi käsittelyä tiettyihin tarkoituksiin. Koska Haiku.lt käsittelee tietojasi ainoastaan tarjotakseen pyytämäsi laskutuspalvelun, käsittelyn vastustaminen estäisi meitä tarjoamasta palvelua.

## Tietojen säilytys

Tietosi säilytetään **kunnes poistat tilisi**. Emme poista automaattisesti käyttämättömiä tilejä. Sinä hallitset täysin milloin tietosi poistetaan.

Kun poistat tilisi, kaikki tietosi poistetaan pysyvästi järjestelmistämme.

## Rekisterinpitäjä

Haiku.lt:n rekisterinpitäjä on:

**Dalius Dobravolskas**

Yksityisyyteen liittyvissä kysymyksissä tai oikeuksiesi käyttämiseksi, ota yhteyttä:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Palvelimen sijainti

Kaikki Haiku.lt:n palvelimet ja tietojen tallennus sijaitsevat **Euroopan unionissa, erityisesti Saksassa**. Tietosi eivät poistu EU:sta, ellet erikseen valtuuta kolmannen osapuolen integraatioita (katso Alihankkijat alla).

## Käsittelyn oikeusperuste

Käsittelemme henkilötietojasi seuraavien perusteiden mukaisesti:

- **Sopimuksen täyttäminen**: Tarjotaksemme laskutuspalvelun, johon olet rekisteröitynyt
- **Oikeutettu etu**: Palvelun turvallisuuden ylläpitämiseksi, petosten estämiseksi ja palvelun parantamiseksi
- **Suostumus**: Valinnaisille ominaisuuksille kuten Google Drive ja Gmail -integraatiolle

## Alihankkijat

Haiku.lt käyttää seuraavia kolmannen osapuolen palveluita toiminnallisuutemme tarjoamiseksi:

### Google LLC

**Käytetyt palvelut**: OAuth 2.0 -autentikointi, Google Drive API, Gmail API, Google Calendar API

**Jaetut tiedot**: Sähköpostiosoite, nimi, OAuth-tunnukset (vain kun valtuutat Google-integraation)

**Tarkoitus**: Mahdollistaa sinulle:
- **Autentikointi** Google-tililläsi käyttäen OAuth 2.0:aa
- **Google Drive** (scope: `drive.file`): Tallenna lasku-PDF:t Driveesi järjestettyihin kansioihin (Haiku.lt/Laskut/Vuosi). Voimme käyttää vain sovelluksemme luomia tiedostoja, emme muita Drive-tiedostojasi. Tallennamme Drive-tiedostojen ID:t seurataksemme tallennettuja laskuja.
- **Gmail** (scope: `gmail.send`): Lähetä laskulähkeposteja ostajille puolestasi. Emme lue saapuneita postiasi tai olemassa olevia sähköposteja. Lähetetyt sähköpostit näkyvät Gmailin "Lähetetyt"-kansiossa.
- **Google Calendar** (scope: `calendar.readonly`, valinnainen): Lue kalenteritapahtumien otsikot, päivämäärät, ajat ja osallistumistila auttaaksemme laskujen luomisessa. Tämä tieto haetaan väliaikaisesti eikä sitä tallenneta pysyvästi.

**Tietojen säilytys**:
- Drive-tiedostojen ID:t: Tallennettu tietokantaamme kunnes poistat laskun tai katkaiset Google-tilisi yhteyden
- Kalenteritiedot: Ei tallenneta (haetaan vain tarvittaessa)
- Gmail-tiedot: Ei tallenneta (sähköpostit pysyvät Gmail-tilissäsi)
- OAuth-tunnukset: Salattu ja tallennettu kunnes katkaiset tilisi yhteyden

**Tietosuojakäytäntö**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Sijainti**: Yhdysvallat (EU-US Data Privacy Framework -yhteensopivuus)

### Stripe, Inc.

**Käytetyt palvelut**: Tilausten maksunkäsittely

**Jaetut tiedot**: Sähköpostiosoite, maksutiedot (käsitellään suoraan Stripen toimesta)

**Tarkoitus**: Tilausmaksujen käsittely premium-ominaisuuksille

**Tietosuojakäytäntö**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Sijainti**: Yhdysvallat (EU-US Data Privacy Framework -yhteensopivuus)

### Brevo (Sendinblue)

**Käytetyt palvelut**: Transaktionaalisten sähköpostien toimitus

**Jaetut tiedot**: Vastaanottajan sähköpostiosoite, sähköpostin sisältö (taikaliinkin tokenit kirjautumiseen; laskun tiedot lähetettäessä laskuja Brevon kautta)

**Tarkoitus**: Toimittaa autentikointisähköpostit (taikaliinkin kirjautuminen) ja laskusähköpostit ostajille

**Tietojen säilytys**: Brevo voi säilyttää lähetettyjen sähköpostien lokeja rajoitetun ajan heidän käytäntönsä mukaisesti. Emme säilytä sähköpostin sisältöä palvelimillamme enempää kuin sen lähettämiseen tarvitaan.

**Tietosuojakäytäntö**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Sijainti**: Euroopan unioni (Ranska)

## Tietoturva

Ryhdymme asianmukaisiin teknisiin ja organisatorisiin toimenpiteisiin henkilötietojesi suojaamiseksi:

- Arkaluontoisten tietojen salaus (OAuth-tunnukset, päivitystunnukset)
- Turvalliset HTTPS-yhteydet
- HTTP-only, turvalliset autentikointievästeet
- Säännölliset ohjelmistopäivitykset
- Käyttäjäkohtainen tietokannan eristys
- Lokitiedot tilin käytön seurantaan

## Tietoturvaloukkausten ilmoittaminen

Epätodennäköisessä tapauksessa, että tietoturvaloukkaus aiheuttaa riskin oikeuksillesi ja vapaudellesi, ilmoitamme sinulle ja asiaankuuluvalle valvontaviranomaiselle 72 tunnin kuluessa GDPR:n vaatimusten mukaisesti.

## Valvontaviranomainen

Jos sinulla on huolenaiheita siitä, miten käsittelemme henkilötietojasi, sinulla on oikeus tehdä valitus paikalliselle tietosuojavalvontaviranomaiselle.

Suomessa toimiva käyttäjille valvontaviranomainen on:

**Tietosuojavaltuutetun toimisto**
Verkkosivusto: [https://tietosuoja.fi](https://tietosuoja.fi)

## Päivitykset tähän käytäntöön

Saatamme päivittää tätä GDPR-tietosivua ajoittain. Tämän sivun yläosassa oleva "muokattu"-päivämäärä ilmaisee, milloin se on viimeksi päivitetty.

Yleisiä tietosuojatietoja varten, katso [Tietosuojakäytäntö](/fi/privacy).
