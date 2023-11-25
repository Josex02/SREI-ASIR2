# PRACTICA FINAL 1 TRIMESTRE REDES

### Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentros.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python.

Lo primero que tendremos que hacer antes de instalar nuestro sistema, tendremos que buscar si tenemos actualizaciones para comprobar que los archivos del sistema se encuentran actualizados. Para buscar actulizaciones, utilizaremos dos comandos, usaremos "apt update" y "apt upgrade", cuando ajecutemos el comando nos pedirá confirmación, podremos la contraseña quee le tengamos asiganada y ya estaría.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ce571fd1-c557-40d8-802d-34d8c0442b1e)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/108479b2-300c-4b93-853e-d615f2194496)

Cuando ya hayamos descargado las actulizaciones, ahora descargaremos apache mediante el comando "apt instsall apache2".
Pero como en mi caso ya lo tenía instalado, me aparece que ya tengo la última versión de la instalación.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e6bcd3d5-ebc0-4077-b8b9-5b1d70e9aae1)

Una vez instalado apache, vamos a crear sus respectivas carpetas y paginas principales. para hacerlo tendremos que acceder a "/var/www" mediante el comando "cd /var y cd /www" y cuando ya estemos dentro, crearemos las carpetas con el comando "mkdir nombre_carpeta".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a1af02a0-b15c-4985-a0a9-27029e9d676d)

El siguiente paso que tendremos que hacer, será crear la paginas correspondientes a las carpetas que ya hemos creado anteriormente.

Para ello, lo que tendremos que hacer es acceder a la carpeta que hemos creado con el comando que ya hemos explicado "cd nombre_carpeta" y crearemos la pagina correspondiente a la carpeta medianete el comando "nano index.html"

Haremos este mismo pasao para cada una de las carpetas que hemos creado.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/eb61fe5b-d5e4-44dd-aba4-b2619c3acce6)

