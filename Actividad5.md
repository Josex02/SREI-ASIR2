# ACTIVIDAD 5 --> VIRTUAL HOST

### EJERCICIO 1:  Crea un directorio para el usuario virtual “informatica” en /home/ftp/informatica

Para este ejercicio, vamos a crear un nuevo directorio llamado informatica con el comando:
````
sudo mkdir /home/ftp/informatica
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e369100f-ee41-4081-81d5-79861f1f5dbf)



### EJERCICIO 2: Cambia el propietario del directorio creado anteriormente mediante “chown” al usuario ftp

En este ejercicio vamos a cambiar el propietario del directorio creado anteriormente mediante “chown” al usuario ftp con el comando:

````
sudo chown ftp:ftp /home/ftp/informatica
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c684cb9d-5019-409d-ae01-4780990de69e)



### EJERCICIO 3: Crea un usuario virtual “informatica” mediante “ftpasswd”

Ahora vamos a crear un usuario virtual llamado "**informatica**" mediante "**ftpasswd**", cunado ejecutemos el comando nos pedira que le agregemos una contraseña (en mi caso le he añadido la contraseña "linux").

````
sudo ftpasswd --passwd --file=/etc/proftpd/ftpd.passwd --name=informatica --uid=1001 --gid=1001 --home=/home/ftp/informatica --shell=/bin/false
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/22f93eae-676a-4dbf-a1aa-7ddc1525ff56)



### EJERCICIO 4: Haz los cambios necesarios en el fichero de configuración de proftpd

Nos iremos al archivo de configuracion de "**proftd**" y haremos los cambios necesarios, entraremos dentro del archivo de configuracion con el comando.

````
sudo nano /etc/proftpd/proftpd.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e36804bf-b413-4a13-a860-4b0709adf743)



### EJERCICIO 5: Crea un sitio virtual para “informatica.marisma.local”

Para este ejercicio, vamos a crear el sistio virtual para "**informatica.marisma.local**" con el comando

````
sudo nano /etc/apache2/sites-available/informatica.marisma.local.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/79a8b47e-8afa-4abb-a7d4-f27162a7b56b)

Cuando estemos dentro editaremos el archivo tal y como te mostramos en la imagen.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b262a065-f617-4ae9-80b6-97a864f7dff2)



### EJERCICIO 6: Modifica el fichero de zona del DNS para que resuelva adecuadamente

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/89e1d191-b473-4f06-94b2-f5eea2d7a01b)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c5dd5245-9c27-4257-bf6b-e13781b69f78)
















