## RESPUESTA CORREGIDA
**1. Introducción**
El proyecto "Predicción de riesgo de incendios en edificios" consiste en un modelo predictivo de inteligencia artificial diseñado para clasificar el nivel de riesgo de incendio (bajo, medio o alto) de un inmueble. Este sistema funciona como una herramienta de apoyo a la decisión, procesando datos de sensores IoT y del historial del edificio para que un inspector humano de protección civil revise cada resultado y decida dónde prevenir o intervenir primero.

**2. Alcance**

* **Qué incluye:**
* Estimación predictiva del nivel de riesgo de incendio en tres niveles: bajo, medio o alto.
* Procesamiento de: año de construcción, tipo de uso, ubicación generalizada (zona o colonia), tipo de sensor e historial de incendios agregado.
* Usuarios: técnico de instalación, administrador del edificio, ingeniero de IA, inspector de protección civil y propietarios.
* Transmisión exclusiva del nivel de riesgo resultante a protección civil o aseguradoras.


* **Qué no incluye:**
* Ejecución de acciones automatizadas sin la revisión de un inspector humano.
* Recolección o procesamiento de datos de los ocupantes del inmueble.
* Ingreso de detalles de incidentes o la ubicación exacta a modelos generativos.



**3. Requisitos funcionales**

* **RF-1:** El sistema debe estimar el nivel de riesgo en bajo, medio o alto a partir de los datos de sensores IoT y el historial del inmueble.
* **RF-2:** El sistema debe registrar el consentimiento del propietario y el aviso de privacidad a través de [DATO PENDIENTE] antes de iniciar la recolección.
* **RF-3:** El sistema debe proveer una interfaz mediante [DATO PENDIENTE] para que el inspector de protección civil revise cada resultado predictivo.
* **RF-4:** El sistema debe asegurar que protección civil o las aseguradoras reciban únicamente el nivel de riesgo estimado.
* **RF-5:** El sistema debe integrar a los usuarios (técnico de instalación, administrador, ingeniero de IA, inspector y propietario) mediante [DATO PENDIENTE].

**4. Requisitos no funcionales**

* **RNF-1:** Se debe aplicar una política de retención de 10 años para la información, con borrado seguro.
* **RNF-2:** El sistema no recolecta datos de los ocupantes del edificio.
* **RNF-3:** Restricción de uso: el detalle de los incidentes y la ubicación exacta del edificio no se ingresan a modelos generativos.

## Declaración de generación asistida
- Modelo usado: GEMINI
- Fecha: 27/10/2026
- Prompt usado:
  ´´Al prompt que me diste, agrégale las siguientes correcciones, no modifiques nada que no se te pida en las mismas. : N.ºUbicaciónTipo de hallazgoTexto originalCorrección1Introducción, última oraciónVago“determine eficientemente dónde priorizar las tareas de prevención o intervención”Quitar “eficientemente”, que no se puede verificar, y usar lo de la ficha: “decida dónde prevenir o intervenir primero”.2Alcance, “Qué incluye”, tercer puntoInventado“Módulos de acceso y operación para los usuarios autorizados”Dejar solo la lista de usuarios. La ficha no habla de módulos.3RF-2[DATO PENDIENTE] correcto“…a través de [DATO PENDIENTE] antes de iniciar la recolección…”Dejar la marca hasta definir cómo se obtiene el consentimiento.4RF-5Inventado“habilitar perfiles de usuario con permisos específicos…”Quitar o marcar [DATO PENDIENTE]: la ficha no define roles ni permisos.5RNF-1Vago“política de retención estricta de 10 años”Quitar “estricta”. El plazo de 10 años sí está en la ficha.6RNF-2Inventado“bloquear por diseño cualquier intento de recolección… de datos… de los ocupantes”Reescribir como “El sistema no recolecta datos de los ocupantes del edificio”.7RNF-3Contradice la ficha“filtros de seguridad que garanticen técnicamente que… jamás sean transmitidos ni ingresados a modelos generativos”En tu política de la Semana 4 (sección 5) esa regla es de uso del equipo, no una función del sistema. Reescribirla como restricción y quitar “garanticen técnicamente” y “jamás”.8Documento completo Otro (incumple la extensión)458 palabras El prompt pedía máximo 400. Recortar unas 60 palabras.´´
- Número de correcciones aplicadas: 8 correcciones
