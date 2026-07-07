---
title: 'Pigu-Integration: Einrichtung und Rechnungsverwaltung'
date: '2026-05-04'
modified: '2026-05-24'
---

Die Pigu-Integration verbindet Ihr Haiku-Konto mit der Pigu-Marktplatzfamilie — pigu.lt, 220.lv, kaup24.ee und hobbyhall.fi — damit Sie Bestellungen einsehen und Rechnungen erstellen können, ohne zwischen Systemen zu wechseln.

---

## Schritt 1 — Pigu-Konto verbinden

![Pigu-Einstellungsseite](/screenshots/pigu-integration/de/step-1-pigu-settings.png)

1. Gehen Sie zu **Einstellungen → Pigu**.
2. Geben Sie Ihren Pigu-Händler-**Benutzernamen** und **Passwort** ein und klicken Sie auf **Verbinden**.
3. Ein grünes **Verbunden**-Badge erscheint und zeigt Ihren Shop-Namen sowie das Ablaufdatum der Sitzung.

Ihre Anmeldedaten werden verwendet, um ein Zugriffstoken zu erhalten.

---

## Schritt 2 — Jede Länder-Registerkarte konfigurieren

Nach der Verbindung erscheint jeder Marktplatz-Kanal, auf dem Ihr Konto aktiv ist, als Registerkarte: **LT**, **LV**, **EE** oder **FI**. Öffnen Sie jede Registerkarte, auf der Sie verkaufen, und füllen Sie die folgenden Einstellungen aus.

### Rechnungsnummerierung

| Feld | Was eingeben |
|---|---|
| Rechnungsserie | Der Seriencode für Standardrechnungen (z. B. `PIG`) |
| Proforma-Serie | Der Seriencode für Proforma-Rechnungen |
| Gutschriftserie | Der Seriencode für Gutschriften |

### Verkäuferinformationen

| Feld | Was eingeben |
|---|---|
| Verkäufer | Ihr vollständiger Verkäuferblock — Name, Adresse usw. — so wie er auf Rechnungen erscheinen soll |
| Aussteller | Die Person oder Rolle, die die Rechnung unterzeichnet |
| Zusatz | Beliebiger Text, der unten auf der Rechnung gedruckt wird. Unterstützt Handlebars-Vorlagen mit Bestellungs- und Rechnungsvariablen. |
| Verkäuferland | Ihr Registrierungsland — entspricht standardmäßig dem Kanal-Land, ändern Sie es nur bei Abweichung |
| Steuernummer | Aus den globalen Einstellungen vorausgefüllt; hier überschreiben, falls dieser Kanal eine andere Nummer verwendet |
| Steuerregistrierung | Aus den globalen Einstellungen vorausgefüllt; bei Bedarf überschreiben |

Beispiel-Zusatzkonfiguration:

```
Order: {{app_name}}/{{external_id}}
{{#if invoice.invoiceReference}}Standard invoice reference: {{invoice.invoiceReference}}{{/if}}
{{#if invoice.buyerTaxId}}Reverse charge (Directive 2006/112/EC){{/if}}
```

### MwSt.-Einstellungen

Diese Felder erscheinen nur, wenn eine Steuernummer hinterlegt ist.

- **MwSt.-Rechnungen erstellen** — aktivieren, um MwSt. auf Rechnungen für diesen Kanal auszuweisen.
- **Bestellungen mit MwSt. 0 %** — aktivieren, wenn einige Bestellungen für einen MwSt.-Nullsatz infrage kommen (z. B. grenzüberschreitende B2B-Verkäufe).

Klicken Sie nach der Konfiguration jeder Registerkarte auf **Speichern**.

---

## Schritt 3 — Mit manueller Rechnungserstellung beginnen

> **Empfehlung:** Lassen Sie zunächst jegliche Automatisierung deaktiviert.

Öffnen Sie die Seite **Pigu-Bestellungen**, erstellen Sie für einige reale Bestellungen manuell Rechnungen und prüfen Sie, ob Seriencodes, Verkäuferblock und MwSt.-Beträge genau richtig aussehen. Es ist wesentlich einfacher, die Einstellungen in dieser Phase anzupassen, als nachdem Hunderte von Rechnungen automatisch generiert wurden.

Sobald Sie mit der Ausgabe zufrieden sind, fahren Sie mit Schritt 4 fort.

---

## Schritt 4 — Automatisierung aktivieren (optional)

Wenn Sie sicher sind, dass die Konfiguration korrekt ist, können Sie das automatische Verhalten pro Kanal aktivieren:

| Einstellung | Funktion |
|---|---|
| **Standardrechnungen automatisch erstellen** | Eine Standardrechnung wird automatisch erstellt, wenn eine Bestellung abgeschlossen und bezahlt ist |
| **Gutschriften automatisch erstellen** | Eine Gutschrift wird automatisch erstellt, wenn eine Bestellung zurückgegeben oder abgelehnt wird |
| **PDF automatisch zu Pigu hochladen** | Das PDF der Standardrechnung wird nach Erstellung automatisch zu Pigu gesendet und ist für den Käufer sichtbar. Erfordert, dass *Standardrechnungen automatisch erstellen* aktiviert ist |
| **Tägliche E-Mail-Zusammenfassung senden** | Sie erhalten eine tägliche Zusammenfassungs-E-Mail aller Rechnungen, die von der Automatisierung über Nacht erstellt wurden |

### Wie die Automatisierung läuft

Der Job läuft einmal täglich um **3:00 Uhr (Ortszeit Vilnius)**. Jeder Lauf ruft Bestellungen ab, die in den **letzten 48 Stunden** in allen Ihren aktiven Kanälen (LT, LV, EE, FI) aktualisiert wurden, bis zu 5.000 Bestellungen pro Kanal. Proforma-Rechnungen werden nie automatisch erstellt — nur Standardrechnungen und Gutschriften.

> **Tipp:** Aktivieren Sie zuerst die automatische Erstellung und beobachten Sie diese einen Tag lang, bevor Sie den automatischen Upload aktivieren. So können Sie Formatierungsprobleme erkennen, bevor Käufer die PDFs sehen.

---

## Die Bestellungsseite

Gehen Sie zu **Pigu-Bestellungen**, um Ihre Marktplatzbestellungen zu durchsuchen und Rechnungen manuell zu verwalten.

### Filter

Grenzen Sie die Liste nach **Kanal**, **Bestell-ID**, **Bestellstatus** (abgeschlossen, zurückgegeben, abgelehnt) und **Datumsbereich** (aktualisiert von / bis) ein. Standardmäßig zeigt die Seite die letzten 24 Stunden an.

### Aktionen pro Bestellung

Jede Zeile zeigt den Käufer, den Gesamtbetrag, den Bestellstatus, den Zahlungsstatus und alle bereits erstellten Rechnungen. In der Spalte **Aktionen**:

- **Rechnung erstellen** — erstellt die nächste passende Rechnung. Die Schaltflächenbeschriftung gibt an, was erstellt wird: *Proforma-Rechnung erstellen*, *Standardrechnung erstellen* oder *Gutschrift erstellen*.
- **PDF hochladen** — sendet das PDF der Standardrechnung an Pigu. Nach dem Hochladen wird die Schaltfläche durch den Text *Zu Pigu hochgeladen* ersetzt.

### Massenaktionen

Oben auf der Seite wirken zwei Massen-Schaltflächen auf alle infrage kommenden Bestellungen in der aktuellen gefilterten Ansicht:

- **Rechnungen in Masse erstellen** — erstellt Rechnungen für jede Bestellung, die eine benötigt.
- **PDFs in Masse hochladen** — lädt PDFs für jede Standardrechnung hoch, die noch nicht gesendet wurde.

Während der Operation wird ein Fortschrittsbalken angezeigt. Bei einem Fehler stoppt die Verarbeitung und der Fehler wird angezeigt, damit Sie das Problem vor einem erneuten Versuch untersuchen können.
