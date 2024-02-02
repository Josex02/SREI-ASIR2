![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/315bc1dd-12b2-4476-9793-eec980a2f27f)![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8660a9a7-21cb-4039-b242-82aa310a4dba)# PROYECTO FINAL 2 TRIMESTRE: SERVIDOR ALOJAMIENTO  WEB 

## JOSÉ EXPÓSITO ROBLES

### INSTALACIÓN DE SERVICIOS.

Vamos a proceder a hacer la isntalación de todos los servicios que necesitamos para poder hacer la práctica y para poder instalar todos los servicios, usaremos el comando "**sudo apt install apache2 php mysql-server phpmyadmin openssh-server python3**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/27fbb0f3-580a-4151-bdbc-448a6ccd3a73)

### alojamiento a páginas web tanto estáticas como dinámicas con “php”

Para alojar páginas web tanto estáticas como dinámicas con PHP, necesitarás configurar el servidor web. Usaremos el comando "**sudo apt install apache2 php libapache2-mod-php**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/11c6fc32-b65a-452d-9e39-526f60ba1f9f)

Crearemos el directorio web root para your_domain con el comando "**sudo mkdir /var/www/serverjose**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ec56e2e5-485c-443e-a56f-51a8364ff968)

A continuación, asignaremos la propiedad del directorio con la variable de entorno $USER, que hará referencia a su usuario de sistema actual, con el comando "**sudo chown -R $USER:$USER /var/www/serverjose**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1ba4f3d2-51f3-47ef-9801-e9617acbe7fc)

Luego, abra un nuevo archivo de configuración en el directorio sites-available de Nginx con el editor de línea de comandos que prefiera. En este caso, utilizaremos nano: "**sudo nano /etc/apache2/sites-available/serverjose.conf**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3f228249-f977-4a3f-a8c1-a9054fb66960)

De esta manera, se creará un nuevo archivo en blanco. Pegue la siguiente configuración básica:

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/870bf1f9-3f86-4e1d-bc51-625b4cff4f61)

Ahora, puede usar a2ensite para habilitar el nuevo host virtual con el comando "**sudo a2dissite 000-default**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4daf3136-7373-45a1-b2b4-32ab94864b8d)

Puede ser conveniente deshabilitar el sitio web predeterminado que viene instalado con Apache. Es necesario hacerlo si no se utiliza un nombre de dominio personalizado, dado que, en este caso, la configuración predeterminada de Apache sobrescribirá su host virtual. Para deshabilitar el sitio web predeterminado de Apache, ejecutaremos el comando "**sudo a2dissite 000-default**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/381daad7-c984-4ce3-a028-3bc0f6515ef9)

Para asegurarse de que su archivo de configuración no contenga errores de sintaxis, ejecute el comando "**sudo apache2ctl configtest**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ddcf4657-7c1c-4ee3-a6ec-56ca69b7a26c)

Ahora, su nuevo sitio web está activo, pero el directorio root web /var/www/your_domain todavía está vacío. Cree un archivo index.html en esa ubicación para poder probar que el host virtual funcione y lo haremos con el comando "**nano /var/www/serverjose/index.html**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4a47f32a-2194-4cb1-b20f-2e461edf15e9)

Incluya el siguiente contenido en este archivo:

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5f87d78a-7ddf-49ed-a3f0-efee0f8b07dd)

Ahora, diríjase a su navegador y acceda al nombre de dominio o la dirección IP de su servidor una vez más "**http://serverjose**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bceab21a-a1f8-4e4a-91f8-6acc045d5253)

### Probar el procesamiento de PHP en su servidor web.

Ahora que dispone de una ubicación personalizada para alojar los archivos y las carpetas de su sitio web, crearemos una secuencia de comandos PHP de prueba para verificar que Apache pueda gestionar solicitudes y procesar solicitudes de archivos PHP.

Cree un archivo nuevo llamado info.php dentro de su carpeta root web personalizada y lo haremos con el comando "**nano /var/www/serverjose/info.php**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/55c51855-c023-433a-932a-c5fdeced7b9f)

Con esto se abrirá un archivo vacío. Añada el siguiente texto, que es el código PHP válido, dentro del archivo:

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/43a35676-17ba-45de-b4b6-54c9fa766b7c)

Para probar esta secuencia de comandos, diríjase a su navegador web y acceda al nombre de dominio o la dirección IP de su servidor, seguido del nombre de la secuencia de comandos, en el que usaremos el comando "**http://serverjose/info.php**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/26683983-d87c-405d-9b63-a917a3fba7b8)

### Probar la conexión con la base de datos desde PHP.

Crearemos una base de datos denominada proyecto y un usuario llamado jose, pero puede sustituir estos nombres por valores diferentes.
Primero, establezca conexión con la consola de MySQL usando la cuenta root con el comando "**sudo mysql**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/fc5835e4-3b48-41b8-9072-520e95d5bf3b)

Para crear una base de datos nueva, ejecute el siguiente comando desde su consola de MySQL "**CREATE DATABASE proyecto;**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/977f59f1-1efd-4f0e-a8c3-4b48aa1b0988)

Ahora vamos a crear un nuevo usuario y vamos a darle una contraseña usando el comando "**CREATE USER 'jose'@'%' IDENTIFIED WITH mysql_native_password BY '1234';**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4065393e-81ef-42fb-8d8e-162dd36dd9d5)

Ahora, debemos darle permiso a este usuario a la base de datos proyecto con el comando "**GRANT ALL ON proyecto.* TO 'jose'@'%';**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/9a29324f-c7a7-4024-89a8-e21c2c80f62e)

Ahora, cierre el shell de MySQL con lo siguiente con el comando "**exit**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0f00c58a-76dc-46ce-9fa8-3c4a94733de9)




















