# DOCKER. PRACTICA 2

### EJECUTA LA IMAGEN "HELLO-WORLD"

Para ejecutar la imagen "**hello-world**" tendremos que ejecutar el comando.

````
docker run hello-world
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/abe695f9-ee2a-4e73-9e51-96cdd91c8b8e)

### MUESTRA LAS IMAGENES DOCKER INSTALADAS

Para ver que la imagen que hemos ejecutado se ha ejecutado correctamente, lo comprobaremos con el comando:

````
docker image ls
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d23766ee-9a36-40a1-9074-ac05b0ae7cf0)

### MUESTRA LOS CONTENEDORES DE DOCKER

Si queremos visualizar los contenedores de docker tendremos que ejecutar el siguiente comando:

````
docker container ls
````

En este momento no aparecen ninguno porque aun no hemos creado ninguno, en el momento que creemos algun contenedor nos aparecerá ejecutando el comando.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b05a309d-18bb-4586-b0e2-93c4583265ce)

### EDITA EL FICHERO DOCKERFILE

Lo primero que tendremos que hacer antes de editar el archivo "**Dockerfile**", tendremos que obtener el codigo fuente de la aplicación en nuestra maquina, lo haremos con el comando:

````
git clone https://github.com/docker/getting-started-app.git
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b12f8cd9-bece-435a-b411-45b8dcdd074d)

Luego tendremos que acceder dentro de la ruta que hemos creado, ejecutando el comando,

````
cd /home/jose/getting-started
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/927302b8-d770-40fa-926a-9e0d7c4b1a9d)









