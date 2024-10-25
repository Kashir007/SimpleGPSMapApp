**Desarrollo de un Programa de Mejora de Seguridad**

**Evaluar y mejorar la seguridad de la aplicación**
Diseño estructurado:
Realizar un análisis de seguridad inicial para identificar todas las vulnerabilidades y problemas potenciales (ya detectados en el reporte).
Implementar una metodología de Desarrollo Seguro (SDLC - Secure Development Lifecycle) para garantizar que cada fase del desarrollo de la aplicación incluya medidas de seguridad.
Usar herramientas de análisis de vulnerabilidades como escáneres automáticos de seguridad, pruebas de penetración (pentesting), y auditorías manuales periódicas.
Mejora:
Corregir las vulnerabilidades específicas detectadas, como la necesidad de soportar versiones más seguras de Android y deshabilitar la depuración en producción.
Eliminar o minimizar el uso de permisos abusivos y ajustar la configuración de los certificados.


**Proceso de revisión periódica de la seguridad**
Frecuencia de revisiones:
Establecer revisiones trimestrales de seguridad para identificar nuevas vulnerabilidades.
Realizar pruebas de seguridad en cada actualización importante de la aplicación o cuando cambien las dependencias o librerías externas.
Áreas clave de revisión:
Revisión de las dependencias y librerías de terceros para evitar vulnerabilidades conocidas.
Monitorear la política de permisos de la aplicación, eliminando aquellos que no sean esenciales.
Validar la seguridad de la comunicación de la aplicación (certificados, HTTPS).
Revisar la política de manejo de datos sensibles y garantizar que los mecanismos de cifrado sean adecuados.


**Identificación de métricas clave de seguridad**
Métricas para medir el estado de seguridad:
Número de vulnerabilidades detectadas y corregidas: Llevar un registro del número de vulnerabilidades identificadas durante las auditorías de seguridad y su tiempo de resolución.
Porcentaje de dispositivos que utilizan una versión de Android segura: Monitorear la compatibilidad de la aplicación con versiones más seguras de Android y reducir el 
soporte para versiones vulnerables como Android 7.0 (API 24).
Cumplimiento con las políticas de permisos: Medir la reducción del uso de permisos peligrosos, como ACCESS_FINE_LOCATION y ACCESS_COARSE_LOCATION, y 
asegurarse de que solo se usen cuando sean estrictamente necesarios.
Porcentaje de sesiones de red seguras (HTTPS): Asegurar que todas las comunicaciones de la aplicación utilicen HTTPS y que los certificados estén verificados.
Aplicación de mejoras específicas:
Problema: Aplicación firmada con certificado de depuración.
Mejora: Implementar una política estricta de firmar la app de producción con un certificado de firma de código.
Problema: Uso del algoritmo SHA1 para la firma de certificados.
Mejora: Migrar a un algoritmo de hash más seguro como SHA-256 para la firma de la aplicación.
