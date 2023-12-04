Busca información sobre las siguientes directivas y el valor que toman por defecto y el lugar donde se encuentra definida.

# Directivas de Identificación:
### ServerName:

Valor por defecto: Ninguno.
Definición: Puede establecerse en el archivo de configuración principal (httpd.conf) o en archivos de configuración de virtual hosts. Especifica el nombre del servidor y se utiliza para generar URL cuando se necesita saber el nombre del servidor.

### ServerAdmin:

Valor por defecto: webmaster@localhost.
Definición: Puede configurarse en el archivo de configuración principal o en archivos de configuración de virtual hosts. Establece la dirección de correo electrónico del administrador del servidor.

### ServerTokens:

Valor por defecto: Full.
Definición: Puede configurarse en el archivo de configuración principal. Controla la información que se incluye en la respuesta del servidor a las solicitudes. Los valores posibles incluyen Full, OS, Minor y Major.
Directivas de Localización de Ficheros:

### DocumentRoot:

Valor por defecto: Depende de la instalación, pero comúnmente es /var/www/html.
Definición: Puede configurarse en archivos de configuración de virtual hosts. Especifica el directorio base desde el cual se sirven los documentos.

### ErrorLog:

Valor por defecto: logs/error_log.
Definición: Puede configurarse en el archivo de configuración principal o en archivos de configuración de virtual hosts. Especifica la ubicación del archivo de registro de errores.

### CustomLog:

Valor por defecto: Ninguno.
Definición: Puede configurarse en el archivo de configuración principal o en archivos de configuración de virtual hosts. Especifica la ubicación y el formato del archivo de registro de acceso personalizado.

### ServerRoot:

Valor por defecto: Depende de la instalación, pero comúnmente es /etc/httpd o /etc/apache2.
Definición: Configurado en el archivo de configuración principal. Especifica el directorio base del servidor web.
Directivas de Control de la Conexión:

### Timeout:

Valor por defecto: 300 segundos.
Definición: Puede configurarse en el archivo de configuración principal. Establece el tiempo máximo de espera para las operaciones de red.

### KeepAlive:

Valor por defecto: On.
Definición: Puede configurarse en el archivo de configuración principal. Habilita o deshabilita la funcionalidad de Keep-Alive, que permite que una conexión TCP se reutilice para varias solicitudes HTTP.

### MaxKeepAliveRequests:

Valor por defecto: 100.
Definición: Puede configurarse en el archivo de configuración principal. Establece el número máximo de solicitudes que se pueden enviar a través de una conexión Keep-Alive.

### KeepAliveTimeout:

Valor por defecto: 5 segundos.
Definición: Puede configurarse en el archivo de configuración principal. Establece el tiempo máximo de espera para recibir la siguiente solicitud en una conexión Keep-Alive.
Otras:

### LogLevel:

Valor por defecto: "warn".
Definición: Puede configurarse en el archivo de configuración principal o en archivos de configuración de virtual hosts. Establece el nivel de detalle del registro. Otros valores posibles incluyen "info", "debug", "error", etc.

### LogFormat:

Valor por defecto: Ninguno (debe ser definido por el usuario).
Definición: Puede configurarse en el archivo de configuración principal o en archivos de configuración de virtual hosts. Especifica el formato de los registros de acceso en el archivo de registro de acceso personalizado.





