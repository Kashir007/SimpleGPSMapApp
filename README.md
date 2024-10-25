# Nombre del Proyecto
**SimpleGPSMapApp**

## Descripción
Este proyecto es una aplicación Android que sirve para poder ubicarnos en el mapa, usando la API de GoogleMaps.

## Vulnerabilidades Identificadas
**Vulnerabilidad por versión antigua**
**Depuración habilitada para la aplicación**  
**Permiso para hacer copia de seguridad de los datos de la aplicación**  
**Receptor de broadcast expuesto con nivel de protección no verificado** 

## Mejoras Implementadas
- **Cifrado de datos sensibles**: Se implementa cifrado robusto para proteger la información crítica.
- **Comunicación segura (HTTPS)**: Todas las comunicaciones se realizan a través de HTTPS para garantizar la seguridad de la transmisión.
- **Validación y sanitización de entradas**: Se valida y sanitiza todas las entradas del usuario para prevenir inyecciones y otros ataques.

## Documentación
- [Vulnerabilidades](vulnerabilities.md)
- [Vulnerabilidades Detalles](vulnerability_report.md)
- [Best Practices](best_practices.md)
- [Security Tips](security_tips.md)
- [Security Improvement Program](security_improvement_program.md)

## Cómo Ejecutar la Aplicación de Forma Segura
1. Clonar el repositorio.
2. Importar el proyecto en Android Studio.
3. Ejecutar la aplicación en un dispositivo o emulador.
4. Asegurarse de que los permisos necesarios están configurados.

## Reporte de Vulnerabilidades
El reporte detallado de las pruebas de vulnerabilidad realizadas se encuentra en el archivo `vulnerability_report.pdf`.
