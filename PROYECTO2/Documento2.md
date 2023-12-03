# PRACTICA FINAL 1 TRIMESTRE REDES

### Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentros.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python.

Para comenzar a hacer la practica, lo primero que todo haremos un (apt update) y (apt upgrade) para ver si tenemos algo que actualizar y en caso de que tengamos algo lo actualizaremos.

Una vez ya hayamos actualiado todo, procederemos a la instalacion de APACHE2 con el comando (apt install apache2)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/76f38483-8f14-4fa0-b75e-fe109a75d6ce)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bab82fc8-866d-400b-bec3-ec357bbb987c)

Ahora, lo que haremos va a ser crear "centro.intranet" y "departamentos.centro.intranet" con el comando (mkdir)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0cd16248-4a85-4fb1-b35e-e0f79f40cd8d)

El próximo paso va a ser movernos dentro de "centro.intranet" y vamos a crear un archivo llamado index.html con el comando (nano index.html)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1eeb2c6b-f31b-4d44-a117-5239b54639af)

Luego, editaremos el archivo que hemos creado, tanto de centro.intranet como de departamentos.centro.intranet.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/378383cc-61d0-4bc4-bc92-5e68ae15a771)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a2455f66-84f3-4282-9b7f-f01ff5e1857f)

Ahora, lo que haremos va a ser entrar en "centro.intranet.conf"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2a08865d-4c2a-4938-977f-72ac6904d7b3)

Cuando entremos editaremos el archivo como tal y como te muestro, tanto en "centro.intranet.conf" como en "departamentos.centro.intranet".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/13112318-8dd2-4068-9dac-98c68f02cb98)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f2d3f90f-477f-4983-b133-aaf0962d887d)

El siguiente paso que tenemos que hacer es ejecutar el comando "a2ensite centro.intranet" y también "a2ensite departamentos.centro.intranet".

Cuando hagamos el "a2ensite", tendremos que reiniciar el servidor para que se apliquen los cambios con el comando "service apache2 restart".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4bdfae14-808f-4ddc-b44c-8188ea2b293e)

Ahora, nos iremos a nuestro archivo "hosts" y cambiaremos lo nombre asignados a las IPs por los que hemos creado.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/24f1d89c-8d6f-4ac7-a5ce-493479c07d90)

Por último, nos iremos a nuestro buscador y podremos la ruta que hemos creado "http://centro.intranet" y "http://departamento.centro.intranet".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f723219e-4ff1-40ca-957a-970ac3e3fcc7)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/586a8c47-5639-4e18-bf39-54df1b5111c9)

### Activar los módulos necesarios para ejecutar php y acceder a mysql

Para comenzar hacer este ejercicio, comenzaremos intalando mysql con el comando "apt install mysql-server".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e54bd379-8263-44de-98a6-6453f7996b18)

Ahora para comprobar que todo se ha instalado correctamente, escribimos "mysql".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4ca59e4f-e749-4741-a883-5529bf305ca6)

Luego, instalaremos libapache2 con el comando "apt install php libapache2-mod-php php-mysql".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8292ef31-3298-4b34-b08c-4201917d4b92)

Para comprobar que se ha instalado correctamente, ejecutamos el comando "php -v" para ver la version en la que se ha instalado.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5ed70d4e-cd1d-42ab-ba7c-04ddcadce729)

### Instala y configura wordpress

Para el comienzo de este ejercicio, lo que haremos va a ser instalar WordPress con el comando "wget http://wordpress.org/latest.tar.gz"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8642918e-63ec-455e-bd28-1a869af3f314)

Ahora, vamos a descomprimir y extraer los archivos del archivo comprimido latest.tar.gz con el comando "tar -xzvf latest.tar.gz".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/863a16c8-6980-41eb-870b-3c4f011c1abe)

Ahora creamos los directorios del wordpress con el comando "mkdir"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/200e747a-3ef9-4fac-b443-0fe46401bccb)

Luego le damos permisos a la carpeta con el comando "sudo chmod -R 777 /var/www/html/wordpress" (o en la ruta en la que tengas la carpeta".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/708e0341-fa25-4387-bc57-d30201a00c8e)

Ahora vamos a iniciar sesión en el sistema de gestión de bases de datos MySQL como el usuario "root" con el comando "mysql -u root -p"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bde91787-2ca5-45c8-b3e2-907e458c769b)

Crearemos la base de datos de "wordpress".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/60cf9551-9ea6-4675-ba24-2262c35ff0f3)

Después, crearemos nuestro usuario con nuestra contraseña, escribiendo el comando "CREATE USER 'Jose'@'%'IDENTIFIED BY 'Admin1234.'"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/09990990-b3af-4d3b-ae8c-b2964de949e8)

Ahora le daremos los privilegios a wordpress con el comando "GRANT ALL PRIVILEGES ON wordpress.** TO 'Jose'@'%';"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/993dc760-4eef-4b8f-ae5e-fce344590878)

Vamos a recargar los privilegios almacenados en la memoria y aplicar los cambios realizados con el comando "FLUS PRIILEGES"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/23eca1bb-34a1-4eae-9b9b-40452143e067)

Nos salimos de mysql con el comando "exit"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/641b65c5-cecc-4695-8c8c-c773e2166dd0)

El siguiente paso que haremos va a ser compiar el conteido de un archivo a otro con el comando "cp wp-config-sample.php wp-config.php"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c2572de2-8ed9-420b-99da-aabdd8d93927)

Ahora, abriremos el archivo al que hemos copiado los datos del otro

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/89197002-7891-4c15-995a-8d56683554b2)

Cuando lo abramos tendremos que editar el archivo con los datos que anteriormente hemos creado

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5f740806-b426-42a0-821f-d34cd58302f3)

Ahora, ejecutaremos un comando sin mostrar información adicional en la salida estándar y el comado es "curl -s https://api.wordpress.org/secret-key/1.1/salt/"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/18fa131c-35f9-4dea-be24-63f87efbc358)

Copiaremos los datos que hemos sacado antes con el comando que hemos puesto antes, y cuando lo copiemos volveremos a entrar en el archivo que hemos entrado anteriormente y pegaremos.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/55667fa9-c07c-4821-b279-a83dc38bcbe3)

Ahora, entraremos en el archivo de "wordpress.conf" con el comando "sudo nano /etc/apache2/wordpress.conf"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d6e817fe-e958-4dc1-9ed3-118eab876d6b)

Cuando entremos editaremos el archivo como podemos ver en la imagen.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/417ee514-4292-43c7-a44e-81b8109f2bdb)

Vamos hacer un test sintáctico para ver que no hemos cometido ningún error sintáctico y reiniciaremos el servidor de apache. Lo haremos con el comando "apachectl configtest" para hacer un test sintáctico y "service apache2 restart" para reiniciar el servidor.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b35fc8ee-b89b-47ea-8100-54dadbee008c)

Ahora nos iremos al buscador y pondremos la ruta que le hemos asignado "localhost/wordpress/wp-admin/"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5fc77f4b-7b1d-4c29-b6d6-1bef887f6684)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/192e0cb7-f932-4b97-a45e-487951008267)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/26927adc-3ae1-41ca-ac8d-80ebe37400eb)

### Activar el módulo "wsgi" para permitir la ejecución de aplicaciones Phyton.

Para habilitar mod_wsgi en Apache, basta con instalar el paquete libapache2-mod-wsgi

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/32d2ce8c-663c-49fd-a6fb-671bd85cb2ed)

Debemos tener un directorio destinado a montar toda la aplicación:

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/98d0d3b8-ae84-4151-b720-4366b6485acb)

Dentro de este directorio, vamos a dividir su arquitectura en dos partes:

1. Destinada al almacenaje de nuestra aplicación Python pura (será un directorio privado, no servido).
2. Destinada a servir la aplicación (directorio público servido) en el cuál solo almacenaremos archivos estáticos.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3446336a-0904-46ee-ab25-023cabf3c618)

Aprovecharemos este paso, para crear una carpeta, destinada a almacenar los logs de errores y accesos a nuestra Web App:

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3e2ad4dd-0031-4b17-9216-933c3d692460)

Todas las peticiones realizadas por el usuario (es decir, las URI a las cuáles el usuario acceda por el navegador), serán manejadas por un único archivo, que estará almacenado en nuestro directorio mypythonapp.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0aff8435-1fe9-4eae-8b98-4146697afe81)

Dicho módulo, solo se encargará de definir una función, que actúe con cada petición del usuario. Esta función, deberá ser una función WSGI aplicación válida. Esto significa que:

1. Deberá llamarse application
2. Deberá recibir dos parámetros: environ, del módulo os, que provee un diccionario de las peticiones HTTP estándar y otras variables de entorno, y la función start_response, de WSGI, encargada de entregar la respuesta HTTP al usuario.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/039e8fbf-6e11-4979-b364-ef9e6ec219a4)

Ahora entraremos en el archivo de "departamentos.centro.intranet.conf" con el comando "nano departamntos.centro.intranet.conf"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5dfaf339-c26d-4130-87a5-d6ac95c9149e)

Ahora editaremos el archivo tal y como vemos en la imagen.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2154374b-9e9f-4a9a-bf2f-56f6b65fd739)

El siguiente paso que haremos va a ser entrar en el archivo del python

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8ab719ae-2916-4bea-81a6-e4862944382c)

Ahora editaremos el archivo con los datos que viene en la imagen que hemos añadido

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6295f23f-88d9-45a7-ba0e-1dcd3563fa14)

Volveremos a ejecutar el comando de "a2ensite" pero esta vez en "departamentos.centro.intranet". Cuando lo hagamos reiniciaremos el servidor apache con el comando "service apache2 reload"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/49c3c023-fa86-4dd6-8a92-62bd642dca88)

Entraremos en el archivo "hosts".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b51b0748-fb41-4f10-827d-e7ce85ed6a2e)

Editaremos el archivo y le pondremos el nombre que le hemos asignado, en este caso "departamentos.centro.intranet

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bd979c54-3eff-4a34-ab4a-f82cbcae520d)

Ahora nos iremos a nuestro buscador y nos iremos a nuestra ruta "departamentos.centro.intranet" y veremos que nos sale de nuestra página web.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e69e90eb-1b70-41cf-993b-62724b9e7e30)

### Adicionalmente protegeremos el acceso a la aplicación python mediante autenticación

Instalaremos una utilidad llamada htpasswd, que forma parte del paquete apache2-utils para administrar los nombres de usuarios y contraseñas con acceso a contenido restringido.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f69be6d6-ef62-4c34-873e-bda87be48f88)

Ahora crearemos el primer usuario con el comando "sudo htpasswd -c /etc/apache2/.htpasswd root".

Cuando le demos al "Intro" nos solicitará proporcionar y confirmar una contraseña para el usuario.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b1a9a580-75d3-4ef1-b85b-e2f531ca1efc)

Ahora nos dirigimos a entrar a nuestro archivo "departamentos.centro.intranet"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/170a43a4-3437-4d7e-83ac-8a68f5d2fb33)

Y volveremos a editar nuestro archivo con los datos que tenemos señalado en la imagen marcada.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b86b65c7-53f9-44ff-842d-359133572200)

Luego, cuando terminamos tendremos que reiniciar el servidor de apache con el comando "service apache2 reload".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2e105ff1-4e81-4f5b-a971-df1eda13d2fc)

Nos volveremos a ir a nuestro buscador y volveremos a poner la ruta de "http://departamentos.centro.intranet" y veremos como que nos pide el nombre de usuario y la contraseña que le hemos puesto anteriormente.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/572fcd9e-0036-4642-a3d8-20a205c41415)

### Instala y configura awstat.

El primer paso que tendremos que hacer va a ser instalar "awstats" con el comando "apt install awstats"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3438b180-17a8-4bd6-97bd-baa188d1e091)

Ahora nos iremos a nuestro archivo de "awstats.conf"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/baa2b4a3-82e1-47c6-be15-8637a24868cf)

Editaremos el archivo de "awstats.conf" con los datos que hemos mostrado

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f730cb8f-998e-4048-b82c-eccf12896265)

El paso siguiente que vamos a dar va a ser ejecutar el comando de "a2enmod cgi" y el comando "a2enconf awstats"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ffa2cfe7-16df-41b9-bc7d-0613fa15e26c)

Luego, reiniciaremos el servidor de apache, con el comando "service apache2 reload"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f4420cfe-32b9-4c56-a515-632e2ff9c685)

Después, copiaremos los datos del archivo "awstats.conf" al arhivo "awstats.departamentos.centro.intranet.conf"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/092a5ae3-52ee-4062-a68d-dd5628e518fb)

Editaremos el archivo por los datos de la ruta que vemos en la imagen señalada

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bc63353b-e0fb-4394-8fa3-20612222f992)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a18592f0-7f06-4910-99f8-7beaae62ff94)

Ahora ejecutaremos el comando "sudo /usr/lib/cgi-bin/awstats.pl -config=departamentos.centro.intranet -update" para actualizar el archivo

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8ab194cb-3207-4a9a-a494-7074991ddf3c)

Cuando ya hayamos hecho todos los pasos anterior, nos volveremos a ir a nuestro buscador y buscaremos la ruta que hemos puesto "http://departamentos.centro.intranet/awstats/awstats.pl" y veremos como nos ha salido todo perfectamente

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0e5892a8-5855-4977-a7e1-4f66134d6648)

### Instala un segundo servidor de tu elección (nginx, lighttpd) bajo el dominio “servidor2.centro.intranet”. Debes configurarlo para que sirva en el puerto 8080 y haz los cambios necesarios para ejecutar php. Instala phpmyadmin.

Para comenzar, vamos a hacer un "apt update" para buscar actulizaciones y tenerlo todo actualizado.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/35b113e2-6c0d-43e8-9138-486f2858b260)

Vamos a instalar "NGINX" con el comando "apt install nginx"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/03265e18-7064-4e44-9946-f944c9cd6667)

Ahora vamos a crear un directorio que en mi caso lo voy a llamar "servidorcentro"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/52d0127b-7eb9-4777-b92a-dca6d17c1d56)

Dentro de "servidorcentro" crearemos un archivo, el cual, lo he llamado "index.html".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ca0d552e-9df0-43d1-a309-2e8a8a9be714)

Ahora nos iremos a nuestro archivo "hosts" y añadiremos la dirección.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/65cf9cf0-6b21-4faf-b697-e857fd1c2764)

Ahora nos iremos a nuestro archivo "default" de la nuestra ruta del "nginx" 

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6a7f0516-4292-43f6-b8eb-dbdcb582e407)

Cuando estemos dentro de nuestro archivo "default" editaremos el puerto donde lo tendremos situado, la ruta del archivo y el nombre del servidor.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/9683e25e-7258-4a8b-8f32-0c43c495b411)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/67776f0e-c000-4ca5-b2c6-f2d36fb29bae)

Ahora ejecutaremos el comando "ln -s ../sites-avalaible/servidor2 ../sites-enabled/servidor2.conf"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0d3c1716-47b7-43ab-b947-9f0bc8047505)

Nos iremos a nuestro navegador y pondremos la ruta "http://servidor2.centro.intranet:8080"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/831b500b-d038-4d0d-b5f6-329a861106ff)

Ahora tendremos que instalar mysql-server, pero como ya lo tendremos instalado, nos saldrá la última versión en la que lo tenemos instalado

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/26971613-cc25-4cfe-a06a-bab72fde49bb)

Instalamos "php" con el comando "apt install php-fpm php-mysql"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d6823be5-f665-4534-912c-d82581430bc2)

Ahora cambiamos el propietario con el comando "chown -R $USER:$USER /var/www/servidorcentro/"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a3b84ab2-0115-4642-8f1b-93e45fba3ac1)

Ahora entramos en el archivo de "servidor2.conf" lo editaremos como mostramos en la imagen señalada

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1a717eeb-74d2-4489-be0e-5327b58db3b1)








