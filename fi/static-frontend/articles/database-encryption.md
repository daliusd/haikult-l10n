---
title: 'Tietosi on salattu: Miksi sillä on merkitystä'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Jokainen Haiku.lt-käyttäjän tietokanta on salattu levossa. Tässä kerrotaan, mitä se tarkoittaa ja miksi sinun pitäisi välittää siitä.

## Mitä salaus tarkoittaa (yksinkertaisesti)

Kuvittele laskusi ja asiakastietosi päiväkirjaksi. Salaus lukitsee päiväkirjan ja sekoittaa jokaisen sanan satunnaiseksi sekamelskaksi. Ilman avainta päiväkirjaa hallussaan pitävä henkilö näkee pelkkää kohinaa — `X7k#mQ2$pL9@vR4...` — täysin lukukelvotonta.

Jokaisen käyttäjän tietokanta saa yksilöllisen avaimen, eikä Haiku.lt koskaan tallenna avainta selväkielisenä tekstinä.

## Varmuuskopiointiskenaario

Haiku.lt tekee säännöllisesti varmuuskopioita suojautuakseen tietojen katoamiselta. Kuvittele nyt pahin mahdollinen skenaario: hakkeri saa jotenkin haltuunsa yhden näistä varmuuskopiotiedostoista.

Mitä heillä on? Tiedosto täynnä sekavaa siansaksaa. Ilman salausavainta varmuuskopio on heille arvoton. He eivät voi lukea asiakkaiden nimiä, laskutussummia tai muita tietoja.

## Kuinka vahva on «salattu»?

Haiku.lt käyttää AES-256-salausta — samaa standardia, jota pankit ja hallitukset käyttävät maailmanlaajuisesti. AES-256-avaimen murtamiseksi hyökkääjän pitäisi kokeilla 2²⁵⁶ mahdollista yhdistelmää.

Vaikka kaikki maapallon tietokoneet toimisivat täydellä nopeudella, yhden AES-256-avaimen murtaminen kestäisi kauemmin kuin maailmankaikkeuden nykyinen ikä. Se ei ole käytännöllinen hyökkäys.

## Lopputulos

Jos Haiku.lt:n varmuuskopiot joskus varastettaisiin, tietosi pysyisivät suojattuina. Salaus varmistaa, että varmuuskopiotiedoston fyysinen hallussapito on merkityksetöntä ilman salausavainta.

Laskusi ovat sinun liiketoimintaasi. Niiden pitäisi pysyä sinun.
