---
title: 'Tietosuojakäytäntö'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Tämä tietosuojakäytäntö kuvaa miten Haiku.lt kerää ja käyttää tietoja.

## Keräämämme tiedot

- IP-osoite, päivämäärä ja aika, selaimen tiedot.

- Sähköpostiosoite.

- Tiedot, jotka syötät järjestelmään käyttäessäsi sitä.

## Evästeet ja selaimen tallennus

Käytämme evästeitä ja selaimen tallennustilaa tarjotaksemme olennaisen toiminnallisuuden:

### Evästeet

- **Autentikointievästä (auth_token)**: Turvallinen, HTTP-only-evästä, jota käytetään kirjautumisistuntosi ylläpitoon. Tämä evästä on välttämätön palvelun toimimiselle ja vanhenee noin 2 kuukauden kuluttua. Ilman tätä evästettä et voi käyttää Haiku.lt:tä.

### Selaimen paikallinen tallennus

Tallennamme seuraavat tiedot selaimesi paikalliseen tallennustilaan:

- **Kielivalinta**: Valitsemasi käyttöliittymän kieli tarjotaksemme välitöntä käyttöliittymän renderöintiä.

- **Ilmoitusten hylkääminen**: Tallentaa oletko hylännyt tiettyjä ilmoituksia, jotta niitä ei näytetä toistuvasti.

- **Tilin vaihdon synkronointi**: Väliaikainen tieto (poistetaan 1 sekunnin kuluttua), jota käytetään tilin vaihdon synkronointiin useiden selaimen välilehtien välillä.

### Selaimen istuntojen tallennus

- **Vierailuseuranta**: Vain istunnon aikainen merkintä estääksemme uudelleenohjaussilmukat aloitussivulla. Tämä tieto poistetaan kun suljet selaimesi.

### Ei kolmannen osapuolen seurantaa

Emme käytä analytiikka-, mainos- tai kolmannen osapuolen seurantaevästeitä. Kaikki evästeet ja tallennus ovat ehdottoman välttämättömiä palvelun toimimiselle.

## Kolmannen osapuolen palvelut

- **Google-palvelut**: Integroidumme Google-palveluihin kun yhdistät Google OAuth:n kautta:

  - **Google Drive** (valinnainen): Jos myönnät Google Drive -luvan, käytämme:
    - **Mitä käytämme**: Haiku.lt:n luomat tiedostot Google Drivessasi. Käytämme `drive.file`-scopea, joka tarjoaa pääsyn vain sovelluksemme luomiin tiedostoihin - emme näe tai käytä mitään muita tiedostoja Drivessasi.
    - **Miten käytämme**: Tallentaaksemme lasku-PDF:t Google Driveesi järjestettyyn kansiorakenteeseen (Haiku.lt/Laskut/Vuosi). Kun käytät "Tallenna Driveen" -ominaisuutta, luomme tai päivitämme PDF-tiedostoja.
    - **Miten tallennamme**: Tallennamme Google Drive -tiedoston ID:n tietokantaamme seurataksemme mitä laskuja on tallennettu ja mahdollistaaksemme olemassa olevien tiedostojen päivitykset. Varsinaista PDF-sisältöä ei tallenneta palvelimillemme - se on vain Google Drivessasi.
    - **Miten jaamme**: Google Drive -tiedostojen ID:itä ei koskaan jaeta kolmansille osapuolille, myydä tietovälittäjille tai käytetä mainontaan, markkinointiin, tekoälyn koulutukseen tai mihinkään muuhun tarkoitukseen kuin lasku-PDF:iesi hallintaan Drivessasi.
    - **Miten hallitset**: Voit hallita Drive-lupia [Google-tilisi lupien](https://myaccount.google.com/permissions) kautta. Tiedostot pysyvät Drivessasi hallinnassasi. Voit poistaa ne milloin tahansa. Luvan peruuttaminen estää kykymme luoda uusia tiedostoja tai päivittää olemassa olevia.

  - **Gmail** (valinnainen): Jos myönnät Gmail-luvan, käytämme:
    - **Mitä käytämme**: Luvan lähettää sähköposteja Gmail-tililtäsi. Käytämme `gmail.send`-scopea, joka sallii sähköpostien lähettämisen puolestasi. Emme lue olemassa olevia sähköpostejasi tai saapuneita postiasi.
    - **Miten käytämme**: Lähettääksemme laskulähkeposteja ostajillesi kun käytät "Lähetä lasku" -ominaisuutta. Sähköpostit sisältävät lasku-PDF:n liitteenä ja mahdolliset lisäliitteet (kuten CII XML sähköistä laskutusta varten).
    - **Miten tallennamme**: Emme tallenna sähköpostin sisältöä tai lähetettyjen viestien tietoja. Lähetetyt sähköpostit näkyvät Gmailin "Lähetetyt"-kansiossa hallinnassasi.
    - **Miten jaamme**: Sähköpostin lähetyskykyä ei koskaan jaeta kolmansille osapuolille, myydä tai käytetä mainontaan, markkinointiin, roskapostiin tai mihinkään muuhun tarkoitukseen kuin niiden laskujen lähettämiseen, jotka nimenomaisesti valitset lähetettäväksi.
    - **Miten hallitset**: Voit hallita Gmail-lupia [Google-tilisi lupien](https://myaccount.google.com/permissions) kautta. Lähetetyt sähköpostit pysyvät Gmail-tilissäsi. Luvan peruuttaminen estää kykymme lähettää sähköposteja puolestasi.

  - **Google Calendar** (valinnainen, vain luku): Jos myönnät kalenteriluvan, käytämme:
    - **Mitä käytämme**: Kalenterisi nimet, tapahtumien otsikot, tapahtumien päivämäärät/ajat ja osallistumistila (suodattaaksemme pois hylätyt tapahtumat). Käytämme Google Calendar API -scopea `calendar.readonly`, joka tarjoaa vain luku -oikeuden.
    - **Miten käytämme**: Yksinomaan auttaaksemme sinua luomaan laskuja kalenteritapahtumien perusteella "Luo kalenterista" -ominaisuuden kautta. Tapahtumien otsikoista tulee laskurivien kuvaukset, ja tapahtumien päivämääristä auttavat laskun päivämäärävälin asettamisessa.
    - **Miten tallennamme**: Kalenteritietoja **ei tallenneta pysyvästi** tietokantoihimme. Se haetaan tarpeen mukaan vain kun käytät kalenterilaskuominaisuutta ja on olemassa väliaikaisesti selaimesi muistissa laskun luomisprosessin aikana.
    - **Miten jaamme**: Kalenteritietoja **ei koskaan jaeta** kolmansille osapuolille, **ei koskaan myydä** tietovälittäjille ja **ei koskaan käytetä** mainontaan, markkinointiin, tekoälyn koulutukseen tai mihinkään muuhun tarkoitukseen kuin laskujen luomiseen sinulle.
    - **Miten hallitset**: Voit hallita kalenterilupia itsenäisesti [Google-tilisi lupien](https://myaccount.google.com/permissions) kautta. Luvan peruuttaminen pysäyttää tietojen käytön välittömästi. Voit myös katkaista koko Google-tilisi yhteyden Haiku.lt:n asetusten kautta.

  Kaikki Google OAuth -luvat vaativat nimenomaisen valtuutuksesi. Hallitset mitä lupia myönnät ja voit peruuttaa ne milloin tahansa.

- **Stripe**: Käytämme Stripea premium-tilausten maksunkäsittelyyn. Stripe käsittelee kaikki maksutiedot turvallisesti heidän tietosuojakäytäntönsä mukaisesti. Me saamme vain vahvistuksen onnistuneista maksuista.

- **Brevo (Sendinblue)**: Käytämme Brevoa transaktionaalisten sähköpostien toimittamiseen, mukaan lukien taikaliinkikirjautumissähköpostit ja laskusähköpostit. Brevo vastaanottaa vastaanottajan sähköpostiosoitteen ja sähköpostin sisällön, joka tarvitaan näiden viestien toimittamiseen. Brevo sijaitsee EU:ssa (Ranska). Katso heidän [Tietosuojakäytäntönsä](https://www.brevo.com/legal/privacypolicy/).

## Tietosuoja

Suojataksemme kerättyjä tietoja, ryhdymme seuraaviin toimenpiteisiin:

- Päivitä palvelinohjelmistoja mahdollisimman usein.

- Päivitä Haiku.lt-ohjelmistoa mahdollisimman usein.

- Konfiguroi palvelimet asianmukaisesti.

## Oikeutesi

Yksityiskohtaisia tietoja oikeuksistasi GDPR:n mukaisesti, mukaan lukien oikeus päästä tietoihisi, poistaa ja viedä tietosi, katso [GDPR-sivumme](/fi/gdpr).
