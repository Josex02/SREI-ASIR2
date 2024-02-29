# PROYECTO FINAL 2 TRIMESTRE: SERVIDOR ALOJAMIENTO  WEB 

# JOSÉ EXPÓSITO ROBLES

## PASO1: INSTALACIÓN DE SERVICIOS.

Vamos a proceder a hacer la isntalación de todos los servicios que necesitamos para poder hacer la práctica y para poder instalar todos los servicios, usaremos el comando "**sudo apt install apache2 php mysql-server phpmyadmin openssh-server python3**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/27fbb0f3-580a-4151-bdbc-448a6ccd3a73)

### Alojamiento a páginas web tanto estáticas como dinámicas con “php”

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

Ahora vamos a verificar si el usuario nuevo tiene los permisos adecuados al volver a iniciar sesión en la consola de MySQL, esta vez, con las credenciales de usuario personalizadas y lo haremos con el comando "**mysql -u example_user -p**".
Cuando ejecutamos este comando nos pedirá la contraseña que le hayamos asignado a nuestro usuario.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4274d9d2-aa0c-487f-bacf-0de1d6649cc2)

Después de iniciar sesión en la consola de MySQL, confirme que tenga acceso a la base de datos, ejecutaremos el comando "**SHOW DATABASES;**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c5d952f1-51ed-4af5-a587-79e05c104123)

A continuación, crearemos una tabla de prueba denominada redes: Desde la consola de MySQL, ejecute la siguiente instrucción que mostraremos en la imagen.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d9eb20fa-29e8-4302-94d9-b08be6fb26fa)

Ahora, insertaremos alguna filas de contenido de prueba en nuestra tabla con el comando que te vamos a mostrar en la imagen de abajo.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d1e691bc-52fd-44a9-9502-a20d0886312f)

Para confirmar que los datos se guardaron correctamente en su tabla, ejecute lo siguiente.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f9694814-757e-4d94-867e-1a2b3f6bf1fd)

Después de terminar todos estos pasos, saldremos de mysql escribiendo "**exit**" en mysql.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1712ec99-46ae-4903-ab5e-644895cfa85f)

Ahora cuando acabemos todos los pasos anteriores, nos iremos a nuestro navegador web  y escribiremos la ruta "**http://localhost/phpmyadmin**" y entraremos dentro de phpmyadmin.
Cuando estemos dentro, tendremos  que iniciar sesió con el usuario que hemos creado anterioirmente y cuando iniciaemos sesión ya lo tendríamos.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ba609e91-88d4-4dfb-8564-8588007c0fb5)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2814ad83-5225-483b-b5d8-5e3d44b4fbc8)



## INSTALACION Y CONFIGURACION DE BIND9

Comenzaremos instalando el servicio "**bind9**", lo haremos con el comando.

````
sudo apt install bind9
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/669f2c42-2e58-47a9-be22-6c7d94eeeba1)

Ahora nos iremos al archivo de configuracion "**named.conf.options*" con el comando.

````
sudo nano /etc/bind/named.conf.options
````

Lo configuraremos la direccion que vanmos a utilizar con el dominio "**marisma.local**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/79e9ab55-b56a-4270-968c-e38032f2d9de)

Cuando lo hayamos editado correctamente y ahora crearemos la zona directa y la zona inversa, entraremos con el comando.

````
sudo nano /etc/bind/named.conf.local
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/7ca2cf7d-6fb8-46ac-97f4-072f53e697c6)

Ahora, vamos a comprobar que la sintaxis funciona correctamente, lo haremos con el comando.

````
sudo named-checkconf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f120fee9-63ee-43a9-9c55-99b50d3237bb)

Vamos a crear una carpeta para alamcenar nuestras zonas, la cual hemos llamado "**zones**" y crearemos un archivo copiando los archivos usando el comando.

````
sudo cp /etc/bind/db.127 /etc/bind/zones/db.192.168.195
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/348993c4-eade-4dd4-8752-76b7be674583)

Una vez ejecutado el comando vemos que la carpeta tiene los archivos correspondientes con el comando 

````
sudo ls /etc/bind/zones/
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/56798d59-ca61-407b-9d6c-61935ee2a127)

Nos iremos al archivo de configuracion de nuestra zona directa y lo pondremos como aparece ne la imagen

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/76691d96-af49-4dea-9d87-a004cf76703d)

Haremos lo mismo pero en el archivo de configuracion de la zona inversa.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/13f8faf5-02f4-4ea8-aaec-b04084c10833)

Por último, una vez hayamos hecho todos los procesos, restablecemos el servicio "**bind9**", lo haremos con el comando.

````
sudo systemctl restart bind9
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b596aa52-d632-4518-a91b-f5165a839a81)



## Acceso mediante ftp para la administracion de archivos

Para instalar el filezilla, usaremos el comando.

````
sudo apt install filezilla
````

En mi caso ya lo tengo instalado y vemos que tengo instalado la ultima version.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a4fc78a0-f028-448c-97f0-214f96fce0dd)

Lo primero que haremos será irnos al archivo de configuración y lo editaremos de la siguiente manera.

````
sudo nano /etc/proftpd/proftpd.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/9aa0afaf-4342-484d-b0ad-bfce9fa3731a)

Luego vamos a editar el archivo de configuración "**modules.conf**" con el comando.

````
sudo nano /etc/proftpd/modules.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0447f796-fbf6-4347-9744-f9415ede36aa)

El siguiente paso que haremos será instalar el servicio "**proftpd-mod-crypto**" con el comando.

````
sudo apt install proftpd-mod-crypto
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/16fd6833-779b-48aa-82a7-c1e164743686)

Cuando lo hayamos instalado correctamente, entraremos en el archivo de configuracion "**tls.conf**" y lo editaremos de la siguiente manera.

````
sudo nano /etc/proftpd/tls.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3e0d1f20-0a34-4fa5-9c2d-b8331eca93ae)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/38f4eb62-2880-476f-9ebd-0090e0ea756f)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f5cbb264-48a3-422b-bcbf-fa6b2fcb4508)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/90d464fb-3ef1-4a07-8b93-0150180f3e17)

Una vez editemos toda la configuracion reiniciaremos el servicio "**proftpd**" para aplicar todos los cambios que hemos hecho, lo haremos con el comando.

````
sudo systemctl restart proftpd
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/df9839d6-df1d-4e67-948f-8e69c56ed120)

Ahora cuando reiniciemos, nos iremos al archivo de configuracion de "**tls.conf**" y usaremos un comando para generar un certificado de seguridad.

````
sudo nano /etc/proftpd/tls.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2214b1bc-a21a-467b-9057-3506f9f2ddc2)

Lo usaremos como comando de la misma forma que te muestro en la imagen

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b1d450e8-471d-4a11-b4db-292afa80b938)

Cuando hayamos hecho correctamente los pasos anteriores, nos dirigiremos a "**filezilla**" y nos conectaremos con la siguiente configuracion.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2f008657-399c-4a56-ab0a-f6b74c9b8f36)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c918fb5a-a9d0-46ab-b433-4be8839144ac)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/654024a0-c8de-4f6e-b7d9-ec39326db294)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0c434463-c0cc-47b4-87b4-59c955111c79)



## POSTFIX, IMAP Y POP3

Lo primero que haremos será isntalar "**postfix**" lo configuraremos, para isntalarlo, usaremos el comando:

````
sudo apt isntall postfix
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a88c0ad6-9489-436e-90d2-ae835e4d9727)

Cuando lo instalemos nos saltará la ventana de configuración y marcaremos la opcion de "**sitio de internet**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f33c6bd5-3cb2-46fd-8cf7-e8a0b9630f15)

Lo siguiente que haremos será escribir el nombre de la configuracion de correo y ya lo tendriamos todo configurado

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2199a87b-217d-4f55-a407-b944bb930089)

Una vez tengamos instalado el servicio comprobaremos que funciona correctamente, usaremos el comando.

````
sudo systemctl status postfix
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c5da151d-3ca1-47a5-b016-15562138eb30)

Luego, instalaremos los servicios de "**IMAP**" y "**POP3**" utilizando el comando:

````
sudo apt install dovecot-imapd dovecot-pop3d
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bc7b604b-d8f7-44bb-9c66-7da4385c1169)

Cuando lo hayamos instalado reiniciaremos **dovecot**:

````
sudo apt install restart dovecot
````

Luego, vamos a editar el archivo de configuracion **dovecot.conf** con el comando:

````
sudo nano /etc/dovecot/dovecot.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/30d618a4-8951-479d-81e1-0b7ba3f74f23)

Una vez dentro lo editaremos y añadiremos la siguiente linea que te muestro en la imagen.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bd00d4e0-8f3e-48e2-a8fa-49fda8de4a7e)




## HABILITAR ARCHIVOS PARA INSTALAR PYTHON

Para habilitar los archivos python para poder instalarlo, usaremos los comandos:

````
sudo apt install libapache2-mod-py3
sudo a2enmod wsgi
sudo systemctl restart apache2
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/fdd7c97f-2f1d-4b0b-8968-a6b56d27a8e2)

Después de habilitar los archivos necesarios para la instalacion de python, vamos a instalarlo con el comando:

````
sudo apt install python3
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e4861a49-de62-4026-9656-0a6388fb33ce)



# CREACION DE SCRIPT:

````
#!/bin/bash

echo "Escribeme el nombre de usuario"
read usuario

echo "Escribe la contraseña que quieras"
read contrasena

echo "Escribe la direccion ip"
read ip



conf="${usuario}.conf"
available="/etc/apache2/sites-available/${conf}"
enable="/etc/apache2/sites-enabled/${conf}"
subdominio="${usuario}.marisma.local"
documentroot="/var/www/html/$usuario"
html="${conf}/index.html"
zona_directa="/etc/bind/zones/db.marisma.local"
zona_inversa="/etc/bind/zones/db.192.168.201"

# Creacion del usuario y del directorio de usuario

echo "Creacion del usuario y directorio para la pagina web"
sudo useradd -m -d /home/$usuario -s /bin/bash $usuario

echo "$usuario:$contrasena" | sudo chpasswd
echo "Has creado el usuario del sistema ${usuario} y actualizado su contraseña."


# Creacion del subdominio

echo "Actualizacion del fichero de zona"
echo "\$ORIGIN ${dominio}." >> $zona_directa
echo "@ IN A ${ip}" >> $zona_directa
echo "www IN A ${ip}" >> $zona_directa
#Zona inversa
echo "${ip} IN PTR ns.${subdominio}." >> $zona_inversa

service apache2 reload > /dev/null
service bind9 reload > /dev/null
service proftpd reload > /dev/null


# Agregar el host a el archivo /etc/hosts
echo "${ip} ${subdominio}" >> /etc/hosts
echo "127.0.0.1 ${subdominio}" >> /etc/hosts
echo "El Host se ha añadido al archivo correctamente"


# Creacion del Host Virtual
echo "Creando fichero de config"
sudo mkdir $documentroot
touch "${documentroot}/index.html"
echo "<html><body><p>Ignacio apruebame</p></body></html>" > "${documentroot}/index.html"
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/$conf
echo "<VirtualHost *:80>
	ServerAdmin admin@$subdominio
	ServerName $subdominio
	DocumentRoot $documentroot
	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>" >> $available


a2ensite $conf

service apache2 reload > /dev/null
service bind9 reload > /dev/null
service proftpd reload > /dev/null


echo "Reiniciando servicios"
service apache2 reload > /dev/null
service bind9 reload > /dev/null
service proftpd reload > /dev/null


# Configuracion de la base de dato
mysql -u root -e "CREATE DATABASE $usuario;"
mysql -u root -e "CREATE USER '$usuario'@'localhost' IDENTIFIED BY  '$contrasena';"
mysql -u root -e "GRANT ALL PRIVILEGES ON $usuario.* TO '$usuario'@'localhost';"
mysql -u root -e "FLUSH PRIVILEGES;"

echo "Has creado la base de datos ${usuario} y el usuario SQL ${usuario}"
````




































