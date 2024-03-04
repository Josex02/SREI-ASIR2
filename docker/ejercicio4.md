# DOCKER. PRACTICA 4

### DESPLIEGUE DE LA APLICACION GUESTBOOK

Lo primero que haremos será crear una red llamada **guestbook**. Lo haremos con el comando

````
docker network create red_guestbook
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f9e21fc6-a040-47a7-b7bc-246d29b8be97)

Cuando creemos la red, ejecutaremos los contenedores con los comandos

````
docker run -d --name redis --network red_guestbook -v /opt/redis:/data redis redis-server --appendonly yes

docker run -d -p 80:5000 --name guestbook --network red_guestbook iesgn/guestbook
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/cb7e6a1b-2270-4e55-84e6-4da998be89b2)

Para comprobar que hemos ejecutado los contenedores correctamente, usaremos el comado 

````
docker ps -a
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f821fb2c-b4df-4432-a561-b624a5cc2be3)

Una vez hayamos hecho todos los pasos, nos iremos a nuestro navegador web y escribiremos lo siguiente

````
http://localhost
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/271f80ab-bde8-4b3e-b003-f07d786cd7f9)

### DESPLIEGUE DE LA APLICACION TEMPERATURAS

Lo primero que haremos será crear una red llamada **temperaturas**. Lo haremos con el comando

````
docker network create red_temperaturas
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/51a1384f-1232-4b7a-96e8-97d62751da13)

Cuando creemos la red, ejecutaremos los contenedores con los comandos

````
docker run -d --name temperaturas-backend --network red_temperaturas iesgn/temperaturas_backend

docker run -d -p 80:3000 --name temperaturas-frontend --network red_temperaturas iesgn/temperaturas_frontend
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/ef86071a-4d19-480e-8797-f270df23341b)

Para comprobar que hemos ejecutado los contenedores correctamente, usaremos el comado 

````
docker ps -a
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a5d97824-23fc-4fbd-ad4e-39c13d77d669)

Una vez hayamos hecho todos los pasos, nos iremos a nuestro navegador web y escribiremos lo siguiente

````
http://localhost
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/829c549e-b95e-478c-a4da-0b82aa353f00)








