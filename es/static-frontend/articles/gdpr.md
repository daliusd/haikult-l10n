---
title: 'RGPD - Tus derechos sobre datos'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt está comprometido con la protección de tus datos personales y el respeto de tus derechos de privacidad bajo el Reglamento General de Protección de Datos (RGPD). Esta página explica tus derechos y cómo manejamos tus datos.

## Tus derechos sobre datos

Bajo el RGPD, tienes los siguientes derechos con respecto a tus datos personales:

### Derecho de acceso

Tienes derecho a acceder a todos los datos personales que conservamos sobre ti. Puedes exportar tus datos en cualquier momento:

- **Exportación completa de base de datos**: Descarga tu base de datos completa incluyendo todas las facturas, configuraciones y registros de auditoría desde la configuración de tu cuenta.
- **Exportación de facturas**: Exporta tus facturas en formato CSV, filtradas por rango de fechas y nombre de serie.

### Derecho al olvido (Derecho a ser olvidado)

Tienes derecho a solicitar la eliminación de tus datos personales. Puedes eliminar toda tu cuenta y todos los datos asociados en cualquier momento a través de la configuración de tu cuenta. Esta acción es permanente y no se puede deshacer.

### Derecho a la portabilidad de datos

Puedes exportar tus datos en formatos legibles por máquina:

- Formato de base de datos SQLite (exportación completa de datos)
- Formato CSV (exportación de datos de facturas)

Esto te permite transferir tus datos a otro servicio si así lo decides.

### Derecho de rectificación

Tienes derecho a corregir datos personales inexactos o incompletos. Puedes editar todos tus datos directamente en la aplicación, incluyendo:

- Detalles de facturas
- Información del comprador y vendedor
- Tus preferencias y configuraciones personales

### Derecho a la restricción del procesamiento

Tienes derecho a solicitar la restricción del procesamiento de tus datos personales en ciertas circunstancias. Contáctanos usando el correo electrónico a continuación para ejercer este derecho.

### Derecho a oposición

Tienes derecho a oponerte al procesamiento de tus datos personales para fines específicos. Dado que Haiku.lt procesa tus datos únicamente para proporcionar el servicio de facturación que solicitaste, oponerte al procesamiento impediría que proporcionáramos el servicio.

## Retención de datos

Tus datos se conservan **hasta que elimines tu cuenta**. No eliminamos automáticamente las cuentas inactivas. Tienes control total sobre cuándo se eliminan tus datos.

Cuando eliminas tu cuenta, todos tus datos se eliminan permanentemente de nuestros sistemas.

## Responsable del tratamiento de datos

El responsable del tratamiento de datos para Haiku.lt es:

**Dalius Dobravolskas**

Para preguntas relacionadas con la privacidad o para ejercer tus derechos sobre datos, contacta:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Ubicación del servidor

Todos los servidores y almacenamiento de datos de Haiku.lt están ubicados en la **Unión Europea, específicamente en Alemania**. Tus datos no salen de la UE a menos que autorices explícitamente integraciones de terceros (ver Subprocesadores a continuación).

## Base legal para el procesamiento

Procesamos tus datos personales basándonos en:

- **Ejecución del contrato**: Para proporcionar el servicio de facturación para el que te registraste
- **Interés legítimo**: Para mantener la seguridad del servicio, prevenir fraudes y mejorar el servicio
- **Consentimiento**: Para funciones opcionales como la integración con Google Drive y Gmail

## Subprocesadores

Haiku.lt utiliza los siguientes servicios de terceros para proporcionar nuestra funcionalidad:

### Google LLC

**Servicios utilizados**: Autenticación OAuth 2.0, API de Google Drive, API de Gmail, API de Google Calendar

**Datos compartidos**: Dirección de correo electrónico, nombre, tokens OAuth (solo cuando autorizas la integración con Google)

**Propósito**: Para permitirte:
- **Autenticarse** con tu cuenta de Google usando OAuth 2.0
- **Google Drive** (alcance: `drive.file`): Guardar PDFs de facturas en tu Drive en carpetas organizadas (Haiku.lt/Facturas/Año). Solo podemos acceder a archivos creados por nuestra aplicación, no a tus otros archivos de Drive. Almacenamos IDs de archivos de Drive para rastrear facturas guardadas.
- **Gmail** (alcance: `gmail.send`): Enviar correos electrónicos de facturas a compradores en tu nombre. No leemos tu bandeja de entrada ni correos electrónicos existentes. Los correos enviados aparecen en tu carpeta "Enviados" de Gmail.
- **Google Calendar** (alcance: `calendar.readonly`, opcional): Leer títulos de eventos de calendario, fechas, horas y estado de asistencia para ayudar a crear facturas. Estos datos se obtienen temporalmente y no se almacenan permanentemente.

**Retención de datos**: 
- IDs de archivos de Drive: Almacenados en nuestra base de datos hasta que elimines la factura o desconectes tu cuenta de Google
- Datos de Calendar: No almacenados (obtenidos solo bajo demanda)
- Datos de Gmail: No almacenados (los correos permanecen en tu cuenta de Gmail)
- Tokens OAuth: Encriptados y almacenados hasta que desconectes tu cuenta

**Política de privacidad**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Ubicación**: Estados Unidos (con cumplimiento del Marco de Privacidad de Datos UE-EE.UU.)

### Stripe, Inc.

**Servicios utilizados**: Procesamiento de pagos para suscripciones

**Datos compartidos**: Dirección de correo electrónico, información de pago (manejada directamente por Stripe)

**Propósito**: Para procesar pagos de suscripción para funciones premium

**Política de privacidad**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Ubicación**: Estados Unidos (con cumplimiento del Marco de Privacidad de Datos UE-EE.UU.)

### Brevo (Sendinblue)

**Servicios utilizados**: Entrega de correos electrónicos transaccionales

**Datos compartidos**: Dirección de correo electrónico del destinatario, contenido del correo (tokens de enlace mágico para inicio de sesión; detalles de factura al enviar facturas a través de Brevo)

**Propósito**: Para entregar correos electrónicos de autenticación (inicio de sesión por enlace mágico) y correos electrónicos de facturas a compradores

**Retención de datos**: Brevo puede conservar registros de correos enviados por un período limitado según su política. No almacenamos el contenido del correo en nuestros servidores más allá de lo necesario para enviarlo.

**Política de privacidad**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Ubicación**: Unión Europea (Francia)

## Seguridad de datos

Tomamos medidas técnicas y organizativas apropiadas para proteger tus datos personales:

- Encriptación de datos sensibles (tokens OAuth, tokens de actualización)
- Conexiones HTTPS seguras
- Cookies de autenticación HTTP-only y seguras
- Actualizaciones regulares de software
- Aislamiento de base de datos por usuario
- Registro de auditoría para seguimiento de acceso a cuentas

## Notificación de violación de datos

En el caso improbable de una violación de datos que represente un riesgo para tus derechos y libertades, te notificaremos a ti y a la autoridad supervisora relevante dentro de las 72 horas según lo requerido por el RGPD.

## Autoridad supervisora

Si tienes inquietudes sobre cómo manejamos tus datos personales, tienes derecho a presentar una queja ante tu autoridad local de protección de datos.

## Actualizaciones de esta política

Podemos actualizar esta página de información del RGPD de vez en cuando. La fecha de "modificación" en la parte superior de esta página indica cuándo se actualizó por última vez.

Para información general de privacidad, consulta nuestra [Política de privacidad](/es/privacy).
