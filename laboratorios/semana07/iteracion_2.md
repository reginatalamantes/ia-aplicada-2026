# Iteración 2 — Rol + contexto

- Modelo usado: PENDIENTE (debe ser el mismo en las seis iteraciones)
- Fecha de ejecución: PENDIENTE
- Regla: una conversación nueva para cada entrada

## Prompt (sustituye {ENTRADA} por el texto de entradas.md)

```text
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

Clasifica este reporte de incidente:

{ENTRADA}
```

## CALIFCACIÓN TOTAL DE LA ITERACIÓN

**Puntajes:** C1 = 0 | C2 = 0 | C3 = 1 | Total de la entrada = ⅙

**Observación (qué falló o qué cambió):** El rol mejora el lenguaje técnico y las recomendaciones, pero no garantiza los campos ni el formato. La segunda respuesta identifica información faltante, aunque persisten suposiciones en otras respuestas.
