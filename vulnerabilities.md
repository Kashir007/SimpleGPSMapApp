#Reporte de Vulnerabilidades

##Sumario
-Total de vulnerabilidades: 4
Critical:0
High:2
Medium:2
Low:0
## Hallazgos detallados

###1. Vulnerabilidad por versión antigua.
-**Descripción:** La aplicación se puede instalar en una versión de Android vulnerable 
(Android 7.0, mindSdk=24) que contiene múltiples vulnerabilidades no solucionadas.
-**Severidad:** Alta
-**Impacto:** Los dispositivos que ejecutan versiones antiguas de Android no recibirán 
actualizaciones de seguridad razonables, lo que los hace susceptibles a ataques y compromisos de seguridad.
-**Pasos para reproducir:** 
-Intentar instalar la aplicación en un dispositivo que ejecute Android 7.0.
-Observar que la instalación se completa sin advertencias sobre vulnerabilidades.
-**Remediación:**:Limitar la instalación de la aplicación a dispositivos que ejecuten 
Android 10 o superior (API 29) para garantizar que los usuarios reciban actualizaciones de seguridad adecuadas.

###2. Depuración habilitada para la aplicación
-**Descripción:** La depuración está habilitada en la aplicación, lo que facilita que los i
ngenieros inversos conecten un depurador a ella. Esto permite volcar un seguimiento de pila 
(stack trace) y acceder a clases auxiliares de depuración.
-**Severidad:** Alta
-**Impacto:**  Los atacantes pueden aprovechar esta configuración para acceder a información sensible, 
manipular el código de la aplicación, o realizar ingeniería inversa, lo que incrementa el riesgo 
de explotación.
-**Pasos para reproducir:** 
-Revisar el archivo AndroidManifest.xml de la aplicación.
-Verificar que el atributo android:debuggable esté configurado en true
-**Remediación:**:Deshabilitar la depuración en el entorno de producción configurando 
android:debuggable en false en el archivo AndroidManifest.xml.

###3. Permiso para hacer copia de seguridad de los datos de la aplicación
-**Descripción:** Este permiso permite que cualquier persona realice una copia de seguridad de 
los datos de la aplicación a través de adb. Los usuarios que hayan habilitado la depuración USB 
pueden copiar los datos de la aplicación desde el dispositivo.
-**Severidad:** Advertencia
-**Impacto:** Los datos sensibles de la aplicación pueden ser extraídos sin autorización 
si el dispositivo está conectado a través de USB y la depuración está habilitada. 
Esto podría llevar a la exposición de datos críticos de la aplicación.
-**Pasos para reproducir:** 
-Conectar un dispositivo con la depuración USB habilitada.
-Usar el comando adb backup para intentar realizar una copia de seguridad de los datos de la aplicación.
-**Remediación:**: Deshabilitar la opción de copia de seguridad configurando el 
atributo android:allowBackup a false en el archivo AndroidManifest.xml

###4. Receptor de broadcast expuesto con nivel de protección no verificado
-**Descripción:** e encontró un Broadcast Receiver que se comparte con otras aplicaciones en el dispositivo, lo que lo deja accesible a cualquier otra aplicación. Está protegido por un permiso, pero este permiso no está definido en la aplicación analizada. Por lo tanto, el nivel de protección del permiso debe ser verificado donde esté definido. Si el nivel de protección está configurado como "normal" o "peligroso", una aplicación maliciosa podría solicitar e interactuar con el componente. Si está configurado como "signature", solo las aplicaciones firmadas con el mismo certificado podrán obtener el permiso.
-**Severidad:** Advertencia
-**Impacto:** Un atacante podría explotar esta vulnerabilidad para acceder o interactuar con el receptor de broadcast, lo que puede permitir la manipulación o abuso de las funcionalidades compartidas con otras aplicaciones.
-**Pasos para reproducir:** 
-Revisar el archivo AndroidManifest.xml de la aplicación.
-Verificar que el receptor androidx.profileinstaller.ProfileInstallReceiver esté marcado como android:exported=true.
-Comprobar que el permiso android.permission.DUMP no esté definido correctamente.
-**Remediación:**:Asegurarse de que el permiso esté definido correctamente y verificar el nivel de protección del permiso. Configurarlo como signature si es necesario, para limitar el acceso a aplicaciones firmadas con el mismo certificado.
