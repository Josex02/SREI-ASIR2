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

### DESDE UNA IMAGEN CON APACHE2







