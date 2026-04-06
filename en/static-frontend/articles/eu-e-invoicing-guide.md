---
title: 'European E-Invoicing Explained: What Small Businesses Need to Know in 2026'
date: '2026-01-15'
modified: '2026-01-23'
showDate: true
---

If you run a business in Europe, you've probably heard about e-invoicing requirements. The term sounds technical, the regulations vary by country, and the deadlines keep changing. It's confusing. This guide cuts through the complexity and explains what e-invoicing actually means for freelancers and small businesses.

This guide covers the 27 EU member states plus key European trading partners: the UK, Switzerland, Norway, Iceland, and Liechtenstein (collectively "EU+"). These countries either accept EN 16931-compliant formats (which Haiku.lt already generates) or have minimal requirements, making compliance straightforward for businesses operating across Europe.

The good news? For most B2C (business-to-consumer) transactions, traditional PDF invoices remain perfectly valid. E-invoicing mandates primarily target B2B (business-to-business) transactions, and even then, the requirements vary significantly by country.

## What Is E-Invoicing?

E-invoicing isn't just sending an invoice by email. It refers to structured electronic invoices that follow specific technical standards and can be automatically processed by computer systems.

A traditional PDF invoice is essentially a digital image of a paper invoice. A human can read it, but a computer cannot automatically extract the data. An e-invoice, by contrast, contains structured data (usually in XML format) that accounting software can read, validate, and process automatically.

The European standard for e-invoicing is EN 16931, which defines a common format for invoice data across all EU member states. This standard enables invoices to be exchanged between different systems and countries without manual data entry.

## Why Is the EU Pushing E-Invoicing?

The EU's motivation for mandating e-invoicing is primarily about fighting VAT fraud. The "VAT gap" (the difference between expected VAT revenue and actual collection) costs EU countries an estimated 60 billion euros annually. Structured e-invoices make it much harder to create fake invoices or hide transactions from tax authorities.

Beyond fraud prevention, e-invoicing offers real benefits for businesses:

**Faster processing.** Structured invoices can be automatically imported into accounting systems, eliminating manual data entry and reducing errors.

**Quicker payments.** When invoices flow directly into your client's system, they get processed faster. No more invoices sitting in someone's inbox waiting to be manually entered.

**Better record-keeping.** Digital invoices with embedded data are easier to search, archive, and retrieve for audits.

**Environmental impact.** Less paper, fewer physical mailings, smaller carbon footprint.

The EU's VAT in the Digital Age (ViDA) initiative, adopted in 2025, aims to make e-invoicing the standard for all B2B transactions across the EU by 2030.

## B2B vs B2C: What's Actually Required?

Here's the most important thing to understand: **B2C e-invoicing is NOT required in 25 of 27 EU countries.**

The e-invoicing mandates you hear about are almost exclusively for B2B transactions (invoices between businesses). If you're a freelancer invoicing consumers, or a small business selling to individuals, traditional PDF invoices remain perfectly legal in nearly all EU countries.

**Only two countries require B2C e-invoicing:**

- **Italy** 🇮🇹 - Has required e-invoicing for all transactions (B2B, B2C, and B2G) since 2019
- **Romania** 🇷🇴 - B2B mandatory since January 2024; B2C mandatory from January 2026 with 5-day transmission requirement

No other European country (EU or EU+) requires B2C e-invoicing.

**Why B2C is generally exempt:**

1. Consumers don't need structured XML invoices
2. Cash transactions and retail environments are impractical for e-invoicing
3. VAT fraud primarily occurs in B2B supply chains, not consumer sales
4. People simply prefer PDF receipts or paper invoices

If you're selling to consumers in any EU country except Italy or Romania, you can continue using standard PDF invoices without any compliance issues.

## EU+ Coverage: Beyond the European Union

This guide covers not just the 27 EU member states, but also key European trading partners:

**EEA/EFTA Countries** (European Economic Area / European Free Trade Association):
- **Norway** 🇳🇴 - B2G e-invoicing mandatory since 2019; B2B mandate proposed for 2028
- **Iceland** 🇮🇸 - B2G mandatory since 2020; B2B voluntary
- **Liechtenstein** 🇱🇮 - Most flexible; accepts EN 16931 formats voluntarily

**Major Trading Partners**:
- **Switzerland** 🇨🇭 - B2G mandatory since 2016; B2B voluntary (high adoption)
- **United Kingdom** 🇬🇧 - Mandatory e-invoicing from April 2029

These countries either accept EN 16931-compliant formats (which Haiku.lt already generates) or have minimal requirements, making compliance straightforward for businesses operating across Europe.

## What Haiku.lt Supports Today

Haiku.lt already includes e-invoicing capabilities that meet requirements in several EU countries.

### EN 16931 Compliance via CII/Factur-X

Every invoice generated by Haiku.lt includes embedded structured data following the Cross Industry Invoice (CII) format, which is fully compliant with the EN 16931 European standard. This is the same format used by ZUGFeRD (Germany) and Factur-X (France/Germany).

When you download or send a PDF invoice from Haiku.lt, it's actually a hybrid document: it looks like a normal PDF to humans, but it contains embedded XML data that accounting systems can automatically extract and process.

This means your Haiku.lt invoices should meet e-invoicing requirements for countries that accept EN 16931 formats.

### Lithuanian i.SAF Support

For businesses registered in Lithuania, Haiku.lt provides full i.SAF (Standartine Audito Rinkmena) export functionality. You can generate monthly VAT reports in the exact format required by VMI (State Tax Inspectorate) with a single click.

### Multi-Language and Multi-Currency

Haiku.lt supports 32+ invoice languages (all EU languages and more) and multiple currencies. Date formats, number formats, and other localization details automatically adjust based on the selected language.

### Where Haiku.lt Is Likely Compliant Today

**Likely compliant (generates EN 16931-compliant formats):**
- Germany (ZUGFeRD/Factur-X accepted)
- Lithuania (EN 16931 + i.SAF exports)
- Switzerland (CII/Factur-X accepted for B2G)
- Liechtenstein (EN 16931 accepted)
- Czech Republic (voluntary, EN 16931 accepted)
- Estonia (voluntary, EN 16931 accepted)
- Luxembourg (voluntary, EN 16931 accepted)

**Likely compliant (EN 16931 accepted):**
- Austria, Croatia, Slovenia, Latvia, Ireland, Slovakia
- Countries still in planning phase that will adopt EN 16931

**B2G likely compliant, B2B voluntary:**
- Norway (Peppol required for B2G; voluntary for B2B)
- Iceland (Peppol required for B2G; voluntary for B2B)

**Partial support:**
- France (CII/Factur-X supported, UBL format coming)

### What About Countries with Platform Requirements?

Some countries require invoices to be submitted through specific government platforms:

- Belgium requires Peppol network
- Poland requires KSeF platform
- Italy requires SDI (Sistema di Interscambio)
- Greece requires MyDATA platform
- Spain requires VeriFactu certification

Haiku.lt does not currently integrate with these platforms. If you're doing significant B2B business in these countries, you may need additional solutions for compliance.

However, remember: if you're invoicing consumers (B2C) in these countries (except Italy and Romania), standard PDF invoices remain valid.

## European E-Invoicing Requirements by Country

| Country | B2B Mandatory | B2C Required | Haiku.lt Status |
|---------|---------------|--------------|-----------------|
| Austria 🇦🇹 | Planning (B2G mandatory) | No | Likely OK |
| Belgium 🇧🇪 | Jan 2026 (grace until Apr) | No | Platform needed |
| Bulgaria 🇧🇬 | Planning | No | Likely OK |
| Croatia 🇭🇷 | Jan 2026 target | No | Likely OK |
| Cyprus 🇨🇾 | Planning | No | Likely OK |
| Czech Republic 🇨🇿 | Voluntary (B2G mandatory) | No | Likely OK |
| Denmark 🇩🇰 | 2026 (unclear) | No | Likely OK |
| Estonia 🇪🇪 | Voluntary | No | Likely OK |
| Finland 🇫🇮 | Planning | No | Likely OK |
| France 🇫🇷 | Sep 2026-2027 (phased) | No | Partial |
| Germany 🇩🇪 | Jan 2027-2028 (phased) | No | Likely OK |
| Greece 🇬🇷 | Feb 2026 (large companies) | No | Platform needed |
| Hungary 🇭🇺 | Already mandatory | No | Platform needed |
| Iceland 🇮🇸 | Voluntary (B2G since 2020) | No | Platform needed |
| Ireland 🇮🇪 | 2026 phased (ViDA) | No | Likely OK |
| Italy 🇮🇹 | Since 2019 | **Yes** | Platform needed |
| Latvia 🇱🇻 | Jan 2026 planned | No | Likely OK |
| Liechtenstein 🇱🇮 | Voluntary | No | Likely OK |
| Lithuania 🇱🇹 | Before Jul 2030 (voluntary) | No | Likely OK |
| Luxembourg 🇱🇺 | Voluntary | No | Likely OK |
| Malta 🇲🇹 | Planning (B2G mandatory) | No | Likely OK |
| Netherlands 🇳🇱 | Planning (B2G mandatory) | No | Likely OK |
| Norway 🇳🇴 | 2028 proposed (B2G since 2019) | No | Platform needed |
| Poland 🇵🇱 | Feb-Apr 2026 | No | Platform needed |
| Portugal 🇵🇹 | No B2B mandate | No | Likely OK |
| Romania 🇷🇴 | Since Jan 2024 | **Yes (2026)** | Platform needed |
| Slovakia 🇸🇰 | 2026 expected | No | Likely OK |
| Slovenia 🇸🇮 | Jun 2026 | No | Likely OK |
| Spain 🇪🇸 | 2026-2027 (phased) | No | Platform needed |
| Sweden 🇸🇪 | Planning (B2G mandatory) | No | Likely OK |
| Switzerland 🇨🇭 | Voluntary (B2G since 2016) | No | Likely OK |
| United Kingdom 🇬🇧 | Apr 2029 | No | Platform needed |

**Legend:**
- **Likely OK** = EN 16931 format (which Haiku.lt generates) should be accepted
- **Partial** = Some formats supported, others in development
- **Platform needed** = Requires government platform integration not yet available

## Future E-Invoicing Improvements

We're actively working to expand Haiku.lt's e-invoicing capabilities based on user demand:

**Critical Platform Integrations (2026 priorities)**:
- **Belgium Peppol** - Required for B2B transactions since January 2026
- **Poland KSeF** - Mandatory February-April 2026
- **Greece MyDATA** - Mandatory February 2026 for large companies

**Format Expansions**:
- **UBL 2.1 format support** - Required by Belgium, France, Spain, and UK (2029)
- **FatturaPA** - Italian format (mandatory since 2019)
- **Facturae** - Spanish B2G format

**Long-term ViDA Compliance** - As the EU finalizes its VAT in the Digital Age regulations targeting full implementation by 2030, we'll ensure Haiku.lt stays compliant with evolving requirements.

We're committed to making e-invoicing compliance as seamless as possible for our users. Our goal is to handle the technical complexity so you can focus on running your business.

## The Bottom Line

E-invoicing regulations can seem overwhelming, but here's what matters for most freelancers and small businesses:

1. **B2C invoicing remains simple.** If you invoice consumers, PDF invoices are valid in all European countries except Italy and Romania. No special e-invoicing required.

2. **B2B requirements vary by country.** Some countries accept EN 16931 formats (which Haiku.lt already generates), while others require specific government platforms (Belgium, Poland, Greece, Italy, Romania, Spain, Hungary).

3. **Haiku.lt is likely compliant** for Germany, Lithuania, Switzerland, Liechtenstein, and several other EU countries that accept EN 16931 formats. For countries like France that accept multiple formats, we're expanding support.

4. **EU+ coverage is promising.** Switzerland and Liechtenstein should work with Haiku.lt's current EN 16931-compliant implementation. Norway, Iceland, and UK will require Peppol integration in the future.

5. **We're continuously improving.** E-invoicing support will expand as we add new formats and platform integrations based on user demand.

For most users, Haiku.lt's current capabilities should be sufficient. Your invoices already contain structured data following European EN 16931 standards. As requirements evolve, we'll evolve with them.

Ready to create professional, compliant invoices? Get started at [haiku.lt](https://haiku.lt).
