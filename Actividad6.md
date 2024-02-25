# ACTIVIDAD 6 --> PROFTPD - TLS

### EJERCICIO 1:  Instala filezilla

Para instalar el filezilla, usaremos el comando.

````
sudo apt install filezilla
````

En mi caso ya lo tengo instalado y vemos que tengo instalado la ultima version.

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/a4fc78a0-f028-448c-97f0-214f96fce0dd)



### EJERCICIO 2: Configura filezilla para usar una conexión TLS y comprueba que funciona correctamente.

Lo primero que haremos será irnos al archivo de configuración y lo editaremos de la siguiente manera.

````
sudo nano /etc/proftpd/proftpd.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/9aa0afaf-4342-484d-b0ad-bfce9fa3731a)

Luego vamos a editar el archivo de configuración "**modules.conf**" con el comando.

````
sudo nano /etc/proftpd/modules.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/0447f796-fbf6-4347-9744-f9415ede36aa)

El siguiente paso que haremos será instalar el servicio "**proftpd-mod-crypto**" con el comando.

````
sudo apt install proftpd-mod-crypto
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/16fd6833-779b-48aa-82a7-c1e164743686)

Cuando lo hayamos instalado correctamente, entraremos en el archivo de configuracion "**tls.conf**" y lo editaremos de la siguiente manera.

````
sudo nano /etc/proftpd/tls.conf
````

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/3e0d1f20-0a34-4fa5-9c2d-b8331eca93ae)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/38f4eb62-2880-476f-9ebd-0090e0ea756f)

![image](https://github.com/Josex02/SREI-ASIR2/assets/91255971/f5cbb264-48a3-422b-bcbf-fa6b2fcb4508)











