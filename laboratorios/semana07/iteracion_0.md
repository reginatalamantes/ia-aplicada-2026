# Iteración 0 — Línea base (zero-shot)

- Modelo usado: **GEMINI**

## Prompt 

```text
Clasifica este reporte de incidente:

{ENTRADA}
```

## Entrada 1

**Respuesta completa del modelo (sin editar):** 
"### Clasificación del Incidente

* **Tipo de Incidente:** Compromiso de Credenciales mediante Phishing (Robo/Harvesting de credenciales).
* **Categoría de Seguridad:** Ingeniería Social / Seguridad de Identidad y Accesos.
* **Nivel de Severidad:** **ALTA**
* **Estado del Incidente:** En mitigación inicial (usuario realizó cambio de contraseña; requiere verificación por TI/SOC).

---

### Justificación del Nivel de Riesgo

Aunque cambiaste la contraseña minutos después, el incidente se clasifica como **Alto** porque hubo una **entrega efectiva de credenciales corporativas** a un tercero no autorizado. En la ventana de tiempo transcurrida entre el ingreso de datos y el cambio de contraseña, un atacante automatizado o manual pudo haber realizado las siguientes acciones:

1. **Persistencia de acceso:** Generar tokens de sesión activos o autorizar aplicaciones de terceros (OAuth) que permiten mantener acceso aun tras cambiar la contraseña.
2. **Modificación de reglas de correo:** Crear reglas silenciosas de reenvío automático o borrado de correos para monitorear tu actividad.
3. **Inscripción de dispositivos MFA:** Registrar un método de autenticación multifactor propio en tu cuenta.
4. **Movimiento lateral:** Acceder a la intranet, unidades en la nube o directorios de la empresa aprovechando el SSO (Single Sign-On).

---

### Acciones Recomendadas para el Equipo de TI / SOC

1. **Cierre forzado de sesiones:** Revocar todos los tokens de acceso y cerrar las sesiones activas de la cuenta en todos los dispositivos desde la consola de administración (p. ej., Microsoft Entra ID / Google Workspace).
2. **Auditoría de registros (Logs):**
* Inspeccionar inicios de sesión entre las 9:40 y la hora exacta del cambio de contraseña para identificar direcciones IP o ubicaciones anómalas.
* Revisar los logs de auditoría en busca de cambios en los métodos de autenticación multifactor (MFA).


3. **Inspección del buzón:** Verificar la presencia de reglas de reenvío de correo o filtros creados recientemente en la cuenta afectada.
4. **Contención del vector:** Extraer el remitente y la URL maliciosa del correo para bloquearlos en el Secure Email Gateway (SEG) y Firewall de la organización, previniendo que otros usuarios caigan en el mismo ataque.
5. **Escaneo del equipo:** Ejecutar un análisis antimalware completo en la laptop corporativa por precaución, para descartar ejecución de scripts o descarga silenciosa de payloads durante la visita al enlace.

¿Deseas redactar el reporte formal o el correo de notificación estructurado para enviarlo al equipo de respuesta a incidentes de tu empresa?
"

## Entrada 2

**Respuesta completa del modelo (sin editar):** PENDIENTE

"**Clasificación del Incidente**

* **Categoría:** Ciberseguridad / Seguridad de la Información
* **Tipo de Incidente:** Posible acceso no autorizado / Compromiso de cuenta (*Account Takeover*)
* **Nivel de Severidad:** Media (El riesgo inmediato disminuyó al cambiar la contraseña, pero persiste la posibilidad de accesos no autorizados en curso o persistencia configurada por el atacante)
* **Estado:** En mitigación / Bajo investigación

---

**Acciones recomendadas (¿Qué hacer?)**

1. **Cerrar todas las sesiones activas:** Cambiar la contraseña no siempre desconecta las sesiones que ya estaban abiertas. Ve a la sección de seguridad de tu cuenta y selecciona la opción de **""Cerrar sesión en todos los dispositivos""** o **""Cerrar todas las demás sesiones""**.
2. **Activar la autenticación de dos factores (2FA / MFA):** Configura la verificación en dos pasos utilizando una aplicación de autenticación (Google Authenticator, Microsoft Authenticator) o un número de teléfono seguro.
3. **Revisar el historial de actividad:** Accede al registro de inicio de sesión de tu cuenta para consultar las ubicaciones, direcciones IP y dispositivos que ingresaron recientemente.
4. **Verificar las reglas de reenvío y filtros de correo:** Los atacantes suelen crear reglas ocultas para reenviar copias de tus correos entrantes a direcciones externas o desviar alertas de seguridad a la papelera. Revisa y elimina cualquier regla sospechosa.
5. **Revisar los métodos de recuperación:** Comprueba que el correo de respaldo y el número de teléfono vinculados a la cuenta sigan siendo únicamente los tuyos.
6. **Revocar acceso a aplicaciones de terceros:** Revisa qué aplicaciones o sitios web tienen permisos otorgados para acceder a tu correo y elimina las que no reconozcas.
7. **Verificar cuentas vinculadas de alto impacto:** Si usas este correo como cuenta principal para bancos, redes sociales o plataformas de trabajo, revisa si has recibido solicitudes recientes de restablecimiento de contraseña en esos servicios.

¿Qué servicio de correo electrónico utilizas (Gmail, Outlook, Yahoo, etc.) para indicarte la ruta exacta donde verificar las sesiones activas y las reglas de reenvío?
"

## Entrada 3

**Respuesta completa del modelo (sin editar):** PENDIENTE

"| Parámetro | Clasificación |
| --- | --- |
| **Tipo de Incidente** | **Multivectorial Complejo**: Robo de dispositivo móvil + Compromiso de cuenta corporativa + Posible infección por malware (*Infostealer*) + Intento de fraude financiero. |
| **Nivel de Severidad** | **CRÍTICA / ALTA (Nivel 1)** |
| **Nivel de Urgencia** | **INMEDIATA** (Acción requerida en menos de 1 hora) |
| **Estado del Incidente** | **En curso / No contenido** |

---

### Análisis de Impacto y Evaluación de Riesgo

A diferencia de la percepción inicial del usuario, **el incidente es de gravedad máxima** debido a la coincidencia temporal de eventos físicos y digitales que representan una amenaza latente para la empresa y la finanzas personales:

1. **Riesgo Corporativo (Cuenta del trabajo):**
* **Intento de intrusión activa:** Los intentos de acceso indican que las credenciales ya fueron filtradas o que el atacante tiene acceso a los tokens de verificación/SMS recibidos en el celular robado.
* **Posible presencia de malware:** El archivo abierto el lunes pudo haber ejecutado un *software* malicioso (ej. un *infostealer* o troyano) que extrajo contraseñas almacenadas en el equipo, cookies de sesión o permitió el acceso remoto.


2. **Riesgo Financiero e Identidad:**
* **Superación del factor de doble autenticación (2FA):** Al poseer el dispositivo físico robado y/o acceso a las cuentas de correo, el atacante puede autorizar transferencias o restablecer contraseñas de aplicaciones bancarias.


3. **Vectores de Ataque Correlacionados:**
* **Escenario A (Físico a Digital):** El robo del celular le dio al atacante acceso a aplicaciones, cuentas de correo y SMS de autenticación.
* **Escenario B (Digital a Físico/Dirigido):** El archivo del lunes infectó el equipo, extrajo datos de geolocalización o información sensible, y los accesos sospechosos son producto de la fuga de credenciales.



---

### Plan de Acción Inmediato (Contención y Mitigación)

#### 1. Ámbito Corporativo (Prioridad 1)

* **Revocación de sesiones y cambio de credenciales:** Informar de inmediato al departamento de TI/Ciberseguridad para forzar el cierre de sesión en todos los dispositivos, restablecer la contraseña corporativa y desvincular el dispositivo móvil robado del sistema de doble factor (MFA).
* **Aislamiento del equipo:** Desconectar de Internet (Wi-Fi y cable) la computadora donde se abrió el archivo el lunes hasta que el equipo de ciberseguridad realice un análisis forense/antivirus.

#### 2. Ámbito Físico y de Telecomunicaciones

* **Bloqueo de línea y dispositivo:** Contactar a la compañía telefónica para suspender la SIM (evitar la recepción de códigos SMS) y solicitar el bloqueo del equipo por IMEI.
* **Borrado remoto:** Ejecutar la orden de borrado remoto del celular desde las plataformas oficiales (*Google Find My Device* o *Apple Find My*).

#### 3. Ámbito Financiero

* **Contacto directo con el banco:** Comunicarse con la línea de atención oficial del banco (no a través de enlaces del correo recibido) para verificar la autenticidad de la transacción, bloquear temporalmente las cuentas o banca móvil y cambiar contraseñas de acceso.

¿Deseas que te redacte un plantilla de notificación formal para enviar al departamento de TI/Ciberseguridad de tu empresa notificando el incidente?"

