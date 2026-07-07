---
title: 'Rechnungsstellung in Deutschland: Vollständiger Compliance-Leitfaden 2026 für kleine Unternehmen'
date: '2026-02-08'
modified: '2026-03-28'
showDate: true
---

Deutschland hat einige der strengsten Anforderungen an die Rechnungsstellung in Europa. Zwischen GoBD-Vorschriften, E-Invoicing-Mandaten und strengen Anforderungen an den Prüfpfad kann man sich leicht überfordert fühlen. In diesem Leitfaden erfahren Sie, was Sie über die Rechnungsstellung in Deutschland im Jahr 2026 wissen müssen - von der Mehrwertsteuerregistrierung und den Pflichtfeldern bis hin zu den Fristen für die elektronische Rechnungsstellung und der Einhaltung der GoBD.

## Mehrwertsteuerregistrierung und -sätze

Deutschland bietet eine **Kleinunternehmerregelung**: Wenn Ihr Jahresumsatz unter 22.000 € liegt, können Sie ohne Mehrwertsteuer arbeiten. Die Registrierung wird obligatorisch, wenn Sie im letzten Jahr mehr als 22.000 € umgesetzt haben oder in diesem Jahr voraussichtlich mehr als 50.000 € umsetzen werden. Für grenzüberschreitende Verkäufe in der EU gilt ein Schwellenwert von 10.000 €.

**Format der Umsatzsteuer-Identifikationsnummer**: `DE` + 9 Ziffern (z.B. `DE123456789`)
**Bearbeitungszeit**: 2-4 Wochen vom Bundeszentralamt für Steuern (BZSt)

**Mehrwertsteuersätze:**
- **19%** - Standardsatz (die meisten Waren und Dienstleistungen)
- **7%** - Ermäßigter Satz (Lebensmittel, Bücher, Zeitungen, öffentliche Verkehrsmittel, kulturelle Veranstaltungen)
- **0%** - Exporte und Lieferungen innerhalb der EU (mit gültiger MwSt.-Nummer)

## Pflichtangaben auf Rechnungen

Jede **vollständige Rechnung** (über 250 €) muss enthalten:

- Name, Adresse und Umsatzsteuernummer des Verkäufers (DE + 9 Ziffern)
- Name, Adresse und MwSt.-Nummer des Käufers (falls B2B und registriert)
- Eindeutige fortlaufende Rechnungsnummer (keine Lücken erlaubt)
- Rechnungsdatum und Liefer-/Leistungsdatum
- Klare Beschreibung der Waren/Dienstleistungen
- Menge, Einzelpreis (netto), Mehrwertsteuersatz, Mehrwertsteuerbetrag, Gesamtbetrag (brutto)

> Für **Kleinbetragsrechnungen** unter 250 € gelten geringere Anforderungen - Name und Adresse des Käufers sind nicht erforderlich, nur Angaben zum Verkäufer, Datum, Beschreibung, Mehrwertsteuersatz und Gesamtbetrag.

**Besondere Textanforderungen:**
- **Reverse charge**: „Steuerschuldnerschaft des Leistungsempfängers"
- **Innergemeinschaftliche Lieferung**: „Innergemeinschaftliche Lieferung"
- **Kleinunternehmerregelung**: „Kein Ausweis von Umsatzsteuer, da Kleinunternehmer gemäß § 19 UStG"

## Rechnungsnummerierung

Die Nummern müssen **fortlaufend und eindeutig** sein und dürfen keine Lücken aufweisen. Alphanumerische Formate sind in Ordnung:
- `2026-0001, 2026-0002...`
- `INV-DE-2026-00001`
- `R-2026/001` (R = Rechnung)

Sie können jährlich zurücksetzen, solange das Jahr in der Nummer enthalten ist.

## Sprache und Währung

**Sprache**: Jede der 24 offiziellen EU-Sprachen wird akzeptiert. Deutsch wird für inländische Kunden empfohlen, Englisch für internationale Kunden. Die Steuerbehörden können bei Betriebsprüfungen Übersetzungen verlangen.

**Währung**: Jede Währung wird auf Rechnungen akzeptiert, aber die Mehrwertsteuer muss in EUR angegeben werden, wobei die EZB-Wechselkurse ab dem Rechnungsdatum gelten.

## Anforderungen an die elektronische Rechnungsstellung (2025-2028)

E-Invoicing bedeutet **strukturierte elektronische Rechnungen** mit maschinenlesbaren XML-Daten, nicht nur PDF-E-Mails. Deutschland akzeptiert **ZUGFeRD** (hybrides PDF mit eingebettetem CII XML) und **XRechnung** (reines XML), beide EN 16931-konform.

**Zeitplan:**
- **1. Januar 2025**: Alle B2B-Unternehmen müssen in der Lage sein, elektronische Rechnungen zu **empfangen** (ein E-Mail-Posteingang ist ausreichend; es ist kein spezielles System erforderlich)
- **1. Januar 2027**: Große Unternehmen (ab 800.000 € Umsatz) müssen elektronische Rechnungen **ausstellen**
- **1. Januar 2028**: Alle Unternehmen müssen elektronische Rechnungen **ausstellen**

**B2C-Ausnahme**: Wenn Sie Rechnungen an Verbraucher ausstellen, bleiben die herkömmlichen PDF-Rechnungen gültig. Die elektronische Rechnungsstellung gilt nur für B2B-Transaktionen zwischen mehrwertsteuerlich registrierten Unternehmen.

## Benötigen Sie die doppelte Buchführung?

Die deutschen Buchführungsanforderungen hängen von Ihrer Unternehmensform ab – und das ist entscheidend dafür, was Haiku abdeckt.

**Das deutsche Recht unterscheidet zwei Methoden:**

| Unternehmensform | Erforderliche Methode | Haiku ausreichend? |
|---|---|---|
| Freiberufler, Kleinunternehmer, GbR (unterhalb der HGB-Grenzen) | Einnahmen-Überschuss-Rechnung (EÜR) – einfache Einnahmen-/Ausgabenerfassung gemäß §4 Abs. 3 EStG | ✅ Ja |
| GmbH, AG, größere Kaufleute (über 600.000 € Umsatz oder 60.000 € Gewinn) | Doppelte Buchführung gemäß §238 HGB | ⚠️ Separate Buchhaltungssoftware erforderlich |

**Als Freiberufler oder Kleinunternehmer** unterhalb der HGB-Grenzen gilt die vereinfachte EÜR-Methode. Haikus Rechnungs- und Ausgabenverwaltung – zusammen mit dem Journal-CSV-Export – erfüllt diese Anforderung vollständig.

**Wenn Ihr Unternehmen §238 HGB unterliegt** (typischerweise GmbH, AG oder größere Einzelkaufleute), schreibt das deutsche Recht ein Hauptbuch, einen Kontenplan und eine formelle Bilanz nach dem doppischen System vor. Haiku ist ein Rechnungsstellungstool, keine Buchhaltungssoftware – Sie benötigen dann eine dedizierte Buchhaltungslösung (z. B. DATEV, Lexware, Sevdesk) zusätzlich zu Haiku.

**GoBD-Compliance** (Prüfpfad, Unveränderlichkeit, 10-jährige Aufbewahrung) gilt für **alle** deutschen Steuerpflichtigen unabhängig von der Buchführungsmethode – und Haiku setzt dies vollständig für alle Nutzer um.

## GoBD: Anforderungen an die digitale Buchhaltung

Die deutschen GoBD-Vorschriften verlangen umfassende Prüfpfade und eine unveränderbare Speicherung digitaler Finanzunterlagen.

**Anforderungen an Prüfpfade:**
- Protokollierung aller Zugriffe auf Rechnungen, ihrer Erstellung, Änderung und Löschung
- Benutzeridentifikation und genaue Zeitstempel verfolgen
- Prüfprotokolle 10 Jahre lang aufbewahren
- Sicherstellen, dass die Protokolle manipulationssicher sind

**Unveränderlichkeit von Rechnungen:**
- Rechnungen können nach der Ausstellung nicht mehr geändert werden
- Speicherung im Originalformat (XML für elektronische Rechnungen)
- Eventuelle Korrekturen erfordern Gutschriften oder geänderte Rechnungen
- Aufbewahrung muss manipulationssicher sein

**Zugangskontrolle:**
- Benutzerauthentifizierung erforderlich
- Alle Zugriffe müssen protokolliert werden
- Rollenbasierter Zugriff empfohlen

Für elektronische Rechnungen (ZUGFeRD/XRechnung) ist die XML-Komponente das rechtsverbindliche Dokument.

## Archivierung, Berichterstattung und Sanktionen

**Aufbewahrung**: Bewahren Sie Rechnungen **10 Jahre** ab dem Ende des Kalenderjahres auf. Bewahren Sie sie im Originalformat auf (XML für elektronische Rechnungen), stellen Sie sicher, dass sie für Steuerprüfungen zugänglich sind, und erstellen Sie Sicherungskopien.

**Mehrwertsteuer-Berichterstattung:**
- Monatliche/vierteljährliche MwSt.-Erklärungen, fällig bis zum 10. des Folgemonats
- Jährliche Umsatzsteuererklärung fällig am 31. Mai
- Zusammenfassende Meldung (ZM) monatlich/vierteljährlich bis zum 25.
- **Alle Einreichungen müssen elektronisch** über das ELSTER-Portal erfolgen

**Strafzahlungen**: Die Nichteinhaltung der GoBD kann zu Geldstrafen von bis zu 25.000 €, Steuerschätzungen (in der Regel zu hoch angesetzt) und Nachzahlungen mit Zinsen führen. Die Strafen hängen davon ab, ob die Mängel Ihre finanzielle Lage verzerren - kleinere Fehler sind in der Regel korrigierbar.

## Was Haiku.lt für Deutschland unterstützt

Haiku.lt bietet umfassende Unterstützung für deutsche Rechnungsstellungsanforderungen:

### Kernfunktionen ✅

- **ZUGFeRD/Factur-X-Format**: Jede Rechnung enthält eingebettetes CII XML (EN 16931-konform)
- **Sequentielle Nummerierung**: Konfigurierbare Formate mit Lückenvermeidung
- **Alle Pflichtfelder**: Vollständige Abdeckung der deutschen Rechnungsanforderungen
- **Deutsche Sprache**: Native Unterstützung für alle Rechnungstexte
- **Mehrwährungsfähig mit EUR-Umrechnung**: Unterstützung der internationalen Rechnungsstellung
- **Mehrwertsteuersätze**: 19%, 7% und 0% Berechnungen

### Einhaltung der GoBD ✅ (Aktualisiert Februar 2026)

Haiku.lt enthält jetzt umfassende Funktionen zur Einhaltung der GoBD:

- **Protokollierung von Prüfpfaden**: Verfolgt alle Rechnungsvorgänge (Erstellen, Aktualisieren, Löschen, Anzeigen, Herunterladen) mit Benutzeridentifikation und genauen Zeitstempeln
- **Nicht veränderbare Speicherung**: Die Originaldaten der Rechnungen bleiben in der Datenbank erhalten, wobei alle Änderungen durch Prüfprotokolle dokumentiert werden
- **Zugangskontrolle**: Benutzerauthentifizierung und Aktionsverfolgung für alle Vorgänge
- **Audit-Panel**: Überprüfen Sie Audit-Protokolle unter `/app/settings/invoice-audit`
- **10 Jahre Aufbewahrung**: Vollständige Prüfprotokolle erfüllen die GoBD-Aufbewahrungsanforderungen

### Status der Einhaltung: 🟢 Konform

| Kategorie | Status | Lücke |
|----------|--------|-----|
| **B2C** | ✅ Konform | PDF-Rechnungen mit allen erforderlichen Feldern |
| **B2B-Ausstellung** | ✅ Konform | ZUGFeRD/EN 16931-Format erfüllt alle B2B-Anforderungen |
| **B2B-Empfang** | ✅ Konform | E-Mail-Posteingang ausreichend gemäß BMF (verpflichtend ab Jan 2025) |
| **GoBD** | ✅ Konform | Audit-Protokollierung und unveränderbare Speicherung implementiert |

**E-Rechnungseingang**: Ab Januar 2025 müssen alle deutschen Unternehmen in der Lage sein, strukturierte E-Rechnungen zu empfangen. Laut dem Bundesministerium der Finanzen (BMF) reicht die Bereitstellung eines E-Mail-Postfachs aus, um diese Anforderung zu erfüllen - ein spezielles E-Invoicing-System oder eine App-Funktion ist nicht erforderlich.

## Praktische Erkenntnisse

**B2C-Unternehmen**: Standard-PDF-Rechnungen mit allen Pflichtfeldern sind ausreichend. Keine elektronische Rechnungsstellung erforderlich.

**B2B-Unternehmen**: Müssen bereits jetzt elektronische Rechnungen erhalten (ab Januar 2025) und diese bis 2027/2028 ausstellen. Das ZUGFeRD/EN 16931-Format von Haiku.lt deckt die B2B-Rechnungsstellung ab, und ein E-Mail-Postfach ist für den Empfang gemäß BMF ausreichend.

**Rechnungsnummerierung**: Verwenden Sie einfache Formate wie `2026-0001` und erhöhen Sie die Nummerierung fortlaufend. Dokumentieren Sie alle Lücken.

**Aufbewahrung**: Bewahren Sie Rechnungen 10 Jahre lang auf. Die Speicherung in der Cloud ist in Ordnung, wenn die Integrität und Zugänglichkeit gewahrt bleibt.

**Umsatzsteuer-Voranmeldung**: Setzen Sie Erinnerungen für den 10. eines jeden Monats (oder vierteljährlich). Verspätete Einreichungen sind ein häufiges Problem bei der Einhaltung von Vorschriften.

## Die Quintessenz

Die deutschen Anforderungen an die Rechnungsstellung sind detailliert, aber überschaubar:

- **Pflichtfelder**: Haiku.lt deckt alle Pflichtfelder ab
- **E-Rechnung**: Das Format ZUGFeRD/EN 16931 (das Haiku.lt generiert) erfüllt alle Anforderungen für B2B-Rechnungen
- **B2B-Empfang**: E-Mail-Posteingang ist gemäß BMF ausreichend - kein spezielles System erforderlich
- **B2C**: PDF-Rechnungen bleiben gültig - kein E-Invoicing erforderlich
- **GoBD**: Haiku.lt beinhaltet eine umfassende Audit-Protokollierung und unveränderliche Speicherung (Stand Februar 2026)
- **Aufbewahrung**: Planen Sie eine Archivierung für 10 Jahre

Haiku.lt bietet vollständige B2B- und B2C-Rechnungskonformität für Deutschland, mit EN 16931-konformem ZUGFeRD-Format, GoBD-Audit-Trail-Funktionen und E-Mail-basiertem E-Rechnungsempfang, der die Anforderungen des BMF erfüllt.

Sind Sie bereit, professionelle, Deutschland-konforme Rechnungen zu erstellen? Starten Sie unter [haiku.lt](https://haiku.lt).
