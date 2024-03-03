# DOCKER. PRACTICA 3

### DESCARGA LA IMAGEN DE UBUNTU

Para descargar la imagen ejecutaremos el comando

````
docker pull ubuntu
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d30d0ba6-8c99-4eb7-9e52-260838d86bc1)

### DESCARGA LA IMAGEN DE HELLO-WORLD

Para descargar la imagen ejecutaremos el comando

````
docker pull hello-world
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d42cff88-4c48-47c0-b642-a5b50ccd7e78)


### DESCARGA LA IMAGEN DE NGINX

Para descargar la imagen ejecutaremos el comando

````
docker pull nginx
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2447ee9c-2757-4224-917e-ce2e06ed1ea2)


### MUESTRA EL LISTADO DE TODAS LAS IMAGENES

El listado de todas las imagenes lo mostramos ejecutando el comando 

````
docker images
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2b3e6e62-7c28-4ecc-a435-0f75dbda5a85)


### EJECUTA UN CONTENEDOR HELLO-WORLD Y DALE NOMBRE "MYHELLO1"

Ejecutar el contenderdor lo haremos con el comando

````
docker run --name myhello1 hello-world
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a0d9699a-0ad2-4cdc-9f81-8fee4d59a6a5)


### EJECUTA UN CONTENEDOR HELLO-WORLD Y DALE NOMBRE "MYHELLO2"

Ejecutar el contenderdor lo haremos con el comando

````
docker run --name myhello2 hello-world
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/70ebd72e-a718-4bd0-a203-667c240509a4)


### EJECUTA UN CONTENEDOR HELLO-WORLD Y DALE NOMBRE "MYHELLO3"

Ejecutar el contenderdor lo haremos con el comando

````
docker run --name myhello3 hello-world
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f213195a-253d-4cb2-b960-d86d890777f0)

### MUESTRA LOS CONTENEDORES QUE SE ESTÁN EJECUTANDO

Para mostrar los contenedores que se están ejecutando, usaremos el comando

````
docker ps -a
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/83f2d448-22db-4170-8c80-f3728c586ba1)

### PARA EL CONTENEDOR "MYHELLO1"

Para parar el contenedor ejecutaremos el comando

````
docker stop myhello1
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0998a9bc-d814-44ef-9706-685b5a609f19)

### PARA EL CONTENEDOR "MYHELLO2"

Para parar el contenedor ejecutaremos el comando

````
docker stop myhello2
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2d7de33e-0d26-489a-9377-21b73c37f2df)

### BORRA EL CONTENEDOR MYHELLO1

Para borrar el contenedor usaremos el comando

````
docker rm myhello1
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/02d183fd-fbdd-41b0-98b1-af1e1560de84)

### MUESTRA LOS CONTENEDORES QUE SE ESTÁN EJECUTANDO

Para mostrar los contenedores que se están ejecutando, usaremos el comando

````
docker ps -a
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4707f408-b53f-4c97-a52f-42cf5293ced4)

### BORRA TODOS LOS CONTENEDORES

Antes de borrar los contenedores, lo primero que tendremos que hacer es parar los contenedores con el comando

````
docker stop $(docker ps -aq)
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c37dcde2-19ce-4725-99b9-58e9694c1d04)

Una vez hayamos parado los contenedores, lo eliminaremos ejecutando el comando

````
docker rm $(docker ps -aq)
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d3462e76-a798-4670-8fce-16fb1b9ecee9)

Para comprobar que los contenedores los hemos borrado correctamente usaremos el comando 

````
docker ps -a
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/eb999dd4-dcf0-4841-a244-1088e9062afb)






