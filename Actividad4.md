# ACTIVIDAD 4 - FTP PRIVADO Y ANONIMO

### EJERCICIO1 - Configura proftpd para que los usuarios accedan al directorio /home/ftp (puedes usar DefaultChdir). ¿Cual es la diferencia entre DefaultRoot y DefaultChdir?

Para comenzar a haer el ejercicio, tendremos que instalar los servicios ProFTPd y bind9, los cuales los haremos con el comando "**sudo apt-get install proftpd**" y "**sudo apt-get install bind9**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8f47ed02-9c8d-4d65-89ec-0f9aed386344)

Vamos a comprobar que el servicio de proftpd está funcionando y lo haremos con el comando "**sudo systemctl status proftpd**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/014f896b-ba2c-42e9-9d56-d234b7205880)

Luego instalaremos el servicio bind9 con el comando "**sudo apt-get install bind9**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/836ffcae-717b-489d-a230-ed08684a7914)

El siguiente paso que haremos será entras al archivo "proftpd.comf" con el comando "**sudo nano /etc/proftpd/proftpd.conf**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/cba60a5b-75c2-44e3-beb1-0bae5d586f86)

Cuando entremos en el archivo, vamos a modificar la configuración añadiendole la ruta "**DefaultRoot /home/ftp**"

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b410420d-7777-4c04-8600-2c6f213a0661)


### EJERCICIO2 - No se permitirá subir ni eliminar nada de la carpeta ftp.

En este ejercicio, vamos a restringir las acciones en la carpeta ftp para que no se permita subir ni eliminar nada de la carpeta y lo haremos configurandola de la siguiente manera.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c5d5f76e-aa32-4631-832d-68161abf3f49)


### EJERCICIO3 - Configura el acceso mediante usuario anónimo 

Para hacer este ejercicio editaremos el archivo proftpd.conf y mostraremos los siguientes comandos.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bc0e795b-0fd2-4f18-ac52-832108f95cd8)


### EJERCICIO4 -  Permite que el usuario anónimo pueda escribir si accede desde la red 10.6.0.x

Para permitir que el usuario anónimo pueda escribir lo haremos mediante "Limit WRITE" y escribiremos el siguiente comando.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c22b50dd-3e90-4048-a50f-280db2b968be)

Por último, reiniciaremos el servicio para oder aplicar todos cambios que hemos realizado anteriormente.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/536bdba3-eb1e-46fc-9aff-ea6345664284)

### COMPROBACION

Para comenzar la comprobación del ejercicio vamos a instalar "**FileZilla**", lo haremos con el comando "**sudo apt-get install filezilla**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/13b0ab39-e5c9-4d90-a931-52c6f98fd33b)

Ahora, vamos a crear un nuevo usuario con el comando "**sudo adduser usuarioftp**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/afcc30ea-0a3f-4db7-ad78-ef81f6cfbceb)

Cuando ya hayamos creado el nuevo usuario nos iremos a FileZilla y una vez dentro vamos a conectarnos.
Para conectarnos, abriremos el gestor de sitios y lo rellenaremos con los datos que hemos creado.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5f163f9e-23d9-424b-82bc-b719647cea64)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/9538e018-e0f5-48c3-91f4-421a92cac1eb)

Cuando le demos a conectar tendremos que poner la contraseña que le hemos establecido anteriormente.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d8171345-841f-480c-ae8d-68bc628eb803)

Por último, veremos que después de introducirle la contraseña ya nos hemos conectado correctamente.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4aedbecb-23f7-4525-8201-dcc1684b5ee9)
















