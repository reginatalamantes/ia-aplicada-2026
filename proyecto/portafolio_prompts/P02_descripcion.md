# P02 — Evaluación de riesgo y primeros pasos ante un phishing bancario

## Objetivo
Obtener en 100 palabras una evaluación inmediata del riesgo y los primeros pasos a seguir en un caso de phishing con suplantación del banco, para después verificar cada dato contra fuentes primarias.

## Modelo y configuración

- Modelo: Claude Sonnet 5.5 (Anthropic), en claude.ai
- Temperatura: por defecto (claude.ai no permite ajustarla)
- Fecha de ejecución: 2026-10-18

## Prompt (versión v1)

```text
Una persona de 30 años de edad reportó a su banco un robo de datos y dinero por seguir un enlace que le enviaron a su correo a nombre del departamento de ciberseguridad del banco. Redacta en 100 palabras la evaluación inmediata del riesgo de la situación y los primeros pasos a seguir.
```

## Resultado obtenido

```text
Riesgo alto. Es un caso de phishing con suplantación del banco, y hubo pérdida de dinero y robo de datos. Las credenciales y los datos personales están expuestos, así que el atacante puede seguir usándolos para nuevos fraudes o para suplantar la identidad de la víctima.

Primeros pasos: llamar de inmediato al banco para bloquear cuentas y tarjetas y pedir la aclaración de los cargos; cambiar las contraseñas desde un dispositivo seguro y activar la autenticación en dos pasos; revisar el dispositivo con un antivirus; conservar el correo y el enlace como evidencia; y presentar la denuncia ante las autoridades.
```

Extensión: 100 palabras.

## Verificación

| Afirmación verificable | Fuente primaria | Resultado | Clasificación |
|---|---|---|---|
| 1. El caso es de phishing (un mensaje que busca que se haga clic en un enlace o se entregue información sensible) | NIST, *What is phishing?* (https://www.nist.gov/document/sbccphishingpdf) | NIST describe el phishing como mensajes que buscan que la persona haga clic, inicie sesión o entregue información sensible; el caso encaja | Correcta |
| 2. Llamar de inmediato al banco para bloquear cuentas y tarjetas | CONDUSEF, *Consejos para tu bolsillo*, 31-ene-2020 (https://www.gob.mx/cms/uploads/attachment/file/530852/CONSEJOSPARATUBOLSILLO-31012020.pdf) y NIST (mismo documento) | CONDUSEF recomienda contactar al banco de inmediato para que bloquee las tarjetas; NIST recomienda contactar al área de fraude de la cuenta afectada | Correcta |
| 3. Cambiar las contraseñas afectadas | NIST, *What is phishing?* | NIST recomienda cambiar de inmediato las contraseñas afectadas y las de otras cuentas donde se repitan | Correcta |
| 4. Activar la autenticación en dos pasos | NIST y CISA (https://cisa.gov/avoid-phishing-attempts) | Ambos recomiendan la autenticación multifactor; CISA la define como usar más que una contraseña | Correcta |
| 5. Revisar el dispositivo con un antivirus | NIST, *What is phishing?* | NIST recomienda mantener antivirus cuando el ataque busca instalar malware | Correcta |
| 6. Presentar la denuncia ante las autoridades | CONDUSEF, *Consejos para tu bolsillo* | CONDUSEF ayuda a presentar la reclamación y asesora para denunciar ante el Ministerio Público | Correcta |
| 7. Conservar el correo y el enlace como evidencia | No encontré el texto en NIST, CISA ni CONDUSEF; solo en guías secundarias | Sin confirmar en fuente primaria | No encontrado |

Tasa de error de esta respuesta: 0% (0 parcialmente correctas y 0 alucinadas de 6 afirmaciones verificadas; la afirmación 7 no cuenta porque no pude verificarla).

Detalles que no verifiqué: "pedir la aclaración de los cargos" y "desde un dispositivo seguro".

## Evaluación

- Qué funcionó: cumplió el formato (dos párrafos, 100 palabras), evaluó el riesgo y ordenó los pasos por urgencia. Todos los datos que pude verificar coincidieron con NIST, CISA y CONDUSEF.
- Qué falló: la respuesta es genérica. No nombra a las autoridades mexicanas concretas (Policía Cibernética, Ministerio Público), no da plazos para reclamar al banco y no distingue qué hacer en la primera hora y qué en las primeras 24 horas. La edad de 30 años no cambió nada, lo cual es correcto porque no es relevante.
- Qué cambiaré en la siguiente versión: pediré que el texto sea para México, que nombre la autoridad a la que se acude en cada paso, que ordene los pasos por tiempo (primera hora, 24 horas) y que indique la fuente de cada recomendación.
- Observación: la tasa de error fue baja porque la respuesta casi no contiene cifras, fechas ni leyes. En P01, donde el prompt pedía esos datos, la tasa fue de 29.4%.

## Historial de versiones

| Versión | Fecha | Cambio realizado | Resultado del cambio |
|---|---|---|---|
| v1 | 2026-10-18 | Versión inicial | Tasa de error 0% (6 de 6 verificadas), 1 afirmación sin fuente primaria |

## Datos usados
Confirmo que este prompt cumple la sección 5 de la política de datos del proyecto: sí, porque describe un caso hipotético con una persona de 30 años, sin nombre ni datos personales reales.
