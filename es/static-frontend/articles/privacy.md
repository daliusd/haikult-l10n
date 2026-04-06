---
title: 'Política de privacidad'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Esta Política de privacidad describe cómo Haiku.lt recopila y utiliza los datos.

## Datos que recopilamos

- Dirección IP, fecha y hora, información del navegador.

- Dirección de correo electrónico.

- Datos que ingresas en el sistema mientras lo usas.

## Cookies y almacenamiento del navegador

Usamos cookies y almacenamiento del navegador para proporcionar funcionalidad esencial:

### Cookies

- **Cookie de autenticación (auth_token)**: Una cookie segura de solo HTTP utilizada para mantener tu sesión de inicio de sesión. Esta cookie es esencial para que el servicio funcione y expira después de aproximadamente 2 meses. Sin esta cookie, no puedes usar Haiku.lt.

### Almacenamiento local del navegador

Almacenamos los siguientes datos en el almacenamiento local de tu navegador:

- **Preferencia de idioma**: Tu idioma de interfaz seleccionado (inglés, lituano o español) para proporcionar renderizado inmediato de la interfaz.

- **Descarte de notificaciones**: Registra si has descartado ciertas notificaciones para evitar mostrarlas repetidamente.

- **Sincronización de cambio de cuenta**: Datos temporales (eliminados después de 1 segundo) utilizados para sincronizar el cambio de cuenta entre múltiples pestañas del navegador.

### Almacenamiento de sesión del navegador

- **Seguimiento de visitas**: Una bandera de solo sesión para evitar bucles de redirección en la página de inicio. Estos datos se eliminan cuando cierras tu navegador.

### Sin seguimiento de terceros

No utilizamos cookies de análisis, publicidad o seguimiento de terceros. Todas las cookies y almacenamiento son estrictamente necesarios para que el servicio funcione.

## Servicios de terceros

- **Servicios de Google**: Integramos con los servicios de Google cuando te conectas a través de OAuth de Google:

  - **Google Drive** (opcional): Si otorgas permiso de Google Drive, accedemos a:
    - **A qué accedemos**: Archivos creados por Haiku.lt en tu Google Drive. Usamos el alcance `drive.file` que proporciona acceso solo a archivos creados por nuestra aplicación; no podemos ver ni acceder a ningún otro archivo en tu Drive.
    - **Cómo lo usamos**: Para guardar PDFs de facturas en tu Google Drive en una estructura de carpetas organizada (Haiku.lt/Facturas/Año). Cuando usas la función "Guardar en Drive", creamos o actualizamos archivos PDF.
    - **Cómo lo almacenamos**: Almacenamos el ID de archivo de Google Drive en nuestra base de datos para rastrear qué facturas se han guardado y permitir actualizaciones de archivos existentes. El contenido real del PDF no se almacena en nuestros servidores; existe solo en tu Google Drive.
    - **Cómo lo compartimos**: Los IDs de archivos de Google Drive nunca se comparten con terceros, nunca se venden a intermediarios de datos y nunca se utilizan para publicidad, marketing, entrenamiento de IA o ningún propósito que no sea gestionar tus PDFs de facturas en tu Drive.
    - **Cómo controlarlo**: Puedes gestionar los permisos de Drive a través de tus [permisos de cuenta de Google](https://myaccount.google.com/permissions). Los archivos permanecen en tu Drive bajo tu control. Puedes eliminarlos en cualquier momento. Revocar el acceso detiene nuestra capacidad de crear nuevos archivos o actualizar los existentes.
  
  - **Gmail** (opcional): Si otorgas permiso de Gmail, accedemos a:
    - **A qué accedemos**: Permiso para enviar correos electrónicos a través de tu cuenta de Gmail. Usamos el alcance `gmail.send` que permite enviar correos electrónicos en tu nombre. No leemos tus correos electrónicos existentes ni accedemos a tu bandeja de entrada.
    - **Cómo lo usamos**: Para enviar correos electrónicos de facturas a tus compradores cuando usas la función "Enviar factura". Los correos electrónicos incluyen el PDF de la factura como archivo adjunto y archivos adjuntos adicionales opcionales (como XML CII para facturación electrónica).
    - **Cómo lo almacenamos**: No almacenamos contenido de correo electrónico ni datos de mensajes enviados. Los correos electrónicos enviados aparecen en tu carpeta "Enviados" de Gmail bajo tu control.
    - **Cómo lo compartimos**: La capacidad de envío de correo electrónico nunca se comparte con terceros, nunca se vende y nunca se utiliza para publicidad, marketing, spam o ningún propósito que no sea enviar facturas que elijas enviar explícitamente.
    - **Cómo controlarlo**: Puedes gestionar los permisos de Gmail a través de tus [permisos de cuenta de Google](https://myaccount.google.com/permissions). Los correos electrónicos enviados permanecen en tu cuenta de Gmail. Revocar el acceso detiene nuestra capacidad de enviar correos electrónicos en tu nombre.
  
  - **Google Calendar** (opcional, solo lectura): Si otorgas permiso de calendario, accedemos a:
    - **A qué accedemos**: Tus nombres de calendario, títulos de eventos, fechas/horas de eventos y estado de asistencia (para filtrar eventos rechazados). Usamos el alcance de API de Google Calendar `calendar.readonly` que proporciona acceso de solo lectura.
    - **Cómo lo usamos**: Exclusivamente para ayudarte a crear facturas basadas en eventos de calendario a través de la función "Crear desde calendario". Los títulos de eventos se convierten en descripciones de artículos de línea de factura, y las fechas de eventos ayudan a establecer rangos de fechas de factura.
    - **Cómo lo almacenamos**: Los datos de calendario **no se almacenan permanentemente** en nuestras bases de datos. Se obtienen bajo demanda solo cuando usas la función de factura de calendario y existen temporalmente en la memoria de tu navegador durante el proceso de creación de facturas.
    - **Cómo lo compartimos**: Los datos de calendario **nunca se comparten** con terceros, **nunca se venden** a intermediarios de datos y **nunca se utilizan** para publicidad, marketing, entrenamiento de IA o ningún propósito que no sea crear facturas para ti.
    - **Cómo controlarlo**: Puedes gestionar los permisos de calendario de forma independiente a través de tus [permisos de cuenta de Google](https://myaccount.google.com/permissions). Revocar el acceso detiene el acceso a datos de inmediato. También puedes desconectar toda tu cuenta de Google a través de la configuración de Haiku.lt.
    
  Todos los permisos de OAuth de Google requieren tu autorización explícita. Controlas qué permisos otorgar y puedes revocarlos en cualquier momento.

- **Stripe**: Usamos Stripe para el procesamiento de pagos de suscripciones premium. Stripe maneja toda la información de pago de forma segura según su política de privacidad. Solo recibimos confirmación de pagos exitosos.

- **Brevo (Sendinblue)**: Usamos Brevo para entregar correos electrónicos transaccionales, incluyendo correos de inicio de sesión por enlace mágico y correos de facturas. Brevo recibe la dirección de correo electrónico del destinatario y el contenido del correo necesario para entregar estos mensajes. Brevo está ubicado en la UE (Francia). Consulta su [Política de privacidad](https://www.brevo.com/legal/privacypolicy/).

## Protección de datos

Para proteger los datos recopilados, tomamos las siguientes medidas:

- Actualizar el software del servidor con la mayor frecuencia posible.

- Actualizar el software de Haiku.lt con la mayor frecuencia posible.

- Configurar adecuadamente los servidores.

## Tus derechos

Para información detallada sobre tus derechos de datos bajo el RGPD, incluido el derecho a acceder, eliminar y exportar tus datos, consulta nuestra [página de RGPD](/es/gdpr).
