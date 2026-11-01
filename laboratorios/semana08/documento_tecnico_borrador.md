## RESPUESTA SIN EDITAR 

**1. Introducción**
El proyecto "Predicción de riesgo de incendios en edificios" consiste en la implementación de un modelo predictivo de inteligencia artificial diseñado para clasificar el nivel de riesgo de incendio (bajo, medio o alto) de un inmueble. Este sistema funcionará como una herramienta de apoyo a la toma de decisiones, procesando datos provenientes de sensores IoT y del historial del edificio. Su propósito principal es proveer información procesada para que un inspector humano de protección civil revise cada resultado y determine eficientemente dónde priorizar las tareas de prevención o intervención.

**2. Alcance**

* **Qué incluye:**
* Estimación predictiva del nivel de riesgo de incendio categorizado exclusivamente en: bajo, medio o alto.
* Procesamiento de variables de entrada estrictamente delimitadas: año de construcción, tipo de uso, ubicación generalizada (zona o colonia), tipo de sensor e historial de incendios en forma agregada.
* Módulos de acceso y operación para los usuarios autorizados: técnico de instalación, administrador del edificio, ingeniero de IA, inspector de protección civil y propietarios.
* Transmisión del nivel de riesgo resultante hacia entidades externas (protección civil o aseguradoras).


* **Qué no incluye:**
* Toma de decisiones automatizada o ejecución de acciones sin la validación previa del inspector humano.
* Recolección, almacenamiento o procesamiento de datos personales de los ocupantes del inmueble.
* Ingreso de detalles de incidentes o la ubicación exacta del edificio a modelos de IA generativa.



**3. Requisitos funcionales**

* **RF-1:** El sistema debe analizar los datos de sensores IoT y el historial del inmueble para clasificar el riesgo de incendio en los niveles bajo, medio o alto.
* **RF-2:** El sistema debe requerir, registrar y almacenar el consentimiento del propietario y la aceptación del aviso de privacidad a través de [DATO PENDIENTE] antes de iniciar la recolección de información.
* **RF-3:** El sistema debe proveer un módulo de revisión para que el inspector de protección civil pueda visualizar, evaluar y dar visto bueno a cada uno de los resultados emitidos por el modelo predictivo.
* **RF-4:** El sistema debe formatear los envíos de información destinados a protección civil o aseguradoras para que estos reciban única y exclusivamente la etiqueta del nivel de riesgo.
* **RF-5:** El sistema debe habilitar perfiles de usuario con permisos específicos para el técnico de instalación, administrador, ingeniero de IA, inspector y propietario.

**4. Requisitos no funcionales**

* **RNF-1:** La base de datos debe aplicar una política de retención estricta de 10 años para la información del inmueble, tras los cuales se debe ejecutar un mecanismo de borrado seguro.
* **RNF-2:** La arquitectura de datos del sistema debe bloquear por diseño cualquier intento de recolección o entrada de datos relacionados con los ocupantes del edificio.
* **RNF-3:** El sistema debe contar con filtros de seguridad que garanticen técnicamente que el detalle de los incidentes y la ubicación exacta jamás sean transmitidos ni ingresados a modelos generativos.

