---
title: 'Sus datos están cifrados: Por qué es importante'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Todas las bases de datos de usuarios de Haiku.lt están encriptadas en reposo. Esto es lo que realmente significa y por qué debería importarte.

## Qué significa la encriptación (simplemente)

Imagine sus facturas y datos de clientes como un diario. El cifrado bloquea ese diario y convierte cada palabra en un galimatías aleatorio. Sin la clave, quien tenga el diario en sus manos no verá más que ruido — `X7k#mQ2$pL9@vR4...` — completamente ilegible.

La base de datos de cada usuario recibe una clave única, y Haiku.lt nunca almacena esa clave en texto plano.

## El escenario de la copia de seguridad

Haiku.lt hace copias de seguridad periódicas para protegerse contra la pérdida de datos. Ahora imagine el peor de los casos: un hacker de alguna manera se hace con uno de esos archivos de copia de seguridad.

¿Qué es lo que tienen? Un archivo lleno de galimatías. Sin la clave de cifrado, la copia de seguridad carece de valor para ellos. No pueden leer los nombres de los clientes, los importes de las facturas ni ningún otro dato.

## ¿Qué tan fuerte es «encriptado»?

Haiku.lt utiliza encriptación AES-256 — el mismo estándar utilizado por bancos y gobiernos de todo el mundo. Para forzar una clave AES-256, un atacante tendría que probar 2²⁵⁶ combinaciones posibles.

Incluso con todos los ordenadores de la Tierra funcionando a pleno rendimiento, descifrar una sola clave AES-256 llevaría más tiempo que la edad actual del universo. No es un ataque práctico.

## En resumen

Si alguna vez robaran las copias de seguridad de Haiku.lt, sus datos seguirían protegidos. El cifrado garantiza que la posesión física de un archivo de copia de seguridad carece de sentido sin la clave de cifrado.

Sus facturas son su negocio. Deben seguir siendo suyas.
