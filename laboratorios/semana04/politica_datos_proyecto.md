# Política de datos del proyecto Predicción de riesgo de incendios en edificios

## 1. Alcance

Esta política cubre los siguientes datos, numerados en el inventario de la Semana 4:

- **D1** — Año de construcción — No personal
- **D2** — Tipo de uso (residencial, comercial, industrial) — No personal
- **D3** — Ubicación geográfica del edificio — No personal (indirecto, puede revelar domicilio de un propietario identificable)
- **D4** — Tipo de sensor instalado — No personal
- **D5** — Registros de incendios previos (fecha, causa, edificio, afectados) — Sensible/personal indirecto (dato de mayor riesgo)

## 2. Ciclo de vida

El ciclo de vida completo está documentado en `ciclo_vida_dato_proyecto.drawio` / `.png`, en esta misma carpeta. Resumen de las seis etapas y su responsable:

| Etapa | Responsable |
|---|---|
| 1. Captura | Técnico de instalación / administrador del edificio |
| 2. Almacenamiento | Administrador de sistemas |
| 3. Uso | Ingeniero de IA / analista de datos |
| 4. Compartición | Líder del proyecto |
| 5. Retención | Administrador de sistemas |
| 6. Eliminación | Administrador de sistemas |

El dato de mayor riesgo (D5, registros de incendios previos) solo sale hacia terceros externos (protección civil, aseguradora) de forma agregada como nivel de riesgo, nunca como el detalle del incidente.

## 3. Normativa aplicable

El proyecto se evaluó contra tres marcos (matriz completa en `matriz_cumplimiento_proyecto.xlsx`):

- **LFPDPPP México (2025):** aplica porque D3 y D5 pueden vincularse a un propietario identificable. Rigen los principios de consentimiento, información, proporcionalidad y el derecho a oponerse a una decisión automatizada (Art. 26, fracción II) — relevante si un inmueble es clasificado como "alto riesgo" afectando su valor o su seguro.
- **Ley de IA de la UE:** este proyecto podría calificar como sistema de alto riesgo bajo el Anexo III (componente de seguridad en infraestructura crítica), lo que obligaría a documentación de riesgos (Art. 9), registro de eventos (Art. 12) y supervisión humana (Art. 14).
- **NIST AI RMF:** se adopta de forma voluntaria, especialmente relevante para evaluar la calidad y el sesgo de los datos históricos (D5), que afectan directamente la confiabilidad de las predicciones del modelo.

## 4. Controles comprometidos

| Acción | Responsable |
|---|---|
| Obtener consentimiento del propietario antes de incorporar su inmueble al sistema | Técnico de instalación / líder del proyecto |
| Publicar aviso de privacidad al dar de alta cada inmueble | Líder del proyecto |
| Mantener el modelo solo con datos del inmueble, sin datos de ocupantes | Ingeniero de IA |
| Versionar diagrama, matriz y política en el repositorio cada semestre | Líder del proyecto |
| Ninguna acción correctiva se ejecuta sin revisión de un inspector humano | Ingeniero de IA |
| Documentar plazo de retención (10 años) y procedimiento de borrado seguro | Administrador de sistemas |
| Revisar si el modelo correlaciona "alto riesgo" con zonas socioeconómicas sin justificación técnica (sesgo) | Ingeniero de IA |
| Evaluar formalmente si el sistema cae en el Anexo III de la Ley de IA de la UE | Líder del proyecto |
| Crear canal para que un propietario apele una clasificación de riesgo | Líder del proyecto |
| Registrar cada predicción generada con fecha, versión del modelo y datos de entrada | Ingeniero de IA |

## 5. Manejo de datos con herramientas de IA

- **Nunca se ingresan a ChatGPT, Gemini, Deepseek u otras herramientas:** el detalle de D5 (causa específica del incendio, nombres de afectados, dirección exacta del inmueble).
- **Sí se pueden ingresar:** D1, D2, D4 y versiones generalizadas de D3 (zona o colonia, no dirección exacta) y D5 (nivel de riesgo agregado, sin detalle del incidente).
- **Condición obligatoria:** cualquier prueba de prompts debe usar datos ficticios de edificios, nunca el historial real de un inmueble identificable.
- **Antes de compartir cualquier archivo con un modelo generativo**, el responsable debe verificar que no contenga ubicación exacta ni el detalle de incidentes con personas afectadas.
- Esta regla aplica a todas las unidades siguientes del curso (Unidades II y III) en las que se usen modelos generativos y agentes con datos de este proyecto.

## 6. Revisión

Esta política se revisará al cierre de cada unidad del curso (aproximadamente cada 4 semanas), o antes si el proyecto incorpora un nuevo tipo de sensor o fuente de datos. La revisión y aprobación está a cargo del líder del proyecto, en conjunto con el administrador de sistemas para validar que los controles técnicos siguen vigentes.
