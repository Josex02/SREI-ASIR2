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

### DESPLIEGUE DE WORDPRESS + MARIADB

Lo primero que haremos será crear una red llamada **temperaturas**. Lo haremos con el comando

````
docker network create red_wp
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/01933636-3d15-4cdd-abea-abd21a1057cb)

Cuando creemos la red, ejecutaremos los contenedores con los comandos

````
docker run -d --name servidor_mysql \
                --network red_wp \
                -v /opt/mysql_wp:/var/lib/mysql \
                -e MYSQL_DATABASE=bd_wp \
                -e MYSQL_USER=user_wp \
                -e MYSQL_PASSWORD=asdasd \
                -e MYSQL_ROOT_PASSWORD=asdasd \
                mariadb
                
docker run -d --name servidor_wp \
                --network red_wp \
                -v /opt/wordpress:/var/www/html/wp-content \
                -e WORDPRESS_DB_HOST=servidor_mysql \
                -e WORDPRESS_DB_USER=user_wp \
                -e WORDPRESS_DB_PASSWORD=asdasd \
                -e WORDPRESS_DB_NAME=bd_wp \
                -p 80:80 \
                wordpress
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/48ac951b-fe0a-4222-8c77-8065c1b51940)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/5699e3b5-762f-4288-bea4-79a788fc5248)

Para comprobar que hemos ejecutado los contenedores correctamente, usaremos el comado 

````
docker ps -a
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2032afbd-9a97-4c41-bbe7-a7d0f5df2cc9)

Una vez hayamos hecho todos los pasos, nos iremos a nuestro navegador web y escribiremos lo siguiente

````
http://localhost
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0774933e-2917-4593-a78e-c56bdaffc303)





