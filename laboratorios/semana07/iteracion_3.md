[iteracion_3.md](https://github.com/user-attachments/files/33937486/iteracion_3.md)
# Iteración 3 — Rol + contexto + formato

- Modelo usado: PENDIENTE (debe ser el mismo en las seis iteraciones)
- Fecha de ejecución: PENDIENTE
- Regla: una conversación nueva para cada entrada

## Prompt (sustituye {ENTRADA} por el texto de entradas.md)

```text
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

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

## CALIFCACIÓN TOTAL DE LA ITERACIÓN

**Puntajes:** C1 = 2 | C2 = 2 | C3 = 1 | Total de la entrada = 5/6 puntos

**Observación (qué falló o qué cambió):** Las tres respuestas presentan la tabla de cinco filas y los campos solicitados. No obstante, asignan severidades sin señalar siempre la incertidumbre, especialmente en el segundo caso.
