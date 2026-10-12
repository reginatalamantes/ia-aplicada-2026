# Selección de modelo generativo para el proyecto “Norma Técnica de Seguridad contra Incendios en Edificaciones”

## Modelos evaluados

Lista los modelos que probaste en este laboratorio y en la semana 1 
ChatGPT.
Gemini.
Deepseek.
AI Studio.
Para este proyecto se usará IA Studio ya que fue el que se estuvo utilizando y el cual nos permite manipular la temperatura según es necesario.

## Evidencia de tokens

**Tokens de mi documento de referencia:** 1,199. 
**Caracteres por token en español:** 5,175. 
**Implicación para mi proyecto:** Sensores IoT envían datos a la nube y una IA estima el riesgo de incendio de cada edificio. Un inspector revisa el resultado antes de actuar..

## Evidencia de temperatura

**Temperatura que usaré para tareas de precisión:** la temperatura baja entre 0 y 0.5
Porque sus respuestas son mucho más objetivas y directas, se basan en hechos y no imaginan nada, dejando de lado la creatividad.

**Temperatura que usaré para tareas creativas:** 1 a 1.5 
Porque es más creativa y sus respuestas son más ingeniosas, sin embargo no llega hasta el 2 ya que no queremos que pierda la credibilidad ni comience a inventar datos demasiado locos..

## Evidencia de contexto

**El modelo reconoció siempre la aguja de AZUL-7342**

El modelo empezó a fallar con aproximadamente en el intento **número 14** con **309,014 tokens** lo que equivale a **15 documentos copiados**.

Mis documentos del proyecto miden aproximadamente 1,199 tokens = a 748 palabras hasta 250,674 tokens ~ 401,816 palabras 

 Por lo tanto: caben completos 14 documentos 
Pero si busco insertar un texto más grande debo dividirlo o debo resumirlo a la mitad o en tres partes para evitar que la interfaz rechace el documento por exceso de tokens.

## Decisión

Modelo elegido: IA Studio. 

**Configuración:** 
Temperatura 0 a 0.5: para tareas que requieran un análisis objetivo y directo.
Temperatura 0.7 a 1: para algo de creatividad y solución de problemas sin salirse de lo real y lógico pero con algo de ingenio.
Temperatura de 1.1 a 1.5: para actividades creativas como generación de ideas nuevas o soluciones de problemas que se salgan un poco más de la caja pero siempre regulando que no se salga de lo real y/o legal.
Temperatura de 1.6 a 2: para una lluvia de ideas donde no se necesite tanta coherencia y puede volar más al momento de responder.

**Restricciones de datos según la política de la semana 4:** no usar datos personales o sensibles, datos de cuentas bancarias, clientes o información clasificada. Cuidar el anonimizar siempre los datos o usar una simulación con datos falsos que no puedan relacionarse con los reales.
