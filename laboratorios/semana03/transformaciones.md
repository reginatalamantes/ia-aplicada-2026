# Transformaciones — Semana 3

## 1. Tabla de transformaciones (Paso 5.1)

| Columna original | Qué le hicimos | Técnica | Por qué |
|---|---|---|---|
| nombre | Sustituida por `id_persona` (código estable P001, P002...) | Seudonimización | Identificador directo; se necesitaba distinguir personas sin exponer su identidad real |
| correo | Eliminada por completo | Eliminación | No aporta al análisis de patrones de acceso; solo es dato de contacto |
| telefono | Eliminada por completo | Eliminación | No aporta al análisis de patrones de acceso; solo es dato de contacto |
| fecha_acceso | Sustituida por `semana` (número de semana del año) | Generalización | Reduce la precisión temporal; sigue permitiendo detectar patrones sin exponer el día exacto |
| hora_entrada | Sustituida por `franja` (Madrugada/Mañana/Tarde/Noche) | Generalización | Reduce la precisión horaria conservando la información necesaria para detectar accesos inusuales |
| empresa | Sustituida por `tipo_empresa` (agrupado por giro) | Generalización | Reduce el riesgo de identificar a la persona por empresa específica, conservando el contexto organizacional |
| area | Se conserva tal cual | Conservación | Necesaria para el análisis de patrones; por sí sola no identifica a nadie |
| motivo | Se conserva tal cual | Conservación | Necesaria para el análisis de patrones; por sí sola no identifica a nadie |
| id | Se conserva tal cual | Conservación | Solo es una llave interna de fila, no identifica a la persona |

**Nota sobre correo_enmascarado:** se construyó como ejercicio (primer carácter + asteriscos + dominio), pero se decidió no incluirla en el archivo final, ya que el análisis de patrones de acceso no requiere ningún dato de contacto, ni siquiera parcial. Mantenerla aumentaría el riesgo de exposición sin aportar valor al análisis.

---

## 2. Tabla de errores introducidos (Paso 1.2 / clave de respuestas)

| Tipo de error | Filas donde aparece | Cuenta |
|---|---|---|
| Fila duplicada exacta | ID 4 (duplica fila 1); ID 30 (duplica fila 12); ID 35 (duplica fila 19) | 3 |
| Fecha en formato dd/mm/aaaa | ID 2, ID 13, ID 14, ID 15, ID 17 | 5 |
| Fecha inválida (mes 13) | ID 7 (2026-13-04); ID 16 (2026-13-10) | 2 |
| Correo sin dominio o con mayúsculas | ID 2, ID 5, ID 17, ID 18, ID 19, ID 35 (duplicado de 19) | 6 |
| Teléfono con espacios o menos de 10 dígitos | ID 2, ID 20, ID 21, ID 22 | 4 |
| Área con distinta capitalización | ID 2, ID 22, ID 23, ID 24 | 4 |
| Celda vacía en empresa o teléfono | ID 3, ID 6, ID 26, ID 27, ID 28 | 5 |
| Hora fuera de horario laboral (<06:00 o >22:00) | ID 5, ID 9, ID 29, ID 31, ID 32 | 5 |

---

## 3. Tabla de incidencias (Paso 2.3 — no corregibles, se dejaron vacías)

| id | columna | valor original | motivo | acción |
|---|---|---|---|---|
| 3 | telefono | (vacío) | Celda vacía en el dato original | Se deja vacío, no se puede inventar |
| 4 | correo | pedro.salgado@correo | Correo sin dominio (falta .com) | Se vacía, dato incompleto |
| 5 | empresa | (vacío) | Celda vacía en el dato original | Se deja vacío, no se puede inventar |
| 6 | fecha_acceso | 2026-13-04 | Mes 13, fecha inválida | Se vacía, no se puede inferir la fecha real |
| 15 | fecha_acceso | 2026-13-10 | Mes 13, fecha inválida | Se vacía, no se puede inferir la fecha real |
| 17 | correo | camila.reyes@correo | Correo sin dominio (falta .com) | Se vacía, dato incompleto |
| 20 | telefono | 551234561 | Solo 9 dígitos, falta uno | Se vacía, no se puede adivinar el dígito faltante |
| 25 | empresa | (vacío) | Celda vacía en el dato original | Se deja vacío, no se puede inventar |
| 26 | telefono | (vacío) | Celda vacía en el dato original | Se deja vacío, no se puede inventar |
| 27 | empresa | (vacío) | Celda vacía en el dato original | Se deja vacío, no se puede inventar |

---

## 4. Diccionario de columnas (Paso 1.3)

| Columna | Tipo de dato | ¿Identifica a una persona? | Sensibilidad | ¿Sirve para el análisis de patrones de acceso? |
|---|---|---|---|---|
| id | número | No | Baja | Sí, como llave interna de referencia |
| nombre | texto | Directo | Alta | No, identifica pero no describe comportamiento |
| correo | texto | Directo | Alta | No, es dato de contacto |
| telefono | número | Directo | Alta | No, es dato de contacto |
| fecha_acceso | fecha | Indirecto | Media | Sí, permite ubicar el acceso en el tiempo |
| hora_entrada | hora | Indirecto | Media | Sí, es central para detectar horarios inusuales |
| area | categoría | Indirecto | Media | Sí, indica dónde ocurrió el acceso |
| empresa | categoría | Indirecto | Media | Sí, da contexto organizacional al patrón |
| motivo | categoría | No | Baja | Sí, ayuda a validar coherencia del acceso |
