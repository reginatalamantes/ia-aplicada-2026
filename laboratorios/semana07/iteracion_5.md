# Iteración 5 — Rol + contexto + formato + ejemplos + cadena de razonamiento

- Modelo usado: PENDIENTE (debe ser el mismo en las seis iteraciones)
- Fecha de ejecución: PENDIENTE
- Regla: una conversación nueva para cada entrada

## Prompt (sustituye {ENTRADA} por el texto de entradas.md)

```text
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

Ejemplo de entrada:
"Descargué un programa gratis para editar PDF desde una página que encontré en un buscador. Desde entonces mi laptop abre ventanas de publicidad y el antivirus me muestra una alerta que no entendí. Fue ayer por la tarde. La laptop es personal, pero la uso para revisar el correo del trabajo."

Ejemplo de salida:
| Campo | Valor |
|---|---|
| Tipo de incidente | malware |
| Severidad | media |
| Activo afectado | laptop personal usada para el correo del trabajo |
| Primera acción recomendada | desconectar la laptop de la red, no abrir el correo del trabajo desde ella y avisar al área de seguridad |
| Información faltante | nombre del programa descargado; texto de la alerta del antivirus |

Antes de la tabla, escribe una sección titulada "Análisis" con tres viñetas: qué información explícita hay en el texto, qué se puede inferir con seguridad y qué no se puede determinar. Después escribe la tabla.

Responde con dos partes, en este orden y sin otro texto adicional. Primero la sección "Análisis" (ver arriba). Después esta tabla en Markdown:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Si un campo no puede determinarse a partir del texto, escribe "NO ESPECIFICADO" en Valor y explica qué falta en la fila "Información faltante".

Texto a clasificar:

{ENTRADA}
```

> Nota: en esta iteración cambié la frase "Responde únicamente con esta tabla" por una instrucción de dos partes, porque pedir "únicamente la tabla" y a la vez una sección de Análisis se contradicen. Es el único ajuste de redacción; la técnica nueva sigue siendo una sola (cadena de razonamiento).

## CALIFCACIÓN TOTAL DE LA ITERACIÓN

**Puntajes:** C1 = 0 | C2 = 0 | C3 = 1 | Total de la entrada = ⅙

**Observación (qué falló o qué cambió):** Los ejemplos ayudan a mantener la estructura y completar los campos. Aun así, algunas respuestas presentan como hechos ciertas características no confirmadas.
