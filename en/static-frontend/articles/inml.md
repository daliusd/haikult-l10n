---
title: 'Invoice Markup Language (InML)'
date: '2026-02-22'
modified: '2026-02-22'
---

InML (Invoice Markup Language) is an XML-based template language for defining
custom invoice PDF layouts in Haiku.lt. It gives you full control over the
structure, styling, and content of your invoices.

You can select one of the five built-in styles as a starting point and
customize it, or write a template from scratch.

## Basic Structure

Every InML template starts with an `<inml>` root element:

```xml
<inml version="1.0" page-size="A4" margin="20mm"
      font-regular="Roboto-Light" font-bold="Roboto-Medium">
  <page>
    <!-- elements drawn on every page -->
  </page>
  <layout>
    <!-- content regions -->
  </layout>
</inml>
```

### Root Attributes

| Attribute      | Description                                       |
| -------------- | ------------------------------------------------- |
| `version`      | InML version. Currently `1.0`.                    |
| `page-size`    | Page format. Currently only `A4` is supported.    |
| `margin`       | Default page margin (e.g. `20mm`).                |
| `font-regular` | Font used for regular text (e.g. `Roboto-Light`). |
| `font-bold`    | Font used for bold text (e.g. `Roboto-Medium`).   |

## Units

All dimensions use millimeters (`mm`) or points. Write values like `20mm`,
`5mm`, `210mm`. Font sizes are specified as plain numbers in points
(e.g. `font-size="12"`).

## Page Elements

The `<page>` section defines elements drawn on **every page** of the PDF,
behind the main content. Use it for background images, decorative rectangles,
or lines.

```xml
<page>
  <image src="{{background}}" x="0mm" y="0mm" width="210mm" height="297mm" />
  <rect x="0mm" y="0mm" width="210mm" height="30mm" fill="#f1f5f9" />
  <line x1="20mm" y1="50mm" x2="190mm" y2="50mm" color="#cccccc" width="0.5mm" />
</page>
```

### Available Page Elements

- **`<image>`** — background image. Attributes: `src`, `x`, `y`, `width`,
  `height`.
- **`<rect>`** — rectangle. Attributes: `x`, `y`, `width`, `height`, `fill`,
  `stroke`, `stroke-width`.
- **`<line>`** — line. Attributes: `x1`, `y1`, `x2`, `y2`, `color`, `width`.

## Layout and Regions

The `<layout>` section contains one or more `<region>` elements. Each region
is an independent content area with its own positioning mode.

```xml
<layout>
  <region id="header" flow="fixed" margin-top="5mm"
          margin-left="20mm" content-width="170mm">
    <!-- content -->
  </region>
  <region id="body" flow="sequential" margin-top="20mm">
    <!-- content -->
  </region>
</layout>
```

### Region Attributes

| Attribute       | Description                                                                   |
| --------------- | ----------------------------------------------------------------------------- |
| `id`            | Unique identifier for the region.                                             |
| `flow`          | Positioning mode: `sequential`, `absolute`, or `fixed`.                       |
| `margin-left`   | Horizontal offset from the page edge.                                         |
| `content-width` | Override the content width for this region.                                    |
| `margin-top`    | Vertical offset. For `sequential` regions, adds space above the region.       |
| `min-height`    | Minimum height reserved for the region, even if content is shorter.           |

### Flow Modes

- **`sequential`** — regions flow one after another, top to bottom. This is the
  most common mode for body content.
- **`absolute`** — positioned at a specific location, calculated from the
  current vertical position. Subsequent sequential regions continue after it.
- **`fixed`** — positioned at a fixed location on the page, independent of
  other regions. Useful for headers or overlays.

### Layout Columns

To place regions side by side, wrap them in a `<columns>` element at the
layout level:

```xml
<layout>
  <columns>
    <column margin-left="20mm" content-width="80mm">
      <region id="left" flow="sequential">
        <!-- left content -->
      </region>
    </column>
    <column content-width="80mm">
      <region id="right" flow="sequential">
        <!-- right content -->
      </region>
    </column>
  </columns>
</layout>
```

Each `<column>` can have `margin-left` and `content-width` attributes, and
contains one or more `<region>` elements.

## Content Elements

Content elements are placed inside regions. All content elements share these
optional attributes:

| Attribute       | Description                                             |
| --------------- | ------------------------------------------------------- |
| `font`          | `regular` or `bold`.                                    |
| `font-size`     | Font size in points (e.g. `12`).                        |
| `color`         | Text or fill color (e.g. `#333333`).                    |
| `align`         | Text alignment: `left`, `right`, or `center`.           |
| `margin-top`    | Space above the element.                                |
| `margin-bottom` | Space below the element.                                |

### `<logo>`

Displays the company logo image, preserving aspect ratio.

```xml
<logo src="{{logo}}" width="50mm" ratio="{{logoRatio}}" />
```

| Attribute | Description                                            |
| --------- | ------------------------------------------------------ |
| `src`     | Image data (use `{{logo}}` template variable).         |
| `width`   | Display width.                                         |
| `height`  | Optional fixed height.                                 |
| `ratio`   | Aspect ratio (use `{{logoRatio}}` template variable).  |

### `<title>`

Heading text, typically used for the invoice title.

```xml
<title font="bold" font-size="14" align="center">{{invoiceTitle}}</title>
```

### `<text>`

Regular text content.

```xml
<text font="regular" font-size="12">{{seller}}</text>
```

### `<columns>` and `<column>`

Arrange content side by side within a region.

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

Each `<column>` has a `width` attribute as a percentage (e.g. `50%`) and an
optional `align` attribute.

### `<stack>` and `<group>`

Vertically stacked groups of content with configurable spacing between them.

```xml
<stack spacing="10mm">
  <group>
    <text font="bold" font-size="12">First Section</text>
    <text font="regular" font-size="12">Content here</text>
  </group>
  <group>
    <text font="bold" font-size="12">Second Section</text>
    <text font="regular" font-size="12">More content</text>
  </group>
</stack>
```

The `spacing` attribute controls the vertical gap between groups.

### `<box>`

A bordered/padded container for content.

```xml
<box stroke="#cccccc" padding="5mm">
  <text font="regular" font-size="12">Boxed content</text>
</box>
```

| Attribute | Description                   |
| --------- | ----------------------------- |
| `stroke`  | Border color.                 |
| `padding` | Inner padding.                |
| `height`  | Optional fixed height.        |

### `<rect>`

A rectangle shape within content flow.

```xml
<rect width="170mm" height="1mm" fill="#238c83" />
```

| Attribute | Description        |
| --------- | ------------------ |
| `width`   | Rectangle width.   |
| `height`  | Rectangle height.  |
| `fill`    | Fill color.        |
| `stroke`  | Border color.      |

### `<image>`

An inline image within content flow.

```xml
<image src="{{logo}}" width="50mm" height="20mm" />
```

### `<spacer>`

Adds vertical space between elements.

```xml
<spacer height="10mm" />
```

### `<invoice-table>`

The line items table. This is the core element for displaying invoice items
with columns and a summary section.

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

#### Table Attributes

| Attribute                | Description                                                                     |
| ------------------------ | ------------------------------------------------------------------------------- |
| `row-style`              | Row styling: `minimal`, `striped`, `bordered`, or `colored-header`.             |
| `cell-padding`           | Padding inside each cell.                                                       |
| `separator-after-header` | Show a line after the header row (`true`/`false`).                              |
| `separator-after-items`  | Show a line after all items (`true`/`false`).                                   |
| `separator-color`        | Color of separator lines.                                                       |
| `separator-width`        | Thickness of separator lines.                                                   |
| `stripe-color`           | Background color for alternating rows (when using `striped` style).             |
| `header-bg-color`        | Header background color (when using `colored-header` style).                    |
| `header-text-color`      | Header text color (when using `colored-header` style).                          |
| `header-extra-padding`   | Additional padding for the header row.                                          |

#### Column Definitions

Each `<col>` defines a table column:

| Attribute | Description                                                                          |
| --------- | ------------------------------------------------------------------------------------ |
| `name`    | Column identifier: `id`, `name`, `unit`, `amount`, `price`, `vat`, `vat_sum`, `total`. |
| `label`   | Column header text (use template variables for translations).                        |
| `width`   | Column width.                                                                        |
| `align`   | Text alignment: `left`, `right`, or `center`.                                        |

For VAT payers, you typically include the extra `vat` and `vat_sum` columns.
Use `{{#if vatpayer}}` to conditionally show them.

#### Summary Rows

The `<summary>` section defines totals displayed below the table:

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

## Template Variables

InML uses [Handlebars](https://handlebarsjs.com/) syntax for dynamic content.
Variables are inserted with `{{variableName}}` and conditional blocks with
`{{#if variableName}}...{{/if}}`.

### Available Variables

#### Invoice Data

| Variable              | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| `invoiceTitle`        | Resolved invoice title based on type and VAT status.         |
| `seriesName`          | Invoice series name.                                         |
| `seriesId`            | Invoice number within the series.                            |
| `formattedDate`       | Formatted invoice date.                                      |
| `seller`              | Seller information.                                          |
| `buyer`               | Buyer information.                                           |
| `issuer`              | Person who issued the invoice.                               |
| `extra`               | Additional information text.                                 |

#### Price Fields

| Variable              | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| `total`               | Total invoice amount (formatted).                            |
| `totalWithoutVat`     | Total without VAT (formatted).                               |
| `vatTotal`            | VAT amount (formatted).                                      |
| `alreadyPaid`         | Amount already paid (number, for use in `{{#if}}`).          |
| `alreadyPaidFormatted`| Amount already paid (formatted string).                      |
| `sumToPay`            | Remaining amount to pay (formatted).                         |
| `priceInWords`        | Total price written out in words (if available).             |
| `priceColumnLabel`    | Label for the price column (changes for VAT payers).         |

#### Flags

| Variable    | Description                                                        |
| ----------- | ------------------------------------------------------------------ |
| `vatpayer`  | `true` if the seller is a VAT payer. Use with `{{#if vatpayer}}`.  |

#### Colors

| Variable                   | Description                             |
| -------------------------- | --------------------------------------- |
| `colors.headerBackground`  | Header background color (default `#f1f5f9`). |
| `colors.primaryAccent`     | Primary accent color (default `#238c83`).     |

#### Images

| Variable    | Description                                         |
| ----------- | --------------------------------------------------- |
| `logo`      | Company logo image data. Use with `{{#if logo}}`.   |
| `logoRatio` | Logo aspect ratio (use in `<logo ratio="...">`).    |
| `background`| Background image data. Use with `{{#if background}}`. |

#### Translation Strings

All UI labels are available through the `t` object. Common ones include:

| Variable                         | Description          |
| -------------------------------- | -------------------- |
| `t.invoice.seller`               | "Seller" label       |
| `t.invoice.buyer`                | "Buyer" label        |
| `t.invoice.no`                   | "No." label          |
| `t.invoice.total`                | "Total" label        |
| `t.invoice.total_without_vat`    | "Total without VAT"  |
| `t.invoice.vat`                  | "VAT" label          |
| `t.invoice.lineItemNo`           | "No." column header  |
| `t.invoice.lineItemName`         | "Name" column header |
| `t.invoice.lineItemUnit`         | "Unit" column header |
| `t.invoice.lineItemAmount`       | "Amount" column header |
| `t.invoice.lineItemPrice`        | "Price" column header |
| `t.invoice.lineItemPriceWithoutVAT` | "Price (excl. VAT)" |
| `t.invoice.lineItemVat`          | "VAT %" header       |
| `t.invoice.lineItemVatSum`       | "VAT amount" header  |
| `t.invoice.lineItemSum`          | "Sum" column header  |
| `t.invoice.alreadyPaid`          | "Already paid" label |
| `t.invoice.sumToPay`             | "Sum to pay" label   |
| `t.invoice.sumInWords`           | "Sum in words" label |
| `t.invoice.invoiceIssuedBy`      | "Invoice issued by"  |
| `t.metadata.series`              | "Series" label       |

## Built-in Styles

Haiku.lt includes five built-in styles you can use as starting points:

- **minimalist** — clean design with centered title and minimal separators
- **modern-accent** — colored header bar with accent colors
- **left-aligned** — left-aligned layout with simple structure
- **bordered** — bordered table rows and sections
- **split-column** — two-column layout separating seller and buyer info

Select a built-in style in invoice settings, then switch to custom InML to
use it as a base for your modifications.

## Complete Example

Here's a simplified template showing the key InML concepts:

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
