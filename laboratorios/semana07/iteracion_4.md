# Iteración 4 — Rol + contexto + formato + ejemplos (few-shot)

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

Responde únicamente con esta tabla en Markdown, sin texto adicional:

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

> Nota: el ejemplo (malware) es un caso distinto a las entradas 1 a 3 para evitar que el modelo copie partes de él. Lo redacté con mi propio criterio de severidad; revísalo y ajústalo antes de usarlo.

## CALIFCACIÓN TOTAL DE LA ITERACIÓN

**Puntajes:** C1 = 2 | C2 = 2 | C3 = 1 | Total de la entrada = ⅙

**Observación (qué falló o qué cambió):** Los ejemplos ayudan a mantener la estructura y completar los campos. Aun así, algunas respuestas presentan como hechos ciertas características no confirmadas.
