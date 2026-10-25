# P04 — Clasificación de reportes de incidente (iteración 4)

## Objetivo
Clasificar un reporte de incidente escrito en texto libre en cinco campos (tipo, severidad, activo afectado, primera acción recomendada e información faltante), usando un ejemplo y una salida uniforme en Markdown.

## Modelo y configuración

- Modelo: PENDIENTE (no aparece especificado en la información disponible)
- Temperatura: PENDIENTE
- Fecha de ejecución: 2026-10-25

## Prompt (versión de la iteración 4)

Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

Ejemplo de entrada:

“Descargué un programa gratis para editar PDF desde una página que encontré en un buscador. Desde entonces mi laptop abre ventanas de publicidad y el antivirus me muestra una alerta que no entendí. Fue ayer por la tarde. La laptop es personal, pero la uso para revisar el correo del trabajo”.

Ejemplo de salida:

| Campo | Valor |
|---|---|
| Tipo de incidente | malware |
| Severidad | media |
| Activo afectado | laptop personal usada para el correo del trabajo |
| Primera acción recomendada | desconectar la laptop de la red, no abrir el correo del trabajo desde ella y avisar al área de seguridad |
| Información faltante | nombre del programa descargado; texto de la alerta del antivirus |

Responde únicamente con esta tabla en Markdown, sin texto adicional:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Si un campo no puede determinarse a partir del texto, escribe “NO ESPECIFICADO” en Valor y explica qué falta en la fila “Información faltante”.

## Resultado obtenido

Entrada utilizada:

“Hoy a las 9:40 recibí un correo que decía venir del soporte de TI de la empresa, con el asunto ‘Tu contraseña vence hoy’. Hice clic en el enlace y escribí mi usuario y contraseña del correo institucional en una página que se veía igual a la de la empresa. A los cinco minutos noté que la dirección del remitente era rara y cerré la página. Ya cambié mi contraseña desde mi celular. Trabajo en la laptop de la oficina y no he notado nada extraño en ella”.

Salida de la iteración 4:

| Campo | Valor |
|---|---|
| Tipo de incidente | phishing |
| Severidad | alta |
| Activo afectado | cuenta de correo institucional y credenciales de acceso |
| Primera acción recomendada | revocar las sesiones activas de la cuenta de correo institucional y verificar con TI/Seguridad si se requiere reiniciar el token de MFA o aplicar medidas adicionales tras el cambio de contraseña |
| Información faltante | dirección del remitente rara; enlace/URL exacta del sitio web falso; si la cuenta cuenta con autenticación de dos factores (MFA) |

## Verificación

| Afirmación verificable | Fuente primaria | Resultado | Clasificación |
|---|---|---|---|
| La salida contiene los cinco campos requeridos | Resultado de la iteración 4 | Sí, aparecen tipo, severidad, activo afectado, primera acción recomendada e información faltante | Cumple |
| La respuesta usa una tabla Markdown sin texto adicional | Resultado de la iteración 4 | Sí | Cumple |
| La respuesta identifica datos que faltan | Resultado de la iteración 4 | Sí; indica que faltan el remitente, la URL y la confirmación de MFA | Cumple parcialmente: reconoce datos faltantes, pero la evaluación global de incertidumbre de la iteración obtuvo 1/2 |

Este prompt no pide cifras, fechas ni leyes, así que la verificación se hace con la hoja de puntajes (tres criterios, escala 0 a 2) y no contra fuentes externas.

## Evaluación

Resumen de las puntuaciones disponibles:

| Iteración | Técnica | Total disponible |
|---|---|---:|
| 0 | Línea base | 0/6 |
| 1 | Rol | 1/6 |
| 2 | Rol + contexto | 3/6 |
| 3 | + formato | 5/6 |
| 4 | + ejemplos | 5/6 |
| 5 | + cadena de razonamiento | 4/6 |

**Nota sobre la escala:** la hoja de resultados disponible presenta puntuaciones sobre 6 por iteración. La plantilla original indica un máximo de 18, pero no se cuenta con el desglose de las puntuaciones de cada criterio para cada una de las tres entradas; por eso no se convierten a una escala de 18 para evitar inventar resultados.

- **Qué funcionó:** El ejemplo ayudó a mantener la estructura de la tabla y a completar los cinco campos. La iteración 4 obtuvo 5/6 puntos.
- **Qué falló:** En algunas respuestas se hicieron suposiciones no confirmadas, por ejemplo, sobre si el celular era personal o si tenía acceso a cuentas específicas. También se asignó severidad sin explicar siempre la incertidumbre.
- **Qué cambiaré en la siguiente versión:** Mantendré el ejemplo y la tabla fija, y reforzaré la instrucción de no presentar inferencias como hechos y de usar “NO ESPECIFICADO” cuando falte evidencia.

## Historial de versiones

| Versión | Fecha | Cambio realizado | Resultado del cambio |
|---|---|---|---|
| Iteración 4 | 2026-10-25 | Se agregó un ejemplo de entrada y salida, además de una tabla fija con cinco campos | La respuesta mantuvo el formato solicitado y obtuvo 5/6 puntos en la evaluación disponible |

## Datos usados

Las entradas del ejercicio se presentan como casos ficticios de ciberseguridad. No se incluyen datos personales reales.
