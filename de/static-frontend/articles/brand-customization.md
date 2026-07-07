---
title: 'Markenanpassung'
date: '2026-05-24'
modified: '2026-05-24'
---

Mit Haikult können Sie Ihre Rechnungs-E-Mails — und die PDF-Rechnungsvorschauen — mit eigenem Logo und eigener Farbpalette versehen. Einmal konfiguriert, fließen die Werte in jede Vorlage ein, die sie unterstützt, sodass eine einzige Änderung das Aussehen aller versendeten Rechnungen anpasst.

## Logo

![Logo-Upload-Bereich auf der Seite „Marke“](/screenshots/brand-customization/de/step-1-logo.png)

Öffnen Sie **Einstellungen → Marke**, um das Firmenlogo hochzuladen. Am besten eignet sich ein PNG oder SVG mit transparentem Hintergrund. Das Logo steht E-Mail-Vorlagen als `{{logoUrl}}` zur Verfügung, und die Vorlagen **Mit Logo** rendern es oben in der Nachricht. Sie können das Logo jederzeit austauschen oder entfernen — die Änderung wirkt sich auf danach versendete Rechnungen aus.

## Markenfarben

![Markenfarben-Editor auf der Seite „Marke“](/screenshots/brand-customization/de/step-2-brand-colors.png)

Unterhalb des Logos legen Sie über den Farbeditor die Palette für HTML-E-Mail-Vorlagen fest: Primär- und Sekundärfarbe, Text- und sekundäre Textfarbe sowie Hintergrundfarben. Während Sie eine Farbe verändern, wird die E-Mail-Vorschau auf derselben Seite neu gerendert, sodass Sie die Wirkung vor dem Speichern sehen.

Die Farben stehen E-Mail-Vorlagen als `{{brandPrimary}}`, `{{brandSecondary}}`, `{{brandText}}`, `{{brandTextSecondary}}`, `{{brandBackground}}`, `{{bodyBackground}}` und `{{backgroundSecondary}}` zur Verfügung — wie Sie sie in einer eigenen MJML-Vorlage einsetzen, lesen Sie unter [E-Mail-Vorlagen und Variablen](/de/email-templates-and-variables).

## Wann die Änderungen wirksam werden

Markeneinstellungen werden beim Versand gelesen. Die nächste verschickte Rechnung verwendet die aktuellen Logo- und Farbwerte. Bereits gesendete Rechnungen behalten die Werte, mit denen sie verschickt wurden — ein erneuter Versand ist nicht nötig.

Siehe auch: [E-Mail-Vorlagen und Variablen](/de/email-templates-and-variables).
