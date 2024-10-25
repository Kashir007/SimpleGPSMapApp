**Desarrollo de un Programa de Mejora de Seguridad**

**Evaluar y mejorar la seguridad de la aplicación**
Análisis inicial: Identificar vulnerabilidades y problemas.
Desarrollo Seguro: Implementar SDLC para incluir medidas de seguridad en todas las fases del desarrollo.
Herramientas de análisis: Usar escáneres de seguridad, pruebas de penetración y auditorías manuales periódicas.
Correcciones:
Soportar versiones más seguras de Android y deshabilitar la depuración en producción.
Minimizar permisos abusivos y mejorar la configuración de certificados.


**Proceso de revisión periódica de la seguridad**
Frecuencia: Realizar revisiones trimestrales y pruebas de seguridad tras cada actualización importante.
Áreas clave:
Revisar dependencias y librerías para detectar vulnerabilidades.
Monitorear permisos y eliminar los no esenciales.
Validar la seguridad de la comunicación (HTTPS) y manejar datos sensibles con cifrado adecuado.


**Identificación de métricas clave de seguridad**
Métricas:
Número de vulnerabilidades detectadas y corregidas.
Porcentaje de dispositivos que usan versiones de Android seguras.
Cumplimiento con políticas de permisos.
Porcentaje de sesiones de red seguras (HTTPS).
Mejoras específicas
Problema: Certificado de depuración.
Mejora: Usar un certificado de firma de código para producción.
Problema: Algoritmo SHA1 para firma de certificados.
Mejora: Migrar a SHA-256 para una mayor seguridad.
