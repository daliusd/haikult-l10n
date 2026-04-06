---
title: 'Hvordan lage fakturaer fra Google Calendar-hendelser (Trinn-for-trinn-guide)'
date: '2026-01-08'
modified: '2026-01-08'
showDate: true
---

Hvis du er konsulent, coach, terapeut eller en hvilken som helst serviceprofesjonell som fakturerer per time, kjenner du den månedlige rutinen: åpne kalenderen din, tell sesjoner for hver klient, deretter manuelt opprette fakturaer én om gangen. Det er kjedelig, tidkrevende og utsatt for feil.

Hva om kalenderen din ganske enkelt kunne bli fakturaene dine?

Det er nøyaktig det Haiku.lts "Opprett fra kalender"-funksjon gjør. I denne guiden vil jeg vise deg hvordan du kan transformere Google Calendar-avtalene dine til profesjonelle fakturaer på minutter, ikke timer.

## Hvem drar nytte av denne funksjonen?

Denne funksjonen er perfekt for alle som fakturerer per avtale eller sesjon:

- **Konsulenter** - Strategisesjoner, rådgivningssamtaler, prosjektmøter
- **Coacher** - Livscoaching, forretningscoaching, karriererådgivning
- **Terapeuter og psykologer** - Individuelle terapisesjoner, gruppesesjoner
- **Veiledere og lærere** - Språkleksjoner, musikkleksjoner, akademisk veiledning
- **Personlige trenere** - En-til-en-treningsøkter, gruppetimer
- **Danselærere** - Private leksjoner, gruppetimer
- **Helsepersonell** - Fysioterapi, massasje, alternativ medisin
- **Juridiske rådgivere** - Konsulenttimer
- **Ernæringsfysiologer og dietetikere** - Klientkonsultasjoner

Hvis du planlegger avtaler i Google Calendar og trenger å fakturere for disse sesjonene, vil denne funksjonen spare deg for timer hver måned.

## Problemet: Manuell fakturaopprettelse

La oss møte Sofia, en psykoterapeut i Amsterdam med en travel praksis. Hun ser omtrent 30 klienter per uke, og tilbyr både individuell terapi og parterapi til forskjellige priser.

Hver måned står Sofia overfor den samme kjedelige oppgaven: gjennomgå kalenderen sin, telle sesjoner for hver klient, og opprette 25-30 fakturaer manuelt. Mellom å sjekke avtalehistorikker, beregne antall og legge inn data, tar det henne nesten 2 timer.

Og hun er ikke alene. Enten du er en yogainstruktør i Roma, en forretningscoach i Paris, eller en pianolærer i Wien, hvis du fakturerer per avtale, har du opplevd denne frustrasjonen.

## Løsningen: Kalender-til-faktura-automatisering

Haiku.lts kalenderintegrasjon konverterer automatisk Google Calendar-hendelsene dine til fakturaer. Her er magien:

- **Hver unike hendelsestittel blir en klientfaktura**
- **Antall avtaler blir antallet**
- **Alle faktureringsdataene dine er forhåndsutfylt fra tidligere fakturaer**
- **Du gjennomgår og tilpasser før du oppretter noe**

Det som pleide å ta Sofia 2 timer tar nå 10 minutter.

## Forutsetninger: Hva du trenger

Før du starter, sørg for at du har:

1. **En Haiku.lt-konto** - Registrer deg på haiku.lt (gratis for opptil 500 fakturaer)
2. **Google Calendar med avtalene dine** - Bruk klientnavn som hendelsestitler for best resultat
3. **Google Calendar-tillatelse** - Gitt når du logger inn med Google

Viktig: Haiku.lt lagrer ikke kalenderdata. Den henter bare hendelsestitler og datoer midlertidig for å opprette fakturaer. Kalenderen din forblir privat.

## Trinn 1: Få tilgang til funksjonen

Etter å ha logget inn på Haiku.lt vil du se dashbordet ditt. Se etter "Opprett fra kalender"-knappen. Klikk på den for å starte den 4-trinns veiviseren.

Knappens verktøytips forklarer: "Opprett flere fakturaer fra Google Calendar-hendelser. Hvert unike hendelsenavn blir en kjøper, og antall forekomster blir antallet."

## Trinn 2: Konfigurer kalenderimporten din

Det første skjermbildet ber deg konfigurere hvordan fakturaer vil bli opprettet. La oss gå gjennom hvert felt:

### Velg kalender

Velg hvilken Google Calendar som inneholder dine fakturerbare avtaler. Hvis du har flere kalendere, velg den der du sporer klientsesjoner. Din primære kalender vil være merket som "(Primær)".

**Pro-tips:** Vurder å opprette en dedikert "Fakturerbare sesjoner"-kalender atskilt fra dine personlige avtaler. Dette gjør fakturering renere og raskere.

### Datointervall

Angi perioden du ønsker å opprette fakturaer for. Systemet går som standard til den nåværende måneden (første til siste dag), men du kan velge hvilket som helst datointervall.

Når du justerer datoene, teller systemet hvor mange hendelser som finnes i den perioden og viser antallet. Hvis du ser "Ingen hendelser funnet", dobbeltsjekk kalendervalget og datointervallet.

**Vanlig mønster:** De fleste profesjonelle fakturerer månedlig, så å velge forrige måned i starten av hver ny måned fungerer perfekt.

### Fakturaserie

Legg inn et serienavn for disse fakturaene (for eksempel "CONSULTING", "THERAPY", "LESSONS"). Hvis du har opprettet fakturaer før, foreslår systemet dine nylige serienavn.

Fakturaserier hjelper deg med å organisere fakturaer etter type eller år. For eksempel "2026-COACHING" eller enkelt "SESSIONS".

### Selgerinformasjon

Legg inn bedriftsdetaljene dine - navnet ditt eller firmanavnet, adressen, org.nr., og annen informasjon du ønsker på fakturaen. Hvis du har opprettet fakturaer i denne serien før, fylles dette feltet automatisk ut med din tidligere informasjon.

### Faktura utstedt av

Legg inn navnet på den som utsteder fakturaen (vanligvis ditt navn). Som selgerfeltet fylles dette automatisk ut fra dine tidligere fakturaer.

### Linjeoppføringskonfigurasjon

Nå konfigurer hva som vises på hver faktura som den fakturerbare tjenesten:

**Linjeoppføringsnavn** - Hva du fakturerer for (f.eks. "Terapisesjon", "Konsulenttime", "Pianoleksjon"). Systemet husker dine tidligere linjeoppføringer og foreslår dem.

**Standardpris (per enhet)** - Din standardrate per sesjon. Legg inn beløpet i din valuta (euro for eurosonesbrukere).

**MVA %** - Hvis du er MVA-registrert virksomhet, legg inn din MVA-prosent. Dette feltet vises bare hvis du har aktivert MVA i innstillingene dine.

**Enhet** - Måleenheten for tjenesten din. Standarden er "stykker" som fungerer for mest sesjonsbasert fakturering. Du kan også velge "timer" eller andre enheter fra rullegardinmenyen.

**Pro-tips:** Når du begynner å skrive i linjeoppføringsnavn, hvis du har brukt den oppføringen før, fyller systemet automatisk ut prisen, MVA-en og enheten basert på historikken din. Dette sikrer konsistens.

Når alle obligatoriske felt er fylt ut og systemet finner minst én kalenderhendelse, blir "Neste"-knappen aktiv.

## Trinn 3: Gjennomgå og rediger fakturaene dine

Dette er der magien skjer. Systemet har gruppert kalenderhendelsene dine etter tittel og forberedt utkast til fakturaer. Her er hva du vil se:

### Hvordan hendelser blir fakturaer

Systemet analyserer kalenderhendelsene dine og bruker denne logikken:

- **Grupperer hendelser etter tittel** - Alle hendelser med samme navn grupperes sammen
- **Hver unike tittel blir én faktura** - "Marie Dubois"-avtaler blir én faktura for Marie
- **Teller forekomster** - Hvis "Marie Dubois" vises 4 ganger, er antallet 4
- **Ekskluderer automatisk** - Hendelser uten titler og avtaler du har avslått hoppes over

### Smart forhåndsutfylling

For hvert klientnavn ser Haiku.lt på fakturahistorikken din og fyller automatisk ut:

- E-postadresse
- Land
- Org.nr.
- Foretrukket fakturaspråk
- Siste pris du fakturerte dem for denne spesifikke tjenesten

Dette er utrolig kraftfullt. Hvis du fakturerte Marie €80 per sesjon forrige måned og Pierre €100 per sesjon (kanskje han er en bedriftsklient), husker systemet og setter disse prisene automatisk.

### Gjennomgangstabellen

Du vil se en tabell med én rad per klient, som viser:

- **Kjøpernavn** - Hendelsestittel fra kalenderen din (redigerbar)
- **Antall** - Antall avtaler (redigerbart)
- **E-post** - Klientens e-post hvis tidligere brukt (redigerbar)
- **Land** - Klientens land (redigerbart)
- **Org.nr.** - Klientens org.nr. hvis kjent (redigerbart)
- **Fakturaspråk** - Hvilket språk for PDF-en, med 39 alternativer inkludert engelsk, tysk, fransk, spansk, italiensk, nederlandsk, portugisisk og mer (redigerbart)
- **Pris (per enhet)** - Prisen for denne spesifikke klienten (redigerbar)

Alt er redigerbart. Du kan:

- Justere antall hvis du telte annerledes
- Oppdatere e-postadresser
- Endre priser for spesifikke klienter
- Angi forskjellige fakturaspråk for internasjonale klienter
- Fjerne klienter du ikke ønsker å fakturere ennå
- Legge til ekstra klienter manuelt med "+ Legg til kjøper"-knappen

**Eksempelscenario:** Sofia ser disse grupperte avtalene:

- Marie Dubois: 4 sesjoner
- Jan de Vries: 4 sesjoner
- Anna Schmidt: 5 sesjoner
- Kombinert parter sesjon (Marie & Jan): 2 sesjoner

Hun kan justere "Kombinert parter sesjon" for å dele mellom de to klientene, eller la den være som en separat faktura. Fleksibiliteten er din.

Hvis du oppretter mer enn 50 fakturaer, viser systemet en advarsel om at det kan ta flere minutter. For de fleste brukere er imidlertid batch-størrelser på 10-30 fakturaer som fullføres veldig raskt.

Når alt ser riktig ut, klikk "Opprett X faktura(er)" for å fortsette.

## Trinn 4: Opprette fakturaer

Systemet oppretter nå fakturaene dine én om gangen. Du vil se en fremdriftsindikator som viser "Oppretter faktura X av Y..." mens den jobber gjennom listen din.

Bak kulissene gjør systemet:

- Oppretter hver faktura med et automatisk økende nummer
- Genererer en profesjonell PDF
- Bruker PDF-stilpreferansene dine (du kan velge fra 5 stiler i innstillingene dine)
- Kjører eventuelle automatiseringsregler du har konfigurert
- Sjekker kontogrensene dine (gratiskontoer: 500 fakturaer totalt, Pro: ubegrenset)

For de fleste batcher fullføres dette på under 2 minutter. Større batcher kan ta lenger tid, men systemet fortsetter å jobbe - du kan vente eller komme tilbake senere.

Hvis du er på gratisplanen og nærmer deg 500 fakturabegrensningen, vil systemet varsle deg før du oppretter fakturaer som vil overstige grensen din.

## Trinn 5: Gjennomgå resultater

Vellykket! Det siste skjermbildet viser deg hva som ble opprettet:

Sammendragsmerket viser: "X vellykket, Y mislyktes av Z totalt"

### Vellykkede opprettede fakturaer

Du vil se en tabell over alle opprettede fakturaer med:

- Serie og nummer (f.eks. "THERAPY-045")
- Kjøpernavn
- "Vis"-lenke for å se fakturadetaljene

### Kunne ikke opprette (hvis noen)

Hvis noen fakturaer ikke kunne opprettes (kanskje på grunn av valideringsfeil eller grense nådd), vises de her med feilmeldinger slik at du kan forstå hva som gikk galt.

### Neste trinn

Fra dette skjermbildet kan du:

- **Tilbake til dashboard** - Gå tilbake til hovedfakturalisten din
- **Opprett mer fra kalender** - Start veiviseren igjen for et annet datointervall
- **Bruk fleredigering for å sende/lagre** - Dette er kraftfullt! Det tar deg til fleredigeringsveiviseren der du kan:
  - Sende alle fakturaer via Gmail i én batch
  - Lagre alle PDF-er til Google Drive samtidig
  - Låse alle fakturaer etter sending
  - Merke dem som betalt når betalinger kommer

## Eksempel på arbeidsflyt fra virkeligheten

La oss se hvordan Luca, en forretningscoach i Milano, bruker denne funksjonen månedlig:

### Lucas oppsett

- **Google Calendar:** "Klientcoaching"-kalender atskilt fra personlig kalender
- **Hendelsesnavn:** Klientnavn som hendelsestittel (f.eks. "Startup Italia", "Marco Rossi")
- **Faktureringssyklus:** Første uke av hver måned for forrige måned
- **Priser:** Standard €120/time, noen VIP-klienter på €150/time

### Lucas månedlige prosess

**Dag 1 i ny måned:**

1. Åpner Haiku.lt, klikker "Opprett fra kalender"
2. Velger "Klientcoaching"-kalender
3. Angir datointervall: Forrige måned (f.eks. desember 1-31)
4. Konfigurerer:
   - Serie: "2026-COACHING"
   - Linjeoppføring: "Forretningscoachingsesjon"
   - Standardpris: €120
   - Enhet: timer
5. Klikker "Neste"

**Gjennomgangsskjerm:**

6. Ser 18 fakturaer for 10 forskjellige klienter
7. De fleste klienter har riktig €120-rate (automatisk utfylt fra historikk)
8. Justerer 2 VIP-klienter til €150 (systemet husket dette fra forrige måned, men han dobbeltsjekker)
9. Endrer fakturaspråk:
   - Italiensk for lokale klienter
   - Engelsk for internasjonale startup-klienter
10. Fjerner en testhendelse som var i kalenderen hans
11. Klikker "Opprett 17 fakturaer"

**Resultater:**

12. Alle 17 fakturaer opprettet vellykket på omtrent 90 sekunder
13. Klikker "Bruk fleredigering for å sende/lagre"
14. Velger alle fakturaer, sender dem via Gmail med sin tilpassede mal
15. Lagrer alle PDF-er til sin "2026 Fakturaer"-mappe i Google Drive

**Total tid:** 8 minutter fra start til slutt

**Tidligere manuell prosess:** Ville ha tatt 90-120 minutter

**Månedlig tidsbesparelse:** 82-112 minutter (omtrent 17 timer per år!)

## Pro-tips og beste praksis

### Kalenderorganisering

**Bruk konsekvent hendelsesnavn:** Sørg for at hver klients hendelser bruker nøyaktig samme navn. "Marie Dubois" og "marie dubois" behandles som forskjellige klienter. Velg en navnekonvensjon og hold deg til den.

**Opprett en dedikert fakturerbar kalender:** I stedet for å blande personlige og fakturerbare hendelser, opprett en separat Google Calendar for klientsesjoner. Dette gjør funksjonen renere og raskere å bruke.

**Avslå hendelser du ikke vil fakturere:** Hvis du har en pro bono-sesjon eller et møte som ikke skal faktureres, avslå det i Google Calendar. Systemet ekskluderer automatisk hendelser du har avslått.

**Bruk kalenderfarger:** Fargelag forskjellige typer sesjoner eller klientkategorier i Google Calendar. Selv om dette ikke påvirker fakturering, hjelper det deg med å visuelt organisere timeplanen din.

### Prisstrategier

**La systemet huske klientspesifikke priser:** Systemet lagrer siste pris du brukte for hver klient og linjeoppføringskombinasjon. Hvis du har trinnpriser (standardklienter på €80, premium på €100), etter første måned fylles disse prisene automatisk ut riktig.

**Angi standardpris for nye klienter:** I konfigurasjonsstrinnet gjelder standardprisen din for enhver klient som ikke har en historikk. Sett den til din mest vanlige pris.

**Gjennomgå før opprettelse:** Sjekk alltid gjennomgangstabellen før du klikker opprett. Det er din sjanse til å fange opp eventuelle planleggingsuregelretninger eller bruke spesialrabatter.

### Batchoperasjoner

Etter å ha opprettet kalenderfakturaer, er fleredigeringsveiviseren din beste venn:

**Send alle samtidig:** Velg alle nylig opprettede fakturaer og send dem via Gmail i én handling. Du kan velge forskjellige e-postmaler og tilpasse meldingen.

**Lagre til Google Drive:** Batch-lagre alle PDF-er til en spesifikk mappe i din Google Drive for journalføring.

**Lås fakturaer:** Etter sending, lås alle fakturaer samtidig for å forhindre utilsiktet redigering.

**Spor betalinger:** Når betalinger kommer, bruk fleredigering for å merke flere fakturaer som betalt.

### Flerspråklige hensyn

Hvis du jobber med internasjonale klienter over hele Europa:

- **Angi språk per klient:** I gjennomgangstrinnet kan du angi hver faktura til et annet språk
- **39 språk støttet:** Alle EU-språk pluss norsk, serbisk, ukrainsk, tyrkisk og mer
- **Språk huskes:** Når du angir en klients foretrukne språk, husker systemet for neste gang

Eksempel: Elena, en yogainstruktør i Barcelona, underviser både lokale og utlendinger. Hennes spanske klienter får fakturaer på spansk (Español), hennes engelske studenter får engelske fakturaer, og hennes tyske klienter får tyske (Deutsch) fakturaer. Systemet husker hver persons preferanse.

### Unngå vanlige feil

**Sjekk hendelsestitler før start:** Gjennomgå kalenderen din først. Hvis du ser inkonsistent navnsetting (noen hendelser sier "Klient: John" og andre sier "John Smith"), rydd opp i dem først for renere gruppering.

**Gjennomgå antall:** Før du klikker opprett, verifiser at antallene gir mening. Hvis en klient viser 12 sesjoner, men du vet de bare hadde 4, sjekk kalenderen din for duplikater eller feilaktig titulerte hendelser.

**Ikke glem e-postadresser:** Selv om det er valgfritt, sparer det tid senere når du ønsker å sende fakturaer å ha e-postadresser i gjennomgangstrinnet. Legg til eventuelle manglende e-poster under gjennomgang.

**Bruk meningsfulle serienavn:** I stedet for "2026-1", bruk beskrivende serier som "2026-COACHING" eller "JAN-THERAPY". Fremtidig-du vil sette pris på klar organisering.

## Ofte stilte spørsmål

**Sp: Lagrer Haiku.lt kalenderdata mine?**

S: Nei. Kalenderdata hentes midlertidig bare når du bruker denne funksjonen. Bare hendelsestitler og datoer leses for å beregne antall. Kalenderinnholdet ditt lagres aldri permanent, og Haiku.lt kan ikke få tilgang til kalenderdata med mindre du aktivt bruker denne funksjonen.

**Sp: Hva hvis jeg har tilbakevendende hendelser i kalenderen min?**

S: Perfekt! Tilbakevendende hendelser utvides automatisk til individuelle forekomster. Hvis du har "Marie Dubois - Ukentlig sesjon" som gjentas hver tirsdag, telles hver forekomst separat. Så 4 tirsdager = antall på 4.

**Sp: Kan jeg ekskludere visse hendelser uten å slette dem fra kalenderen min?**

S: Ja, to måter: (1) Avslå hendelsen i Google Calendar - avslåtte hendelser ekskluderes automatisk, eller (2) Fjern bare den klienten fra gjennomgangstabellen før du klikker opprett.

**Sp: Hva hvis jeg har mer enn 50 klienter på én måned?**

S: Funksjonen fungerer fint, selv om du vil se en advarsel om at opprettelse kan ta noen minutter. Hvis du har dette volumet regelmessig, vurder å oppgradere til Pro (€5/måned) for ubegrensede fakturaer. Gratisplanen inkluderer 500 fakturaer totalt, som kan gå tom raskt med høyt volum.

**Sp: Kan jeg bruke forskjellige priser for forskjellige klienter?**

S: Absolutt! Dette er en av de beste funksjonene. I gjennomgangstrinnet er hver klients pris redigerbar. Systemet husker hva du fakturerte dem sist gang, så hvis du har trinnpriser, fylles det automatisk riktig ut etter første måned.

**Sp: Hva med heldagshendelser?**

S: De er inkludert og teller som én forekomst hver. Systemet behandler heldagshendelser det samme som tidssatte hendelser for faktureringsformål.

**Sp: Kalenderen min har avtaler i to forskjellige kategorier (individuell og gruppesesjoner). Kan jeg håndtere begge?**

S: Du kan kjøre veiviseren to ganger - én gang for hver linjeoppføringstype. Først opprett fakturaer for "Individuell terapisesjon" til én pris, kjør den deretter igjen for "Gruppeterapisesjon" til en annen pris. Eller du kan justere manuelt i gjennomgangstrinnet.

**Sp: Hva hvis jeg gjorde en feil og vil slette fakturaene?**

S: Ikke noe problem. Du kan slette fakturaer individuelt eller bruke fleredigeringsveiviseren for å velge og slette flere fakturaer samtidig. Bare sørg for at du ikke har sendt dem ennå, siden sletting av sendte fakturaer kan forvirre klienter.

## Utover kalenderfakturaer: Andre Haiku.lt-funksjoner

Når fakturaene dine er opprettet, utforsk disse funksjonene:

**Fleredigeringsveiviser** - Batchoperasjoner for sending, låsing, merking som betalt og mer. Essensielt etter å ha opprettet kalenderfakturaer.

**Tilpassede e-postmaler** - Design vakre faktura-e-poster med logoen din og merkefarger ved hjelp av MJML-maler, eller velg fra 5 innebygde maler.

**Google Drive-integrasjon** - Lagre automatisk faktura-PDF-er til Google Drive med ett klikk. Hold organiserte mapper etter måned eller klient.

**JavaScript-automatisering** - For kraftbrukere: skriv JavaScript-programmer for å automatisk fylle ut "Tilleggsinformasjon"-feltet med betalingsbetingelser, forfallsdatoer eller betinget innhold.

**39-språkstøtte** - Opprett fakturaer på hvilket som helst europeisk språk pluss mange andre. Perfekt for internasjonalt arbeid.

**Flervvalutastøtte** - Fakturer i hvilken som helst av 150+ valutaer, med riktig formatering og symboler.

**Statistikk og rapportering** - Spor inntekt etter klient, sammenlign perioder, analyser betalingsmønstre, og eksporter til CSV for regnskapsføreren din.

## Konklusjon: Spar tid, fakturer mer

Hvis du fakturerer per avtale, er kalender-til-faktura-funksjonen en game-changer. Det som pleide å ta timer tar nå minutter, og risikoen for underfakturering (glemme å telle en sesjon) eller overfakturering (dobbelttelle) forsvinner nesten.

Enten du er en terapeut i Brussel, en coach i Dublin, eller en danselærer i Lisboa, inneholder kalenderen din allerede faktureringsdataene dine. Hvorfor legge dem inn to ganger?

### Klar til å prøve det?

**For eksisterende brukere:** Logg inn på Haiku.lt og klikk "Opprett fra kalender" på dashbordet ditt. Hvis du ikke har gitt kalendertillatelse ennå, vil du bli bedt om å re-autentisere.

**Nye brukere:** Registrer deg gratis på haiku.lt (ingen kredittkort påkrevd). Du får 500 fakturaer på gratisplanen, som er nok til å teste denne funksjonen og se tidsbesparelsen selv.

**Spørsmål?** E-post support på dalius.dobravolskas@gmail.com

Neste gang du står overfor den månedlige faktureringsoppgaven, husk: kalenderen din er allerede ferdig. Bare konverter den til fakturaer og kom tilbake til det du er best på - å betjene kundene dine.

---

**Flere nyttige guider:**

- [Hvordan sende profesjonelle fakturaer fra din Gmail-konto](/nb/gmail-invoice-sending)
- [Fakturastyring for frilansere](/nb/invoice-management)
- [Flerspråklig fakturering over hele Europa](/nb/help)
