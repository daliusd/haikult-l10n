---
title: 'Dina data är krypterade: Varför det spelar roll'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Varje Haiku.lt-användardatabas är krypterad i vila. Här är vad det faktiskt betyder och varför du bör bry dig.

## Vad kryptering innebär (helt enkelt)

Föreställ dig dina fakturor och kunddata som en dagbok. Kryptering låser den dagboken och förvränger varje ord till slumpmässig rappakalja. Utan nyckeln ser den som håller i dagboken inget annat än brus — `X7k#mQ2$pL9@vR4...` — helt oläsligt.

Varje användares databas får en unik nyckel, och Haiku.lt lagrar aldrig den nyckeln i klartext.

## Scenariot med säkerhetskopiering

Haiku.lt gör regelbundna säkerhetskopior för att skydda mot dataförlust. Föreställ dig nu ett värsta scenario: en hackare får på något sätt tag på en av dessa säkerhetskopiefiler.

Vad har de då? En fil full av krypterad rappakalja. Utan krypteringsnyckeln är säkerhetskopian värdelös för dem. De kan inte läsa dina kundnamn, fakturabelopp eller någon annan data.

## Hur starkt är «krypterad»?

Haiku.lt använder AES-256-kryptering — samma standard som används av banker och regeringar över hela världen. För att brute-forcea en AES-256-nyckel skulle en angripare behöva prova 2²⁵⁶ möjliga kombinationer.

För att få perspektiv: även om alla datorer på jorden körs i full hastighet skulle det ta längre tid att knäcka en enda AES-256-nyckel än universums nuvarande ålder. Det är inte en praktisk attack.

## Slutsatsen

Om Haiku.lt:s säkerhetskopior någonsin skulle bli stulna är dina data fortfarande skyddade. Krypteringen säkerställer att fysisk besittning av en säkerhetskopiefil är meningslös utan krypteringsnyckeln.

Dina fakturor är ditt företag. De bör förbli dina.
