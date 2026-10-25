# Plantilla: clasificación de incidente v1

# Variables: {ROL_LECTOR}, {CATEGORIAS}, {SEVERIDADES}, {EJEMPLO_ENTRADA}, {EJEMPLO_SALIDA}, {ENTRADA}

```text
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es {ROL_LECTOR} y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: {CATEGORIAS}. Las severidades posibles son: {SEVERIDADES}.

Ejemplo de entrada:
{EJEMPLO_ENTRADA}

Ejemplo de salida:
{EJEMPLO_SALIDA}

Antes de la tabla, escribe una sección titulada "Análisis" con tres viñetas: qué información explícita hay en el texto, qué se puede inferir con seguridad y qué no se puede determinar.

Después escribe esta tabla en Markdown, sin otro texto adicional:

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

## Instrucciones de uso

**Qué poner en cada variable**

| Variable | Qué poner | Ejemplo |
|---|---|---|
| {ROL_LECTOR} | Quién leerá la respuesta | un técnico que atenderá el incidente |
| {CATEGORIAS} | Lista cerrada de tipos de incidente, separada por comas | acceso no autorizado, phishing, malware, pérdida de dispositivo, otro |
| {SEVERIDADES} | Lista cerrada de severidades | baja, media, alta |
| {EJEMPLO_ENTRADA} | Un reporte de ejemplo escrito por ti, de un caso distinto a los que vas a clasificar | el caso de malware de la iteración 4 |
| {EJEMPLO_SALIDA} | La tabla correcta para ese ejemplo | la tabla de la iteración 4 |
| {ENTRADA} | El reporte del usuario, pegado tal cual | texto libre de 4 a 8 líneas |

**Modelo que se probó:** GEMINI

**Puntaje que obtuvo:** 5/6 Puntos

**Limitaciones conocidas:**
- Solo se probó con cuatro textos ficticios en español, de un modelo y de una semana específica. PENDIENTE: agregar lo que observes (por ejemplo, si copia partes del ejemplo o si rompe el formato).
- La severidad depende del criterio del equipo; la plantilla no define cuándo un caso es "alta" y el modelo puede decidir distinto.
- Un cambio de versión del modelo puede cambiar los resultados; hay que volver a medir (ver reflexión 3 del reporte).
- Los reportes que el modelo clasifica deben revisarse por una persona antes de actuar.
