# INSTALAR DOCKER EN UBUNTU.

Para proceder a la instalacion de **docker** en ubuntu, tendremos que seguir los siguientes pasos para su instalacion.

Lo primeto que haremos será actualizar la lista de paquetes con el comando:

````
sudo apt update
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/bc558608-e688-4413-b9ff-80b140cfe80c)

Ahora, haremos la isntalacion de algunos paquetes de requisitos de docker, ejecutaremos el comando:

````
sudo apt install apt-transport-https ca-certificates curl software-properties-common
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/d9b0fc90-e270-4375-8fd7-e52403477ad8)

Luego, añadiremos la clave de GPG para el repositorio oficial de Docker en su sistema, lo haremos con el comando:

````
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0625a490-41cc-4693-83d8-c4f292315a96)

El siguiente paso que haremos será agregar el repositorio de **Docker** a las fuentes APT con el comando:

````
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/933f14ec-1023-46d4-a3b5-b202fcd2fa15)

Para comprobar que estamos a punto de realizar la instalacion desde el repositorio de Docker ejecutaremos el comando:

````
apt-cache policy docker-ce
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e2be0229-3605-44e3-be7a-cd8215987f7f)

Una vez tengamos todos estos pasos realizados correctamente, vamos a proceder a la instalacion de **Docker**:

````
sudo apt install docker-ce
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/e86698d9-b411-461a-b5e0-827c481d05c9)

Cuando ya hayamos instalado **Docker** el dominio se nos iniciará y el proceso se habilitará para ejecutarse en el inicio, para comprobarlo ejecutaremos el comando:

````
sudo systemctl status docker
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/8f8640cd-1f7b-4a26-8cae-25f1f6561c03)

