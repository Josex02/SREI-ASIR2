# DOCKER. PRACTICA 5

### DESPLIEGUE DE MLA APLICACION GUESTBOOK

Lo primero que tendremos que hacer será crear un archivo compose, usando el comando

````
sudo nano docker-compose.yml
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e189641f-5ad4-48e8-8537-538b0ed1b716)

Cuando lo hayamos creado, le añadiremos las siguientes lineas dentro del archivo.

````
version: '3.1'
services:
  app:
    container_name: guestbook
    image: iesgn/guestbook
    restart: always
    environment:
      REDIS_SERVER: redis
    ports:
      - 8080:5000
  db:
    container_name: redis
    image: redis
    restart: always
    command: redis-server --appendonly yes
    volumes:
      - redis:/data
volumes:
  redis:
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/7700a41a-eafc-4c56-8cf8-846672d9d4fc)

Ahora, cuando hayamos añadido las lineas en el archivo, ejecutaremos el siguiente comando para que añada los contenedores 

````
docker compose up -d
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3afd2c7c-2211-4ee6-ac38-7ae21c3f2256)

Miraremos el listado de los contenedores para asegurarnos que se nos ha añadido correctamente

````
docker compose ps
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6b9e295f-08e4-48ed-9956-520fcacf3662)

Lo siguiente que vamos a hacer será parar los contenedores, y lo haremos ejecutando el siguiente comando

````
docker compose stop
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/453957a6-5e9a-4946-aff5-578b439a052c)

Por ultimo, eliminaremos los contendores con el comando

````
docker compose down
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f42e1418-15cb-470a-92f9-7ae8a6365e32)

### DESPLIEGUE DE LA APLICACION TEMPERATURAS

Lo primero que tendremos que hacer será crear un archivo compose, usando el comando

````
sudo nano docker-compose.yml
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e189641f-5ad4-48e8-8537-538b0ed1b716)

Cuando lo hayamos creado, le añadiremos las siguientes lineas dentro del archivo.

````
version: '3.1'
services:
  frontend:
    container_name: temperaturas-frontend
    image: iesgn/temperaturas_frontend
    restart: always
    ports:
      - 8081:3000
    environment:
      TEMP_SERVER: temperaturas-backend:5000
    depends_on:
      - backend
  backend:
    container_name: temperaturas-backend
    image: iesgn/temperaturas_backend
    restart: always
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e71810ac-3203-4546-81bf-bad86ce661c4)

Ahora, cuando hayamos añadido las lineas en el archivo, ejecutaremos el siguiente comando para que añada los contenedores 

````
docker compose up -d
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/36dfd28c-f8b9-4e02-b37e-176271abcc57)

Miraremos el listado de los contenedores para asegurarnos que se nos ha añadido correctamente

````
docker compose ps
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f757b332-3004-4f28-9530-54c7cb4e5fb6)

Lo siguiente que vamos a hacer será parar los contenedores, y lo haremos ejecutando el siguiente comando

````
docker compose stop
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/28e1db33-2f51-4dd5-a066-43455e7e16f5)

Por ultimo, eliminaremos los contendores con el comando

````
docker compose down
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/6f13f2e8-433b-484e-88b3-5a1e668655d1)

### DESPLIEGUE DE WORDPRESS + MARIADB

Lo primero que tendremos que hacer será crear un archivo compose, usando el comando

````
sudo nano docker-compose.yml
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e189641f-5ad4-48e8-8537-538b0ed1b716)

Cuando lo hayamos creado, le añadiremos las siguientes lineas dentro del archivo.

````
version: '3.1'
services:
  wordpress:
    container_name: servidor_wp
    image: wordpress
    restart: always
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: user_wp
      WORDPRESS_DB_PASSWORD: asdasd
      WORDPRESS_DB_NAME: bd_wp
    ports:
      - 80:80
    volumes:
      - wordpress_data:/var/www/html/wp-content
  db:
    container_name: servidor_mysql
    image: mariadb
    restart: always
    environment:
      MYSQL_DATABASE: bd_wp
      MYSQL_USER: user_wp
      MYSQL_PASSWORD: asdasd
      MYSQL_ROOT_PASSWORD: asdasd
    volumes:
      - mariadb_data:/var/lib/mysql
volumes:
    wordpress_data:
    mariadb_data:
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/9b6b47df-0d13-4de9-bf93-0d24accd53f3)

Ahora, cuando hayamos añadido las lineas en el archivo, ejecutaremos el siguiente comando para que añada los contenedores 

````
docker compose up -d
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0b38d6cf-9070-4666-b7cc-948688b5417b)

Miraremos el listado de los contenedores para asegurarnos que se nos ha añadido correctamente

````
docker compose ps
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4f09dd8e-d080-4048-8b73-efaba96a4a2a)

Lo siguiente que vamos a hacer será parar los contenedores, y lo haremos ejecutando el siguiente comando

````
docker compose stop
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/c7244ed0-9494-4903-98f2-1f67a7c221ad)

Por ultimo, eliminaremos los contendores con el comando

````
docker compose down
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/95e3a27a-3e94-4669-be7f-8fb2f956c723)

