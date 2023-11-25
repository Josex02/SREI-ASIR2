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

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/58c17641-83c0-479f-997a-b35b2fd9f35d)






