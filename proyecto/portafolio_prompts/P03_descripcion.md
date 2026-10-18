# P03 — Riesgos de la solución propuesta

## Objetivo
Listar cinco riesgos de una solución que usa sensores IoT y un modelo de IA para predecir el riesgo de incendio en edificios, cada uno con una norma, ley o fuente verificable, para comprobar si los nombres de las fuentes son exactos.

## Modelo y configuración

- Modelo: Google AI Studio, modelo: [escribe el nombre que aparece en el panel de AI Studio]
- Temperatura: [valor que mostraba el panel; "por defecto" si no la cambiaste]
- Fecha de ejecución: [AAAA-MM-DD]

## Prompt (versión v1)

```text
Enumera cinco riesgos de una solución que usa sensores IoT y un modelo de inteligencia artificial para predecir el riesgo de incendio en edificios. Para cada riesgo indica una norma, ley o fuente verificable con su nombre exacto.
```

## Resultado obtenido

```text
Aquí tienes cinco riesgos asociados a la implementación de una solución de IoT e
Inteligencia Artificial para la predicción de incendios, junto con su respectiva
norma o fuente legal:

1.  Riesgo de vulneración de la privacidad de los datos Al utilizar sensores IoT
    (especialmente si incluyen cámaras o micrófonos para detectar humo o
    comportamientos anómalos), existe el riesgo de capturar datos personales o
    sensibles de los ocupantes del edificio sin su consentimiento explícito,
    violando su derecho a la intimidad.

      - Fuente: Reglamento General de Protección de Datos (GDPR).

2.  Riesgo de ciberataques y manipulación de señales (Spoofing) Los dispositivos
    IoT suelen tener vectores de ataque que podrían permitir a un tercero
    interceptar la comunicación o enviar señales falsas al modelo de IA. Un
    atacante podría desactivar las alertas de incendio o provocar evacuaciones
    masivas falsas, generando caos.

      - Fuente: ISO/IEC 27001 (Tecnología de la información — Técnicas de
        seguridad — Sistemas de gestión de la seguridad de la información).

3.  Riesgo de sesgo algorítmico y errores de predicción (Falsos Negativos) El
    modelo de IA puede presentar errores de precisión debido a datos de
    entrenamiento insuficientes o sesgados. Un "falso negativo" (el modelo
    predice que no hay riesgo cuando sí lo hay) es un riesgo crítico que puede
    resultar en la pérdida de vidas humanas.

      - Fuente: ISO/IEC 42001:2023 (Information technology — Artificial
        intelligence — Management system).

4.  Riesgo de falta de seguridad en la interconexión de dispositivos IoT La
    heterogeneidad de los dispositivos (distintas marcas y protocolos) puede
    crear vulnerabilidades en la red local del edificio. Si un sensor no cumple
    con los estándares de seguridad, puede servir como puerta de entrada para
    comprometer todo el sistema de detección de incendios.

      - Fuente: ETSI EN 303 645 (Cyber Security for Consumer Internet of
        Things).

5.  Riesgo de incumplimiento de los estándares de seguridad contra incendios
    Existe el riesgo de que la solución de IA se utilice como sustituto de los
    sistemas de detección tradicionales en lugar de ser un complemento. Si el
    sistema de IA no está integrado bajo las normativas de señalización y
    detección, podría no cumplir con los requisitos legales de seguridad de
    vida.

      - Fuente: NFPA 72 (National Fire Alarm and Signaling Code).
```

## Verificación

| Afirmación verificable | Fuente primaria | Resultado | Clasificación |
|---|---|---|---|
| 1. Existe el Reglamento General de Protección de Datos (GDPR) y sirve para el riesgo de privacidad | Reglamento (UE) 2016/679 (https://eur-lex.europa.eu/eli/reg/2016/679/oj) | Es el nombre oficial corto del Reglamento (UE) 2016/679 y regula el tratamiento de datos personales; el modelo no dio el número | Correcta |
| 2. ISO/IEC 27001 se titula "Tecnología de la información — Técnicas de seguridad — Sistemas de gestión de la seguridad de la información" | ISO/IEC 27001:2022, ficha del organismo de normalización sueco SIS (https://www.sis.se/en/produkter/information-technology-office-machines/it-security/isoiec-270012022/) | La norma existe, pero la edición vigente es ISO/IEC 27001:2022 y su título es "Information security, cybersecurity and privacy protection — Information security management systems — Requirements". El título que dio el modelo es el de la edición 2013, que fue reemplazada | Parcialmente correcta |
| 3. ISO/IEC 42001:2023 se titula "Information technology — Artificial intelligence — Management system" | ISO (https://www.iso.org/standard/42001) | El título coincide exactamente; se publicó en diciembre de 2023 | Correcta |
| 4. ETSI EN 303 645 se titula "Cyber Security for Consumer Internet of Things" | EVS, ficha de ETSI EN 303 645 V2.1.1 (https://www.evs.ee/en/evs-en-303-645-v2-1-1-2020) | El título oficial termina en "Baseline Requirements", que el modelo omitió. Además, la norma es para dispositivos IoT de consumo y excluye los de uso industrial, manufactura o salud | Parcialmente correcta |
| 5. Existe NFPA 72, National Fire Alarm and Signaling Code | NFPA, edición 2025 (https://shop.iccsafe.org/nfpa-72-national-fire-alarm-and-signaling-code-2025-edition.html) | El nombre coincide; la edición vigente es 2025 y amplió los requisitos de protección contra ciberataques | Correcta |

Tasa de error de esta respuesta: 40% (2 parcialmente correctas y 0 alucinadas de 5 afirmaciones verificadas).

Notas de verificación:
- Ninguna de las cinco fuentes fue inventada.
- El título de 2013 de ISO/IEC 27001 lo conozco por conocimiento previo; lo que verifiqué en la fuente es que el título de 2022 es otro y que la edición 2013 fue reemplazada.
- NFPA 72 es un código de Estados Unidos y obliga solo donde la autoridad local lo adopta. No abrí nfpa.org directamente: usé la ficha de una tienda y una nota de prensa.
- No abrí el PDF de ETSI; usé fichas de organismos de normalización.

## Evaluación

- Qué funcionó: las cinco fuentes existen y los riesgos son pertinentes (privacidad, ciberseguridad, sesgo, interconexión y cumplimiento). Ninguna fuente fue inventada.
- Qué falló: dos títulos no eran exactos (ISO/IEC 27001 con el título de la edición 2013 y ETSI sin "Baseline Requirements"), a pesar de que el prompt pedía el nombre exacto. Casi ninguna fuente trae el año o la edición. Tampoco aparece ninguna norma mexicana, como la LFPDPPP de 2025, aunque el proyecto está en México. ETSI EN 303 645 está pensada para IoT de consumo y quizá no cubre un sistema de edificios comerciales.
- Qué cambiaré en la siguiente versión: pediré el título completo con el año o la edición de cada norma, indicaré que el proyecto es para México y para edificios comerciales, y pediré que cada fuente diga a quién aplica. Para el riesgo de sesgo agregaré el NIST AI RMF (función Medir), que ya usé en mi matriz de cumplimiento.
- Observación: igual que en P01, el modelo acertó los nombres de las fuentes y falló en el detalle (edición y título completo). Esto concuerda con que el error principal fue información desactualizada o incompleta, no inventada.

## Historial de versiones

| Versión | Fecha | Cambio realizado | Resultado del cambio |
|---|---|---|---|
| v1 | [AAAA-MM-DD] | Versión inicial | Tasa de error 40% (2 de 5 parcialmente correctas) |

## Datos usados
Confirmo que este prompt cumple la sección 5 de la política de datos del proyecto: sí, porque describe el proyecto en general y no incluye datos personales ni el detalle de D3 o D5.
