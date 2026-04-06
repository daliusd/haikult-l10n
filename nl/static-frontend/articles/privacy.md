---
title: 'Privacybeleid'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Dit Privacybeleid beschrijft hoe Haiku.lt gegevens verzamelt en gebruikt.

## Gegevens die Wij Verzamelen

- IP-adres, datum en tijd, browserinformatie.

- E-mailadres.

- Gegevens die u invoert in het systeem tijdens het gebruik ervan.

## Cookies en Browseropslag

Wij gebruiken cookies en browseropslag om essentiële functionaliteit te bieden:

### Cookies

- **Authenticatiecookie (auth_token)**: Een veilige, HTTP-only cookie die wordt gebruikt om
  uw inlogsessie te onderhouden. Deze cookie is essentieel voor de werking van de dienst
  en verloopt na ongeveer 2 maanden. Zonder deze cookie
  kunt u Haiku.lt niet gebruiken.

### Browser Local Storage

Wij slaan de volgende gegevens op in de local storage van uw browser:

- **Taalvoorkeur**: Uw geselecteerde interfacetaal (Engels of Litouws)
  om directe UI-weergave te bieden.

- **Melding Afgewezen**: Registreert of u bepaalde
  meldingen heeft afgewezen om te voorkomen dat ze herhaaldelijk worden getoond.

- **Account Wissel Synchronisatie**: Tijdelijke gegevens (verwijderd na 1 seconde) gebruikt om
  het wisselen van accounts tussen meerdere browsertabbladen te synchroniseren.

### Browser Session Storage

- **Bezoek Tracking**: Een sessie-only vlag om redirect loops op de
  landingspagina te voorkomen. Deze gegevens worden verwijderd wanneer u uw browser sluit.

### Geen Tracking van Derden

Wij gebruiken geen analytics, advertenties of trackingcookies van derden.
Alle cookies en opslag zijn strikt noodzakelijk voor de werking van de dienst.

## Diensten van Derden

- **Google Services**: Wij integreren met Google-diensten wanneer u verbinding maakt via Google OAuth:

  - **Google Drive** (optioneel): Als u Google Drive-toestemming geeft, hebben wij toegang tot:
    - **Wat wij benaderen**: Bestanden gemaakt door Haiku.lt in uw Google Drive. Wij gebruiken de `drive.file` scope die alleen toegang biedt tot bestanden die door onze applicatie zijn gemaakt - wij kunnen geen andere bestanden in uw Drive zien of benaderen.
    - **Hoe wij het gebruiken**: Om factuur-PDF's op te slaan in uw Google Drive in een georganiseerde mappenstructuur (Haiku.lt/Invoices/Year). Wanneer u de "Opslaan naar Drive" functie gebruikt, maken of updaten wij PDF-bestanden.
    - **Hoe wij het opslaan**: Wij slaan de Google Drive-bestands-ID op in onze database om bij te houden welke facturen zijn opgeslagen en om updates van bestaande bestanden mogelijk te maken. De daadwerkelijke PDF-inhoud wordt niet op onze servers opgeslagen - deze bestaat alleen in uw Google Drive.
    - **Hoe wij het delen**: Google Drive-bestands-ID's worden nooit gedeeld met derden, nooit verkocht aan datamakelaars en nooit gebruikt voor advertenties, marketing, AI-training of enig ander doel dan het beheren van uw factuur-PDF's in uw Drive.
    - **Hoe u het controleert**: U kunt Drive-toestemmingen beheren via uw [Google Account toestemmingen](https://myaccount.google.com/permissions). Bestanden blijven in uw Drive onder uw controle. U kunt ze op elk moment verwijderen. Het intrekken van toegang stopt onze mogelijkheid om nieuwe bestanden te maken of bestaande bij te werken.

  - **Gmail** (optioneel): Als u Gmail-toestemming geeft, hebben wij toegang tot:
    - **Wat wij benaderen**: Toestemming om e-mails te versturen via uw Gmail-account. Wij gebruiken de `gmail.send` scope die het versturen van e-mails namens u mogelijk maakt. Wij lezen uw bestaande e-mails niet en hebben geen toegang tot uw inbox.
    - **Hoe wij het gebruiken**: Om factuuremails naar uw kopers te versturen wanneer u de "Factuur Versturen" functie gebruikt. E-mails bevatten de factuur-PDF als bijlage en optionele aanvullende bijlagen (zoals CII XML voor e-facturering).
    - **Hoe wij het opslaan**: Wij slaan geen e-mailinhoud of verzonden berichtgegevens op. Verzonden e-mails verschijnen in uw Gmail "Verzonden" map onder uw controle.
    - **Hoe wij het delen**: E-mailverzendmogelijkheid wordt nooit gedeeld met derden, nooit verkocht en nooit gebruikt voor advertenties, marketing, spam of enig ander doel dan het versturen van facturen die u expliciet kiest te versturen.
    - **Hoe u het controleert**: U kunt Gmail-toestemmingen beheren via uw [Google Account toestemmingen](https://myaccount.google.com/permissions). Verzonden e-mails blijven in uw Gmail-account. Het intrekken van toegang stopt onze mogelijkheid om e-mails namens u te versturen.

  - **Google Agenda** (optioneel, alleen-lezen): Als u agendatoestemming geeft, hebben wij toegang tot:
    - **Wat wij benaderen**: Uw agendanamen, gebeurtenistijden, gebeurtenisdatums/tijden en aanwezigheidsstatus (om afgewezen gebeurtenissen te filteren). Wij gebruiken de Google Agenda API scope `calendar.readonly` die alleen-lezen toegang biedt.
    - **Hoe wij het gebruiken**: Uitsluitend om u te helpen facturen te maken op basis van agenda-gebeurtenissen via de "Aanmaken vanuit Agenda" functie. Gebeurtenistijden worden factuur regelitem beschrijvingen, en gebeurtenisdatums helpen bij het instellen van factuurdatumbereiken.
    - **Hoe wij het opslaan**: Agendagegevens worden **niet permanent opgeslagen** in onze databases. Ze worden on-demand opgehaald alleen wanneer u de agenda-factuurfunctie gebruikt en bestaan tijdelijk in uw browsergeheugen tijdens het aanmaakproces van de factuur.
    - **Hoe wij het delen**: Agendagegevens worden **nooit gedeeld** met derden, **nooit verkocht** aan datamakelaars, en **nooit gebruikt** voor advertenties, marketing, AI-training of enig ander doel dan het aanmaken van facturen voor u.
    - **Hoe u het controleert**: U kunt agendatoestemmingen onafhankelijk beheren via uw [Google Account toestemmingen](https://myaccount.google.com/permissions). Het intrekken van toegang stopt de gegevenstoegang onmiddellijk. U kunt ook uw volledige Google-account loskoppelen via Haiku.lt-instellingen.

  Alle Google OAuth-toestemmingen vereisen uw expliciete autorisatie. U bepaalt welke toestemmingen u geeft en u kunt ze op elk moment intrekken.

- **Stripe**: Wij gebruiken Stripe voor de betalingsverwerking van premium abonnementen.
  Stripe verwerkt alle betalingsinformatie veilig volgens hun privacybeleid. Wij ontvangen alleen bevestiging van succesvolle betalingen.

- **Brevo (Sendinblue)**: Wij gebruiken Brevo voor het bezorgen van transactionele e-mails, inclusief magische link-inlog e-mails en factuur-e-mails. Brevo ontvangt het e-mailadres van de ontvanger en de e-mailinhoud die nodig is om deze berichten te bezorgen. Brevo bevindt zich in de EU (Frankrijk). Zie hun [Privacybeleid](https://www.brevo.com/legal/privacypolicy/).

## Gegevensbescherming

Om verzamelde gegevens te beschermen, nemen wij de volgende maatregelen:

- Update serversoftware zo vaak mogelijk.

- Update Haiku.lt software zo vaak mogelijk.

- Configureer servers correct.

## Uw Rechten

Voor gedetailleerde informatie over uw gegevensrechten onder de AVG, inclusief het recht
op toegang, verwijdering en export van uw gegevens, zie onze [AVG-pagina](/nl/gdpr).
