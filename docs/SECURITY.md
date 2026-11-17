
# Carlos Dev Lab — Security Engineering

## 1. Objetivo

Diseñar una arquitectura de seguridad avanzada, verificable
y mantenible para proteger Carlos Dev Lab.

La seguridad se implementará desde el diseño y mediante
defensa en profundidad, mínimo privilegio y validación continua.

No se afirmará que el sistema es invulnerable.

## 2. Alcance

Componentes previstos:

- Portafolio público React.
- API de contacto mediante Cloudflare Workers.
- Almacenamiento privado mediante Cloudflare D1.
- Sistema defensivo Sentinel.
- Panel privado Sentinel SOC.
- Repositorio y despliegues mediante GitHub.

Estado actual: arquitectura en planificación.

## 3. Activos que debemos proteger

- Integridad del sitio web.
- Código fuente y dependencias.
- Credenciales y secretos.
- Mensajes enviados por visitantes.
- Registros de eventos de seguridad.
- Acceso administrativo.
- Disponibilidad de la aplicación.
- Integridad de los despliegues.

## 4. Modelo de amenazas

Amenazas principales:

- Inyección de datos maliciosos.
- Cross-Site Scripting (XSS).
- Abuso automatizado de formularios.
- Denegación de servicio.
- Acceso administrativo no autorizado.
- Filtración de información personal.
- Exposición accidental de secretos.
- Dependencias vulnerables.
- Compromiso de la cadena de suministro.
- Manipulación de registros o configuraciones.

Las amenazas se evaluarán según probabilidad,
impacto y controles existentes.

## 5. Defensa en profundidad

Controles previstos:

### Aplicación
- Validación de entradas en el servidor.
- Límites de longitud y tipo de datos.
- Protección contra XSS e inyecciones.
- Política Content Security Policy (CSP).
- Cabeceras HTTP de seguridad.

### Infraestructura
- HTTPS.
- Separación entre frontend y servicios privados.
- Principio de mínimo privilegio.
- Protección de secretos.
- Despliegues controlados.

### Formularios
- Cloudflare Turnstile.
- Limitación de solicitudes.
- Validación del lado del servidor.
- Campos trampa contra automatización.
- Tratamiento seguro de errores.

### Administración
- Panel privado separado del sitio público.
- Autenticación resistente al phishing.
- Autorización comprobada en el servidor.
- Control de sesiones.
- Registro de operaciones administrativas.

## 6. Sentinel — Detección defensiva

Sentinel será responsable de identificar anomalías
y registrar eventos técnicos relevantes.

Capacidades previstas:

- Identificación de solicitudes malformadas.
- Detección de abuso repetitivo.
- Correlación de señales de riesgo.
- Clasificación de eventos.
- Alertas de seguridad.
- Respuestas defensivas proporcionales.
- Supervisión del estado de los controles.

Ninguna señal aislada demostrará por sí sola
que una persona es atacante.

## 7. Sentinel SOC

Panel administrativo privado previsto para:

- Consultar métricas operativas.
- Revisar formularios recibidos.
- Supervisar eventos de seguridad.
- Investigar alertas.
- Consultar el estado de las defensas.
- Documentar incidentes y acciones correctivas.

Los registros y controles sensibles no serán públicos.

## 8. Privacidad y registros

- Recolectar solo información necesaria.
- Evitar almacenar contraseñas o secretos.
- No registrar indiscriminadamente mensajes completos.
- Limitar el acceso a eventos de seguridad.
- Definir períodos de conservación.
- Proteger los registros contra modificaciones indebidas.
- Evitar rastreo encubierto e identificación invasiva.
- Aplicar la normativa de protección de datos pertinente.

## 9. Verificación de seguridad

Antes de publicar se comprobarán:

- Calidad del código.
- Compilación y tipos.
- Dependencias y vulnerabilidades conocidas.
- Exclusión de secretos.
- Validación de formularios.
- Permisos y autorización.
- Configuración de cabeceras.
- Resistencia a solicitudes inválidas.
- Protección de registros.
- Funcionamiento de mecanismos antiabuso.

Las pruebas se realizarán únicamente sobre
sistemas propios o expresamente autorizados.

## 10. Estado de implementación

### Verificado
- Reglas de exclusión de secretos en .gitignore.
- Comprobación con git check-ignore.

### En desarrollo
- Documentación del modelo de seguridad.

### Pendiente
- CSP y cabeceras.
- Validación de formularios.
- Turnstile y limitación de solicitudes.
- API protegida.
- Almacenamiento privado.
- Sentinel.
- Sentinel SOC.
- Autenticación administrativa.
- Auditorías automatizadas.
- Pruebas de seguridad antes del despliegue.

## 11. Referencias técnicas

- OWASP Top 10.
- OWASP ASVS.
- OWASP Cheat Sheet Series.
- NIST Cybersecurity Framework.
- Documentación oficial de seguridad de Cloudflare.

## 12. Criterio de aceptación

Un control solo se considerará implementado
cuando exista código o configuración verificable.

Se considerará validado cuando supere
las pruebas correspondientes.

Toda mejora de seguridad deberá preservar
la funcionalidad, el rendimiento y la privacidad.
