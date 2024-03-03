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
git clone https://github.com/docker/getting-started.git
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/cffb92be-bc3a-44e2-b415-d1f9e8548973)

Luego tendremos que acceder dentro de la ruta que hemos creado, ejecutando el comando,

````
cd /home/jose/getting-started
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3923c4bb-063e-4eff-ab88-b1103987bd51)

Cuando estemos en la ruta veremos lo que hay dentro de la ruta en la que estamos con el comando "**ls**".

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b7ce2aa6-3d5a-4355-80bb-7691f6367baa)

Una vez que veamos que tenemos el archivo **Dockerfile** entraremos dentro del archivo con el comando:

````
sudo nano Dockerfile
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4d963501-dba3-4ea7-ae4e-b8ec8513c1f5)

Cuando entremos dentro del archivo, editaremos el contendio añadiendole las siguientes lineas:

````
# syntax=docker/dockerfile:1

FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/90c0430d-7c5f-44d2-8dee-aded7d59c0f3)

El siguiente paso que haremos será crear el contenedor, el cual, lo ejecutaremos con el comando:

````
docker build -t getting-started .
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ff1f32f0-619b-494f-a3ff-41bc2db3804d)






















