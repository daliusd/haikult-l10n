---
title: 'El. pašto nustatymai: SMTP'
date: '2026-05-23'
modified: '2026-05-23'
---

SMTP (Simple Mail Transfer Protocol) yra universalus el. laiškų siuntimo standartas. Rinkitės SMTP, jei prie „Haiku.lt“ nesijungiate per Google paskyrą arba norite, kad sąskaitos faktūros būtų siunčiamos per konkretų serverį – jūsų domeno paštą, Outlook, SendGrid, Mailgun ar bet kurį kitą tiekėją. Jei naudojate Gmail OAuth, geriau pasirinkite [El. pašto nustatymai: Gmail (OAuth)](/lt/email-setup-gmail) – Google paskyroms tai paprastesnis ir saugesnis variantas.

## Sukonfigūruokite SMTP serverį

![SMTP forma „El. pašto tiekėjo" nustatymų puslapyje](/screenshots/email-setup-smtp/lt/step-1-smtp-form.png)

Atidarykite **Nustatymai → El. pašto tiekėjas**. Puslapis iš karto rodo SMTP formą. Jei prisijungėte per Google, pirmiausia perjunkite į **SMTP** parinktį.

Pradėkite nuo **tiekėjo šablono** sąrašo – pasirinkę Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid ar Mailgun gausite užpildytą serverio adresą, prievadą ir saugumo nustatymus. Jei jūsų tiekėjo sąraše nėra, rinkitės **Custom**.

Toliau užpildykite likusius laukus:

- **Host** – SMTP serverio adresas (pvz., `smtp.gmail.com`).
- **Port** – paprastai 587 (STARTTLS) arba 465 (SSL/TLS). Šabloną pasirinkus, prievadas dažniausiai įvedamas teisingai.
- **Security** – pasirinkite tarp STARTTLS (paprasto ryšio atnaujinimas į šifruotą) ir SSL/TLS (šifruota nuo pirmojo baito). Naudokite tai, ką nurodo jūsų tiekėjas.
- **Username** – paprastai pilnas el. pašto adresas.
- **Password** – paskyros slaptažodis arba programai skirtas slaptažodis, jei tiekėjas to reikalauja (Gmail ir Yahoo reikalauja).
- **From address** – gavėjui rodomas siuntėjas, pvz., `Company Name <you@example.com>`.

## Patikrinkite ryšį

Prieš išsaugodami spauskite **Test Connection**. „Haiku.lt“ bandys prisijungti prie serverio, autentifikuotis ir parodys rezultatą. Jei testas nepavyks, klaidos pranešimas dažniausiai parodys priežastį – netinkamą prievadą, neteisingus prisijungimo duomenis ar neatitinkantį saugumo nustatymą.

## Išsaugokite ir pradėkite siųsti

Kai testas pavyksta, spauskite **Save SMTP Settings**. Nuo to momento kiekviena išsiųsta sąskaita faktūra iškeliaus per jūsų SMTP serverį.

Taip pat žr.: [El. pašto nustatymai: Gmail (OAuth)](/lt/email-setup-gmail).
