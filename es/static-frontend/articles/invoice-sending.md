---
title: 'Envío de facturas'
date: '2021-04-15'
modified: '2026-03-28'
---

Después de crear una factura, necesitas entregarla al comprador. Un método conveniente es enviar el PDF por correo electrónico, y Haiku.lt puede ayudarte con esto.

Haiku.lt admite dos formas de enviar correos electrónicos:

## 1. Elegir un método de envío de correo electrónico

### Gmail (OAuth)

Si iniciaste sesión con Google, Haiku.lt puede enviar correos electrónicos directamente
desde tu cuenta de Gmail usando OAuth seguro — no se requiere compartir contraseña.
Al iniciar sesión, debes otorgar permiso para enviar correos electrónicos en tu nombre.
Si no lo hiciste inicialmente, cierra sesión y vuelve a iniciar sesión.

### SMTP

También puedes enviar correos electrónicos a través de cualquier servidor SMTP. Esto funciona con cualquier
proveedor de correo electrónico y es la única opción para usuarios que no usan Gmail.

Para configurar SMTP, ve a [Configuración → Configuración del proveedor de correo electrónico](/app/settings/email-provider):

1. Si usas inicio de sesión de Gmail, selecciona **SMTP** como método de envío.
2. Elige una **preconfiguración de proveedor** para rellenar automáticamente la configuración del servidor:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun o Personalizado
3. Completa los detalles de SMTP:
   - **Host** — dirección del servidor SMTP (p. ej., `smtp.gmail.com`)
   - **Puerto** — generalmente 587 (STARTTLS) o 465 (SSL/TLS)
   - **Seguridad** — STARTTLS actualiza una conexión sin cifrar a cifrada; SSL/TLS está cifrado desde el inicio
   - **Nombre de usuario** — tu dirección de correo electrónico
   - **Contraseña** — tu contraseña de correo electrónico o contraseña específica de la aplicación
   - **Dirección de remitente** — la dirección del remitente mostrada a los destinatarios (p. ej., `Nombre de empresa <tu@example.com>`)
4. Haz clic en **Probar conexión** para verificar tu configuración antes de guardar.
5. Haz clic en **Guardar configuración SMTP**.

## 2. Configuración de correo electrónico

En [Configuración](/app/settings) puedes configurar:

### Asunto del correo electrónico

Personaliza la línea de asunto del correo electrónico según tus necesidades. Puedes usar estas variables:
- `{{invoiceNo}}` - número de factura (por ejemplo, INV/001)
- `{{buyer}}` - nombre del comprador
- `{{seller}}` - nombre del vendedor
- `{{price}}` - monto de la factura con moneda
- `{{invoiceDate}}` - fecha de la factura

### Plantillas de correo electrónico

Elige entre estas plantillas:

**Texto plano** - formato de texto simple que funciona perfectamente en todos los clientes de correo electrónico.

**HTML simple** - correo electrónico con formato HTML hermoso usando la tecnología [MJML](https://mjml.io/).

**Con logotipo** - plantilla HTML con el logotipo de tu empresa en la parte superior.

**Con logotipo y precio** - además muestra el monto de la factura en el correo electrónico.

**Con logotipo, precio e información adicional** - también muestra información adicional.

**Con logotipo, precio y nota de email** - incluye una nota opcional que puedes escribir antes de enviar.

**Con líneas de artículo** - muestra una tabla completa de las líneas de la factura (nombre, cantidad, precio unitario, total) junto con el total general.

Las plantillas HTML usan el formato [MJML](https://mjml.io/), que garantiza que los correos electrónicos se vean geniales en todos los clientes de correo electrónico. Si deseas crear tu propia plantilla o modificar una existente, puedes pedir ayuda a la IA: solo describe cómo deseas que se vea tu correo electrónico, y la IA puede generar el código MJML por ti.

### Variables de plantilla

En todas las plantillas puedes usar estos valores:

**Información básica:**
- `{{issuer}}` - persona que creó la factura
- `{{invoiceNo}}` - número de factura
- `{{buyer}}` - comprador
- `{{seller}}` - vendedor
- `{{price}}` - monto de la factura
- `{{extra}}` - información adicional
- `{{userNote}}` - tu nota
- `{{emailNote}}` - nota en el correo electrónico (ingresada durante el envío)
- `{{email}}` - correo electrónico del comprador

**Fechas:**
- `{{invoiceDate}}` - fecha de la factura
- `{{created}}` - fecha de creación de la factura (igual que invoiceDate)

**Detalles de la factura:**
- `{{seriesName}}` - nombre de serie de la factura (por ejemplo, "INV")
- `{{seriesId}}` - número en la serie (por ejemplo, "001")
- `{{language}}` - idioma de la factura ("lt" o "en")

**Logotipo:**
- `{{logoUrl}}` - URL del logotipo

**Colores de marca:**
- `{{brandPrimary}}` - color primario
- `{{brandSecondary}}` - color secundario
- `{{brandText}}` - color del texto
- `{{brandTextSecondary}}` - color de texto secundario
- `{{brandBackground}}` - color de fondo
- `{{bodyBackground}}` - color de fondo de página
- `{{backgroundSecondary}}` - color de fondo secundario

### Líneas de Artículo

Puedes iterar sobre las líneas de la factura usando Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Cada línea de artículo expone:
- `{{name}}` - nombre del artículo
- `{{amount}}` - cantidad
- `{{unit}}` - código de unidad UN/ECE sin procesar (p. ej., `H87`)
- `{{unitName}}` - forma larga de la unidad, localizada (p. ej., "unidad", "kilogramo")
- `{{unitSymbol}}` - forma corta de la unidad, localizada (p. ej., "ud", "kg")
- `{{unitPrice}}` - precio formateado por unidad (p. ej., "€10,00")
- `{{formattedPrice}}` - total de línea formateado — cantidad × precio unitario (p. ej., "€30,00")
- `{{vat}}` - porcentaje de IVA (si está definido)
- `{{vatcode}}` - código de IVA (si está definido)

### Plantillas condicionales

Puedes usar condiciones de Handlebars para mostrar contenido solo cuando existe un valor:

```
{{#if extra}}
  <mj-text>Información adicional: {{extra}}</mj-text>
{{/if}}
```

Esto es especialmente útil cuando deseas mostrar un bloque de información adicional solo cuando realmente está completado.

### Colores de marca y logotipo

En la configuración también puedes:
- Subir tu logotipo
- Cambiar colores de marca

## 3. Envío de la factura

1. Especifica la dirección de correo electrónico del comprador en la factura
2. Haz clic en el botón "Enviar factura"
3. La factura se marcará como bloqueada y se enviará

La factura se enviará desde tu cuenta de Gmail usando la plantilla seleccionada.
