---
title: 'Invoice Markup Language (InML)'
date: '2026-02-22'
modified: '2026-05-24'
---

InML (Invoice Markup Language) ist eine XML-basierte Vorlagensprache, mit der
Sie das PDF-Layout Ihrer Rechnungen in Haiku.lt definieren. Sie haben damit
volle Kontrolle über Struktur, Stil und Inhalt Ihrer Rechnungen.

Als Ausgangspunkt können Sie einen der fünf integrierten Stile auswählen und
anpassen oder eine Vorlage von Grund auf neu schreiben.

## Grundstruktur

Jede InML-Vorlage beginnt mit einem `<inml>`-Wurzelelement:

```xml
<inml version="1.0" page-size="A4" margin="20mm"
      font-regular="Roboto-Light" font-bold="Roboto-Medium">
  <page>
    <!-- Elemente, die auf jeder Seite gezeichnet werden -->
  </page>
  <layout>
    <!-- Inhaltsbereiche -->
  </layout>
</inml>
```

### Wurzel-Attribute

| Attribut       | Beschreibung                                       |
| -------------- | -------------------------------------------------- |
| `version`      | InML-Version. Aktuell `1.0`.                       |
| `page-size`    | Seitenformat. Aktuell wird nur `A4` unterstützt.   |
| `margin`       | Standard-Seitenrand (z. B. `20mm`).                |
| `font-regular` | Schriftart für normalen Text (z. B. `Roboto-Light`). |
| `font-bold`    | Schriftart für fetten Text (z. B. `Roboto-Medium`). |

## Einheiten

Alle Maße verwenden Millimeter (`mm`) oder Punkte. Schreiben Sie Werte wie
`20mm`, `5mm`, `210mm`. Schriftgrößen werden als reine Zahlen in Punkten
angegeben (z. B. `font-size="12"`).

## Seitenelemente

Der Abschnitt `<page>` definiert Elemente, die auf **jeder Seite** des PDFs
hinter dem Hauptinhalt gezeichnet werden. Verwenden Sie ihn für
Hintergrundbilder, dekorative Rechtecke oder Linien.

```xml
<page>
  <image src="{{background}}" x="0mm" y="0mm" width="210mm" height="297mm" />
  <rect x="0mm" y="0mm" width="210mm" height="30mm" fill="#f1f5f9" />
  <line x1="20mm" y1="50mm" x2="190mm" y2="50mm" color="#cccccc" width="0.5mm" />
</page>
```

### Verfügbare Seitenelemente

- **`<image>`** — Hintergrundbild. Attribute: `src`, `x`, `y`, `width`,
  `height`.
- **`<rect>`** — Rechteck. Attribute: `x`, `y`, `width`, `height`, `fill`,
  `stroke`, `stroke-width`.
- **`<line>`** — Linie. Attribute: `x1`, `y1`, `x2`, `y2`, `color`, `width`.

## Layout und Bereiche

Der Abschnitt `<layout>` enthält ein oder mehrere `<region>`-Elemente. Jeder
Bereich ist eine unabhängige Inhaltszone mit eigenem Positionierungsmodus.

```xml
<layout>
  <region id="header" flow="fixed" margin-top="5mm"
          margin-left="20mm" content-width="170mm">
    <!-- Inhalt -->
  </region>
  <region id="body" flow="sequential" margin-top="20mm">
    <!-- Inhalt -->
  </region>
</layout>
```

### Region-Attribute

| Attribut        | Beschreibung                                                                  |
| --------------- | ----------------------------------------------------------------------------- |
| `id`            | Eindeutige Kennung des Bereichs.                                              |
| `flow`          | Positionierungsmodus: `sequential`, `absolute` oder `fixed`.                  |
| `margin-left`   | Horizontaler Abstand vom Seitenrand.                                          |
| `content-width` | Überschreibt die Inhaltsbreite für diesen Bereich.                            |
| `margin-top`    | Vertikaler Abstand. Bei `sequential`-Bereichen fügt er Platz darüber ein.     |
| `min-height`    | Mindesthöhe, die für den Bereich reserviert wird, auch bei kürzerem Inhalt.   |

### Flow-Modi

- **`sequential`** — Bereiche fließen nacheinander von oben nach unten. Dies
  ist der gängigste Modus für den Hauptinhalt.
- **`absolute`** — wird an einer bestimmten Stelle positioniert, berechnet aus
  der aktuellen vertikalen Position. Nachfolgende `sequential`-Bereiche folgen
  danach.
- **`fixed`** — wird an einer festen Position auf der Seite platziert,
  unabhängig von anderen Bereichen. Nützlich für Kopfzeilen oder Overlays.

### Layout-Spalten

Um Bereiche nebeneinander anzuordnen, fassen Sie sie auf Layout-Ebene in einem
`<columns>`-Element zusammen:

```xml
<layout>
  <columns>
    <column margin-left="20mm" content-width="80mm">
      <region id="left" flow="sequential">
        <!-- linker Inhalt -->
      </region>
    </column>
    <column content-width="80mm">
      <region id="right" flow="sequential">
        <!-- rechter Inhalt -->
      </region>
    </column>
  </columns>
</layout>
```

Jedes `<column>` kann die Attribute `margin-left` und `content-width` haben
und enthält ein oder mehrere `<region>`-Elemente.

## Inhaltselemente

Inhaltselemente werden innerhalb von Bereichen platziert. Alle Inhaltselemente
teilen sich diese optionalen Attribute:

| Attribut        | Beschreibung                                            |
| --------------- | ------------------------------------------------------- |
| `font`          | `regular` oder `bold`.                                  |
| `font-size`     | Schriftgröße in Punkten (z. B. `12`).                   |
| `color`         | Text- oder Füllfarbe (z. B. `#333333`).                 |
| `align`         | Textausrichtung: `left`, `right` oder `center`.         |
| `margin-top`    | Abstand über dem Element.                               |
| `margin-bottom` | Abstand unter dem Element.                              |

### `<logo>`

Zeigt das Firmenlogo unter Beibehaltung des Seitenverhältnisses.

```xml
<logo src="{{logo}}" width="50mm" ratio="{{logoRatio}}" />
```

| Attribut  | Beschreibung                                            |
| --------- | ------------------------------------------------------- |
| `src`     | Bilddaten (`{{logo}}`-Vorlagenvariable verwenden).      |
| `width`   | Anzeigebreite.                                          |
| `height`  | Optionale feste Höhe.                                   |
| `ratio`   | Seitenverhältnis (`{{logoRatio}}`-Variable verwenden).  |

### `<title>`

Überschriftentext, typischerweise für den Rechnungstitel.

```xml
<title font="bold" font-size="14" align="center">{{invoiceTitle}}</title>
```

### `<text>`

Normaler Textinhalt.

```xml
<text font="regular" font-size="12">{{seller}}</text>
```

### `<columns>` und `<column>`

Ordnen Inhalt innerhalb eines Bereichs nebeneinander an.

```xml
<columns>
  <column width="50%" align="left">
    <text font="bold" font-size="12">{{t.invoice.seller}}</text>
    <text font="regular" font-size="12" margin-top="5mm">{{seller}}</text>
  </column>
  <column width="50%" align="right">
    <text font="bold" font-size="12">{{t.invoice.buyer}}</text>
    <text font="regular" font-size="12" margin-top="5mm">{{buyer}}</text>
  </column>
</columns>
```

Jedes `<column>` hat ein `width`-Attribut als Prozentwert (z. B. `50%`) und
ein optionales `align`-Attribut.

### `<stack>` und `<group>`

Vertikal gestapelte Inhaltsgruppen mit konfigurierbarem Abstand dazwischen.

```xml
<stack spacing="10mm">
  <group>
    <text font="bold" font-size="12">Erster Abschnitt</text>
    <text font="regular" font-size="12">Inhalt hier</text>
  </group>
  <group>
    <text font="bold" font-size="12">Zweiter Abschnitt</text>
    <text font="regular" font-size="12">Weiterer Inhalt</text>
  </group>
</stack>
```

Das Attribut `spacing` steuert den vertikalen Abstand zwischen den Gruppen.

### `<box>`

Ein umrandeter/gepolsterter Container für Inhalt.

```xml
<box stroke="#cccccc" padding="5mm">
  <text font="regular" font-size="12">Eingerahmter Inhalt</text>
</box>
```

| Attribut  | Beschreibung                  |
| --------- | ----------------------------- |
| `stroke`  | Rahmenfarbe.                  |
| `padding` | Innenabstand.                 |
| `height`  | Optionale feste Höhe.         |

### `<rect>`

Eine Rechtecksform im Inhaltsfluss.

```xml
<rect width="170mm" height="1mm" fill="#238c83" />
```

| Attribut | Beschreibung        |
| -------- | ------------------- |
| `width`  | Rechteckbreite.     |
| `height` | Rechteckhöhe.       |
| `fill`   | Füllfarbe.          |
| `stroke` | Rahmenfarbe.        |

### `<image>`

Ein eingebettetes Bild im Inhaltsfluss.

```xml
<image src="{{logo}}" width="50mm" height="20mm" />
```

### `<spacer>`

Fügt vertikalen Abstand zwischen Elementen ein.

```xml
<spacer height="10mm" />
```

### `<invoice-table>`

Die Tabelle der Rechnungspositionen. Dies ist das zentrale Element zur
Darstellung der Rechnungspositionen mit Spalten und einer Zusammenfassung.

```xml
<invoice-table row-style="minimal" cell-padding="0mm"
       separator-after-header="true" separator-after-items="true"
       separator-color="#aaaaaa" separator-width="0.5mm">
  <col name="id"     label="{{t.invoice.lineItemNo}}"     width="10mm" align="left" />
  <col name="name"   label="{{t.invoice.lineItemName}}"   width="80mm" align="left" />
  <col name="unit"   label="{{t.invoice.lineItemUnit}}"   width="20mm" align="right" />
  <col name="amount" label="{{t.invoice.lineItemAmount}}" width="20mm" align="right" />
  <col name="price"  label="{{priceColumnLabel}}"         width="20mm" align="right" />
  <col name="total"  label="{{t.invoice.lineItemSum}}"    width="20mm" align="right" />

  <summary>
    <row label="{{t.invoice.total}}" value="{{total}}" />
  </summary>
</invoice-table>
```

#### Tabellen-Attribute

| Attribut                 | Beschreibung                                                                    |
| ------------------------ | ------------------------------------------------------------------------------- |
| `row-style`              | Zeilenstil: `minimal`, `striped`, `bordered` oder `colored-header`.             |
| `cell-padding`           | Innenabstand in jeder Zelle.                                                    |
| `separator-after-header` | Linie nach der Kopfzeile anzeigen (`true`/`false`).                             |
| `separator-after-items`  | Linie nach allen Positionen anzeigen (`true`/`false`).                          |
| `separator-color`        | Farbe der Trennlinien.                                                          |
| `separator-width`        | Dicke der Trennlinien.                                                          |
| `stripe-color`           | Hintergrundfarbe für abwechselnde Zeilen (im Stil `striped`).                   |
| `header-bg-color`        | Hintergrundfarbe der Kopfzeile (im Stil `colored-header`).                      |
| `header-text-color`      | Textfarbe der Kopfzeile (im Stil `colored-header`).                             |
| `header-extra-padding`   | Zusätzlicher Innenabstand der Kopfzeile.                                        |

#### Spaltendefinitionen

Jedes `<col>` definiert eine Tabellenspalte:

| Attribut  | Beschreibung                                                                          |
| --------- | ------------------------------------------------------------------------------------- |
| `name`    | Spaltenkennung: `id`, `name`, `unit`, `amount`, `price`, `vat`, `vat_sum`, `total`.   |
| `label`   | Spaltenüberschrift (Vorlagenvariablen für Übersetzungen verwenden).                   |
| `width`   | Spaltenbreite.                                                                        |
| `align`   | Textausrichtung: `left`, `right` oder `center`.                                       |

Für umsatzsteuerpflichtige Verkäufer fügen Sie üblicherweise die zusätzlichen
Spalten `vat` und `vat_sum` ein. Verwenden Sie `{{#if vatpayer}}`, um sie
bedingt anzuzeigen.

#### Zusammenfassungszeilen

Der Abschnitt `<summary>` definiert die Summen, die unter der Tabelle
angezeigt werden:

```xml
<summary>
  {{#if vatpayer}}
    <row label="{{t.invoice.total_without_vat}}" value="{{totalWithoutVat}}" />
    <row label="{{t.invoice.vat}}" value="{{vatTotal}}" />
  {{/if}}
  <row label="{{t.invoice.total}}" value="{{total}}" />
  {{#if alreadyPaid}}
    <row label="{{t.invoice.alreadyPaid}}" value="{{alreadyPaidFormatted}}" />
    <row label="{{t.invoice.sumToPay}}" value="{{sumToPay}}" />
  {{/if}}
</summary>
```

## Vorlagenvariablen

InML verwendet die [Handlebars](https://handlebarsjs.com/)-Syntax für
dynamische Inhalte. Variablen werden mit `{{variableName}}` eingefügt,
bedingte Blöcke mit `{{#if variableName}}...{{/if}}`.

### Verfügbare Variablen

#### Rechnungsdaten

| Variable              | Beschreibung                                                  |
| --------------------- | ------------------------------------------------------------- |
| `invoiceTitle`        | Aufgelöster Rechnungstitel nach Typ und Umsatzsteuerstatus.   |
| `seriesName`          | Name der Rechnungsserie.                                      |
| `seriesId`            | Rechnungsnummer innerhalb der Serie.                          |
| `formattedDate`       | Formatiertes Rechnungsdatum.                                  |
| `seller`              | Verkäuferinformationen.                                       |
| `buyer`               | Käuferinformationen.                                          |
| `issuer`              | Person, die die Rechnung ausgestellt hat.                     |
| `extra`               | Zusätzlicher Informationstext.                                |

#### Preisfelder

| Variable              | Beschreibung                                                  |
| --------------------- | ------------------------------------------------------------- |
| `total`               | Gesamtbetrag der Rechnung (formatiert).                       |
| `totalWithoutVat`     | Gesamtbetrag ohne USt. (formatiert).                          |
| `vatTotal`            | USt.-Betrag (formatiert).                                     |
| `alreadyPaid`         | Bereits gezahlter Betrag (Zahl, zur Verwendung in `{{#if}}`). |
| `alreadyPaidFormatted`| Bereits gezahlter Betrag (formatierter String).               |
| `sumToPay`            | Verbleibender Zahlbetrag (formatiert).                        |
| `priceInWords`        | Gesamtpreis in Worten (falls verfügbar).                      |
| `priceColumnLabel`    | Beschriftung der Preisspalte (ändert sich bei USt.-Pflicht).  |

#### Flags

| Variable    | Beschreibung                                                        |
| ----------- | ------------------------------------------------------------------- |
| `vatpayer`  | `true`, wenn der Verkäufer USt.-pflichtig ist. Mit `{{#if vatpayer}}`. |

#### Farben

| Variable                   | Beschreibung                                  |
| -------------------------- | --------------------------------------------- |
| `colors.headerBackground`  | Hintergrundfarbe der Kopfzeile (Standard `#f1f5f9`). |
| `colors.primaryAccent`     | Primäre Akzentfarbe (Standard `#238c83`).      |

#### Bilder

| Variable    | Beschreibung                                          |
| ----------- | ----------------------------------------------------- |
| `logo`      | Firmenlogo-Bilddaten. Mit `{{#if logo}}` verwenden.   |
| `logoRatio` | Logo-Seitenverhältnis (in `<logo ratio="...">`).      |
| `background`| Hintergrundbilddaten. Mit `{{#if background}}` verwenden. |

#### Übersetzungs-Strings

Alle Oberflächenbeschriftungen sind über das `t`-Objekt verfügbar. Gängige
sind:

| Variable                            | Beschreibung                |
| ----------------------------------- | --------------------------- |
| `t.invoice.seller`                  | „Verkäufer"-Beschriftung    |
| `t.invoice.buyer`                   | „Käufer"-Beschriftung       |
| `t.invoice.no`                      | „Nr."-Beschriftung          |
| `t.invoice.total`                   | „Gesamt"-Beschriftung       |
| `t.invoice.total_without_vat`       | „Gesamt ohne USt."          |
| `t.invoice.vat`                     | „USt."-Beschriftung         |
| `t.invoice.lineItemNo`              | „Nr."-Spaltenkopf           |
| `t.invoice.lineItemName`            | „Name"-Spaltenkopf          |
| `t.invoice.lineItemUnit`            | „Einheit"-Spaltenkopf       |
| `t.invoice.lineItemAmount`          | „Menge"-Spaltenkopf         |
| `t.invoice.lineItemPrice`           | „Preis"-Spaltenkopf         |
| `t.invoice.lineItemPriceWithoutVAT` | „Preis (ohne USt.)"         |
| `t.invoice.lineItemVat`             | „USt. %"-Spaltenkopf        |
| `t.invoice.lineItemVatSum`          | „USt.-Betrag"-Spaltenkopf   |
| `t.invoice.lineItemSum`             | „Summe"-Spaltenkopf         |
| `t.invoice.alreadyPaid`             | „Bereits gezahlt"           |
| `t.invoice.sumToPay`                | „Zu zahlende Summe"         |
| `t.invoice.sumInWords`              | „Summe in Worten"           |
| `t.invoice.invoiceIssuedBy`         | „Rechnung ausgestellt von"  |
| `t.metadata.series`                 | „Serie"-Beschriftung        |

## Integrierte Stile

Haiku.lt enthält fünf integrierte Stile, die Sie als Ausgangspunkt verwenden
können:

- **minimalist** — klares Design mit zentriertem Titel und minimalen Trennern
- **modern-accent** — farbige Kopfleiste mit Akzentfarben
- **left-aligned** — linksbündiges Layout mit einfacher Struktur
- **bordered** — umrandete Tabellenzeilen und -abschnitte
- **split-column** — zweispaltiges Layout mit getrennten Verkäufer- und
  Käuferinformationen

Wählen Sie in den Rechnungseinstellungen einen integrierten Stil aus und
wechseln Sie dann zu benutzerdefinierter InML, um ihn als Basis für Ihre
Anpassungen zu verwenden.

## Vollständiges Beispiel

Hier ist eine vereinfachte Vorlage, die die wichtigsten InML-Konzepte zeigt:

```xml
<inml version="1.0" page-size="A4" margin="20mm"
      font-regular="Roboto-Light" font-bold="Roboto-Medium">
  <page>
    {{#if background}}
      <image src="{{background}}" x="0mm" y="0mm" width="210mm" height="297mm" />
    {{/if}}
  </page>
  <layout>
    {{#if logo}}
      <region id="logo" flow="absolute">
        <logo src="{{logo}}" width="50mm" ratio="{{logoRatio}}" />
        <spacer height="10mm" />
      </region>
    {{/if}}

    <region id="title-block" flow="absolute" min-height="40mm">
      <title font="bold" font-size="14" align="center">{{invoiceTitle}}</title>
      <text font="bold" font-size="12" align="center" margin-top="8mm">
        {{t.metadata.series}} {{seriesName}} {{t.invoice.no}} {{seriesId}}
      </text>
      <text font="regular" font-size="12" align="center" margin-top="16mm">
        {{formattedDate}}
      </text>
    </region>

    <region id="parties" flow="sequential" min-height="30mm">
      <columns>
        <column width="50%" align="left">
          <text font="bold" font-size="12">{{t.invoice.seller}}</text>
          <text font="regular" font-size="12" margin-top="5mm">{{seller}}</text>
        </column>
        <column width="50%" align="right">
          <text font="bold" font-size="12">{{t.invoice.buyer}}</text>
          <text font="regular" font-size="12" margin-top="5mm">{{buyer}}</text>
        </column>
      </columns>
    </region>

    <region id="table" flow="sequential" margin-top="20mm">
      <invoice-table row-style="minimal" cell-padding="0mm"
             separator-after-header="true" separator-after-items="true"
             separator-color="#aaaaaa" separator-width="0.5mm">
        <col name="id"     label="{{t.invoice.lineItemNo}}"     width="10mm" align="left" />
        <col name="name"   label="{{t.invoice.lineItemName}}"   width="80mm" align="left" />
        <col name="unit"   label="{{t.invoice.lineItemUnit}}"   width="20mm" align="right" />
        <col name="amount" label="{{t.invoice.lineItemAmount}}" width="20mm" align="right" />
        <col name="price"  label="{{priceColumnLabel}}"         width="20mm" align="right" />
        <col name="total"  label="{{t.invoice.lineItemSum}}"    width="20mm" align="right" />

        <summary>
          <row label="{{t.invoice.total}}" value="{{total}}" />
        </summary>
      </invoice-table>
    </region>

    <region id="footer" flow="sequential">
      {{#if extra}}
        <text font="regular" font-size="12">{{extra}}</text>
        <spacer height="10mm" />
      {{/if}}
      <text font="regular" font-size="12">
        {{t.invoice.invoiceIssuedBy}} {{issuer}}
      </text>
    </region>
  </layout>
</inml>
```
