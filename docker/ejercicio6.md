# DOCKER. PRACTICA 6

### CONTRUCCION DE IMAGENES CON UNA PAGINA ESTATICA

Lo primero que tenemos que hacer, será crear un directorio (lo he llamado **docker6**) usando el comando

````
mkdir docker6
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/15e1875e-470b-448c-906b-f637f9c5477e)

Cuando ya creemos el directorio, vamos a crear dos archivo, uno **public_html** donde crearemos nuestro archivo html y otro archivo llamado **dockerfile** donde crearemos la imagen.

Lo primero que haremos será crear el archivo **public_html** y lo editaremos con las siguientes lineas.

````
sudo nano public_hmtl
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2c99dcec-23be-4c94-aa0c-b222f308e2c2)

Luego, crearemos el archivo **dockerfile** y le añadiremos las siguientes lineas

````
sudo nano dockerfile
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/4c19d05a-f4b0-478f-897a-fa138f0553de)

Una vez hayamos creado los archivos correctamente, lo siguiente que haremos, será crear la imagen ejecutando el comando

````
docker build -t josex02/prueba6:v1 .
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/296d4502-a829-4ff4-9740-8aa785cd8255)

Cuando ya tengamos creada la imagen, comprobaremos si la hemos creado correctamente con el comando

````
docker images
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1a6f1b6d-76a2-4256-a016-97af94dd17f7)

Por ultimo una vez hecho todos los pasos anteriores, vamos a crear el contenedor con el comando

````
$ docker run -d -p 80:80 --name docker6 josex02/prueba6:v1
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/76c16b1b-a630-4a35-a9cd-23c69839c858)

Ahora vamos a comprobar que hemos hecho todos los pasos correctamente. Lo haremos en nuestro navegador y escribiremos lo siguiente

````
http://localhost/public_html
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/1222174d-07cb-451b-be4b-2535ea4db4bc)

### CONSTRUCCION DE IMAGENES CON UNA APLICACION PHP

Lo primero que tenemos que hacer, será crear un directorio (lo he llamado **docker6:2**) usando el comando

````
mkdir docker6:2
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/077c9683-8038-4c82-822f-fc88ed2c0fbb)


Cuando ya creemos el directorio, vamos a crear dos archivo, uno **app** donde crearemos nuestro archivo html y otro archivo llamado **dockerfile** donde crearemos la imagen.

Lo primero que haremos será crear el archivo **app** y lo editaremos con las siguientes lineas.

````
sudo nano app
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a8618b9f-7591-4cc4-9f6b-d064f76b03ce)

Luego, crearemos el archivo **dockerfile** y le añadiremos las siguientes lineas

````
sudo nano dockerfile
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3b8c2adc-ebff-4114-abe5-6ae8ffefbf2a)

Una vez hayamos creado los archivos correctamente, lo siguiente que haremos, será crear la imagen ejecutando el comando

````
docker build -t josex02/prueba6.2:v1 .
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/70ff45d3-b37f-45fb-a3a2-ca6554ac40df)

Cuando ya tengamos creada la imagen, comprobaremos si la hemos creado correctamente con el comando

````
docker images
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/b031b120-2c79-4fd8-802c-3dd93efb1ed2)

Por ultimo una vez hecho todos los pasos anteriores, vamos a crear el contenedor con el comando

````
$ docker run -d -p 80:80 --name docker6.2 josex02/prueba6.2:v1
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a6311907-7c84-4696-a384-c5aaa4d3d8ea)

Ahora vamos a comprobar que hemos hecho todos los pasos correctamente. Lo haremos en nuestro navegador y escribiremos lo siguiente

````
http://localhost/app
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/2c3434c4-aacb-4984-b3b9-6e5dc671427a)


### CONSTRUCCION DE IMAGENES CON UNA APLICACION PYTHON

Lo primero que tenemos que hacer, será crear un directorio (lo he llamado **docker6:2**) usando el comando

````
mkdir prueba6.3
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/fce955df-7949-4150-9d31-6cd1ddb9edd9)

Cuando ya creemos el directorio, vamos a crear dos archivo, uno **public_html** donde crearemos nuestro archivo html y otro archivo llamado **dockerfile** donde crearemos la imagen.

Lo primero que haremos será crear el archivo **public_html** y lo editaremos con las siguientes lineas.

````
sudo nano app
````






