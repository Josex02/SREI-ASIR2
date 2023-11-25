# PRACTICA FINAL 1 TRIMESTRE REDES

### Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentros.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python.

Lo primero que tendremos que hacer antes de instalar nuestro sistema, tendremos que buscar si tenemos actualizaciones para comprobar que los archivos del sistema se encuentran actualizados. Para buscar actulizaciones, utilizaremos dos comandos, usaremos "apt update" y "apt upgrade", cuando ajecutemos el comando nos pedirá confirmación, podremos la contraseña quee le tengamos asiganada y ya estaría.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d022e8cb-565b-494c-8a9c-026efaaa3043)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/108479b2-300c-4b93-853e-d615f2194496)

Cuando ya hayamos descargado las actulizaciones, ahora descargaremos apache mediante el comando "apt instsall apache2".

Pero como en mi caso ya lo tenía instalado, me aparece que ya tengo la última versión de la instalación.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e6bcd3d5-ebc0-4077-b8b9-5b1d70e9aae1)

Una vez instalado apache, vamos a crear sus respectivas carpetas y paginas principales. Para hacerlo tendremos que acceder a "/var/www" mediante el comando "cd /var y cd /www" y cuando ya estemos dentro, crearemos las carpetas con el comando "mkdir nombre_carpeta".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a1af02a0-b15c-4985-a0a9-27029e9d676d)

El siguiente paso que tendremos que hacer, será crear la paginas correspondientes a las carpetas que ya hemos creado anteriormente.

Para ello, lo que tendremos que hacer es acceder a la carpeta que hemos creado con el comando que ya hemos explicado "cd nombre_carpeta" y crearemos la pagina correspondiente a la carpeta medianete el comando "nano index.html"

Haremos este mismo pasao para cada una de las carpetas que hemos creado.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/eb61fe5b-d5e4-44dd-aba4-b2619c3acce6)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/22e7b037-ec50-4a36-8a95-d36a6a8f580c)

Tendremos que salir de la carpeta de "Centros" mediante el comando "cd .." y volver a acceder con la carpeta de "Departamenntos" y crear la página de la misma manera que la anterior.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6dd9e7c7-cfe6-46c7-806e-6322e835b152)

Después de crear las respectivas paginas, lo que vamos a hacer ahora va a ser crear los archivos de configuracion de dichos sitios.

para comenzar tendremos que acceder a las siguientes rutas.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2fa6e85b-ca9e-4435-8cd6-2e0849667a28)

Luego cunado ejecutemos el comando "nano centro.intrantet.conf" tendremos que crear el propio archivo d configuración

Cuando acabemos "nano centro.intranet.conf", tendremos que hacer lo mismo con "nano departamentos.centro.intranet".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a3073ed3-aaa3-4813-a03e-34c6739ea976)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1bfbf2e1-68d3-4f8f-93c7-f61bb1721554)

Ahora le daremmos permisos a las carpetas para que apache pueda acceder a ellas y pueda abrir el archivo index.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8a0903c9-e9e1-4eb1-9558-0f0f450eebb0)

Una vez tiene permisos vamos a habilitar los VirtualHosts con a2ensite y el nombre del dominio y reiniciando apache para que los cambios se apliquen.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/58c17641-83c0-479f-997a-b35b2fd9f35d)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/476b5ba9-95a0-4294-bd55-466324960f85)


Para terminar, vamos a configurar las IPs de los  dominios en el archivo hosts mediante el comando "nano hosts" y cambiaremos nuestras IPs por lo que hemos creado anteriormente

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/56b690e5-ec24-40a2-8a5d-0e62149604e3)

En mi caso usare el 127.0.0.1 para centro.intranet y 127.0.1.1 para departamentos.centro.intranet. Una vez hecho todo, comprobamos que ambas direcciones funcionen si intentamos acceder a ellas.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/07e79d92-29c7-4368-b3f7-7ab46a5174c3)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6ec71a6c-ebf0-4a10-9347-5ef1b62f8cdf)


### Activar los módulos necesario para ejecutar php y acceder a mysql.

Para instalar MySQL usamos el siguientes comando: sudo apt install mysql-server.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/aa2b89af-250f-4b30-9bb0-9dc946a2212d)

Para comprobar que funciona probamos a iniciar sesión con el comando sudo mysql

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/052cad67-025c-4c51-a37a-30311fec0f3f)

Ahora, tendremos que instalar PHP y para instalar las siguientes librerias necesarias, usaremos el comando "sudo apt install php libapache2-mod-php php-mysql".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/819dbeaf-cb4a-4152-a22c-2afcfb4e3a2f)

Una vez instalado, para comprobar que así ha sucedido y la versión que se ha instalado usamos el comando php -v.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/54151f81-47a5-41a7-a9dc-28da75af3314)

### Instala y configura wordpress.

Para instalar y configurar wordpress, tendremos que crear antes que nada una base de datos y para hacer esto, tendremos que usar el comando "mysql -u root -p".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6a74b25d-b7e9-4a3c-a8ec-c7b2a8c9f00a)

Cuando hayamos iniciado sesion, tendremos que crear una base de datos, para crearlo utilizaremos el comando "CREATE DATABASE centrointranet DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ce47b179-308f-418f-ac6c-47a6dca225ea)

Lo que siguiente que tenemos que hacer es crear un usuario en nuestra base de datos. Para hacerlo usaremos el comando "CREATE USER 'jose '@'%' IDENTIFIED WITH mysql_native_password BY 'Admin1234.';"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/df90cde5-1dfe-48c6-a34a-7418f148965b)

Luego, le otorgaremos acceso completo a la base de datos con el comando "GRANT ALL ON centrointranet .* TO 'jose '@'%'".

Cuando le  demos a Enter nos pedirá que le pongamos ";".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4adb6088-0658-456d-97b1-9c1af8b0d760)

Ahora, lo que tendremos que hacer, será recargar mysql para que recargue los cambios que hemos hecho con el comando "FLUSH PRIVILEGES;"  y cuando ya lo hayamos recargado, lo cerraremos poniendo "EXIT".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/caf4be8c-5f7d-4036-ac30-e410b3fc2bee)



















