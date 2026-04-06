---
title: 'Sąskaitų faktūrų siuntimas'
date: '2021-04-15'
modified: '2026-03-28'
---

Sukūrus sąskaitą faktūrą ją reikia kažkaip įteikti pirkėjui.
Vienas iš būdų yra išsiųsti PDF failą el. paštu ir „Haiku.lt”
čia gali padėti.

„Haiku.lt” palaiko du el. pašto siuntimo būdus:

## 1. Pasirinkite el. pašto siuntimo būdą

### Gmail (OAuth)

Jei prisijungiate per Google, „Haiku.lt” gali siųsti laiškus tiesiogiai
iš jūsų Gmail paskyros naudodamas saugų OAuth – nereikia dalintis slaptažodžiu.
Prisijungdami turite leisti siųsti laiškus už jus.
Jeigu to nepadarėte, atsijunkite ir prisijunkite iš naujo.

### SMTP

Taip pat galite siųsti laiškus per bet kurį SMTP serverį. Tai veikia su
bet kuriu el. pašto tiekėju ir yra vienintelė galimybė ne Gmail naudotojams.

Norėdami sukonfigūruoti SMTP, eikite į [Nustatymai → El. pašto tiekėjo nustatymai](/app/settings/email-provider):

1. Jei naudojate Gmail prisijungimą, pasirinkite **SMTP** kaip siuntimo būdą.
2. Pasirinkite **tiekėjo šabloną**, kad automatiškai užpildytų serverio nustatymus:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun arba Pasirinktinis
3. Įveskite SMTP duomenis:
   - **Serveris** — SMTP serverio adresas (pvz., `smtp.gmail.com`)
   - **Prievadas** — paprastai 587 (STARTTLS) arba 465 (SSL/TLS)
   - **Saugumas** — STARTTLS prijungia paprastą ryšį prie šifruoto; SSL/TLS yra šifruotas nuo pat pradžių
   - **Naudotojo vardas** — jūsų el. pašto adresas
   - **Slaptažodis** — jūsų el. pašto slaptažodis arba programai skirtas slaptažodis
   - **Siuntėjo adresas** — siuntėjo adresas, matomas gavėjams (pvz., `Įmonės pavadinimas <jūs@example.com>`)
4. Spustelėkite **Testuoti ryšį**, kad patikrintumėte nustatymus prieš išsaugodami.
5. Spustelėkite **Išsaugoti SMTP nustatymus**.

## 2. El. pašto nustatymai

[Nustatymuose](/app/settings) galite konfigūruoti:

### Laiško tema

Keiskite laiško temą pagal savo poreikius. Galite naudoti šias reikšmes:
- `{{invoiceNo}}` - sąskaitos faktūros numeris (pvz., SF/001)
- `{{buyer}}` - pirkėjo pavadinimas
- `{{seller}}` - pardavėjo pavadinimas
- `{{price}}` - sąskaitos suma su valiuta
- `{{invoiceDate}}` - sąskaitos data

### El. pašto šablonai

Pasirinkite vieną iš šių šablonų:

**Paprastas tekstas** - paprastas teksto formatas, puikiai veiks visuose el. pašto klientuose.

**Paprastas HTML** - gražiai suformatuotas HTML laiškas naudojant [MJML](https://mjml.io/) technologiją.

**Su logotipu** - HTML šablonas su jūsų įmonės logotipu viršuje.

**Su logotipu ir kaina** - papildomas sąskaitos sumos rodymas laiške.

**Su logotipu, kaina ir papildoma informacija** - papildomas papildomos informacijos rodymas.

**Su logotipu, kaina ir el. pašto pastaba** - apima neprivalomą pastabą, kurią galite įvesti prieš siunčiant.

**Su eilutės elementais** - rodo pilną sąskaitos faktūros eilučių lentelę (pavadinimas, kiekis, vieneto kaina, suma) kartu su bendra suma.

HTML šablonai naudoja [MJML](https://mjml.io/) formatą, kuris užtikrina, kad el. laiškai atrodytų puikiai visuose el. pašto klientuose. Jei norite sukurti savo šabloną ar modifikuoti esamą, galite paprašyti AI pagalbos - tiesiog aprašykite, kaip norite, kad atrodytų jūsų laiškas, ir AI gali sugeneruoti MJML kodą.

### Šablonų kintamieji

Visuose šablonuose galite naudoti šias reikšmes:

**Pagrindinė informacija:**
- `{{issuer}}` - žmogus, kuris išrašė SF
- `{{invoiceNo}}` - SF numeris
- `{{buyer}}` - pirkėjas
- `{{seller}}` - pardavėjas
- `{{price}}` - sąskaitos suma
- `{{extra}}` - papildoma informacija
- `{{userNote}}` - jūsų pastaba
- `{{emailNote}}` - pastaba el. pašto laiške (įvedama siuntimo metu)
- `{{email}}` - pirkėjo el. paštas

**Datos:**
- `{{invoiceDate}}` - sąskaitos data
- `{{created}}` - sąskaitos sukūrimo data (tas pats kaip invoiceDate)

**Sąskaitos detalės:**
- `{{seriesName}}` - sąskaitos serijos pavadinimas (pvz., "SF")
- `{{seriesId}}` - sąskaitos numeris serijoje (pvz., "001")
- `{{language}}` - sąskaitos kalba ("lt" arba "en")

**Logotipas:**
- `{{logoUrl}}` - logotipo URL adresas

**Prekės ženklo spalvos:**
- `{{brandPrimary}}` - pagrindinė spalva
- `{{brandSecondary}}` - antraeilė spalva
- `{{brandText}}` - teksto spalva
- `{{brandTextSecondary}}` - antraeilė teksto spalva
- `{{brandBackground}}` - fono spalva
- `{{bodyBackground}}` - puslapio fono spalva
- `{{backgroundSecondary}}` - antraeilė fono spalva

### Eilutės elementai

Galite pridėti sąskaitos faktūros eilutės elementus naudodami Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Kiekvienas eilutės elementas turi:
- `{{name}}` - prekės pavadinimas
- `{{amount}}` - kiekis
- `{{unit}}` - neapdorotas UN/ECE vieneto kodas (pvz., `H87`)
- `{{unitName}}` - vieneto forma, lokalizuota (pvz., "vienetas", "kilogramas")
- `{{unitSymbol}}` - trumpa vieneto forma, lokalizuota (pvz., "vnt", "kg")
- `{{unitPrice}}` - suformatuota kaina už vienetą (pvz., "€10,00")
- `{{formattedPrice}}` - suformatuota eilutės suma — kiekis × vieneto kaina (pvz., "€30,00")
- `{{vat}}` - PVM procentas (jei nustatytas)
- `{{vatcode}}` - PVM kodas (jei nustatytas)

### Sąlyginiai šablonai

Galite naudoti Handlebars sąlygas, kad rodytumėte turinį tik tada, kai yra reikšmė:

```
{{#if extra}}
  <mj-text>Papildoma informacija: {{extra}}</mj-text>
{{/if}}
```

Tai ypač naudinga, kai norite rodyti papildomos informacijos bloką tik tada, kai jis iš tikrųjų yra užpildytas.

### Prekės ženklo spalvos ir logotipas

Nustatymuose taip pat galite:
- Įkelti savo logotipą
- Pakeisti prekės ženklo spalvas

## 3. Sąskaitos siuntimas

1. Sąskaitoje faktūroje nurodykite pirkėjo el. pašto adresą
2. Paspaukite mygtuką „Išsiųsti sąskaitą faktūrą"
3. Sąskaita bus pažymėta kaip užrakinta ir išsiųsta

Sąskaita bus išsiųsta iš jūsų Gmail paskyros naudojant pasirinktą šabloną.
