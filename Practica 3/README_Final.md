> [!NOTE]  
> Este es el Markdown Realizado despues de la practica, no contiene nada hecho posteriormente, solo arregla y añade las imagenes al archivo original

# PRACTICA 3
## Por David Rubio 

IMPORTANTE: No me pude conectar al servidor de la practica asi que lo realizare en el servidor de clase

### Sitios Web - Configuracion Inicial
* Creamos las carpetas de los sitios web en '/var/www'
![Captura de un ls en la carpeta /var/www](assets/Captura_01.png)
![Captura de terminal con el index.html de la web1](assets/Captura_02.png)
![Captura de terminal con el index.html de la web2](assets/Captura_03.png)
![Captura de terminal con el index.html de la web3](assets/Captura_04.png)
![Captura de terminal con el index.html de la web4](assets/Captura_05.png)
* Modificamos el archivo '/etc/hosts' de la maquina cliente
![Captura de terminal con el archivo etc/hosts modificado](assets/Captura_06.png)
### Sitio 1
* Inicializamos el servicio de apache2 'sudo systemctl start apache2'
* Nos movemos a la carpeta '/etc/apache2/sites-available/'
* Creamos un fichero llamado web1.conf y lo rellenamos
![Captura de terminal con el archivo web1.conf](assets/Captura_07.png)
* Activamos el sitio con 'sudo a2ensite web1.conf'
![Captura de terminal con los comando de activacion del sitio](assets/Captura_08.png)
* Recargamos el servidio apache2
* Comprobamos que funciona
![Captura de navegador con la pagina web1](assets/Captura_09.png)
### Sitio 2
Exactamente Igual que el Sitio 1
* En la carpeta '/etc/apache2/sites-available/'
* Creamos un fichero llamado web2.conf y lo rellenamos
![Captura de terminal con el archivo web2.conf](assets/Captura_10.png)
* Activamos el sitio con 'sudo a2ensite web2.conf'
![Captura de terminal con los comando de activacion del sitio](assets/Captura_11.png)
* Recargamos el servidio apache2
* Comprobamos que funciona
![Captura de navegador con la pagina web1](assets/Captura_12.png)
### Sitio 3
> [!NOTE]  
> Como estoy usando mi maquina virtual no necesito instalar ni activar ssl para las claves, se haria de la siguiente forma:
* Primero instalaria open ssl en la maquina con 'sudo apt install openssl'
* Luego con el servidor avierto activaria el modulo de ssl con 'sudo a2enmod ssl'
* Ahora creamos el cerfificado y la clave con el siguiente comando
![Captura de terminal con el comando ssl](assets/Captura_13.png)
* Creamos el archivo web3.conf en '/etc/apache2/sites-available/'
![Captura de terminal con el archivo web3.conf](assets/Captura_14.png)
* Recargamos el servicio y comprobamos que funcione
![Captura de terminal recargando el servicio](assets/Captura_15.png)
* En este caso algo va mal y no abre el puerto 443, por lo que el https jamas carga
![Captura de terminal mostrando los puertos en uso](assets/Captura_16.png)
### Sitio 4
* Inicializamos el servicio de apache2 'sudo systemctl start nginx'
* Nos movemos a la carpeta '/etc/anginx/sites-available/'
* Creamos un fichero llamado web4 y lo rellenamos
![Captura de terminal con el archivo web4.conf](assets/Captura_17.png)
* Activamos el sitio con una tuberia
* Recargamos el servidio nginx
![Captura de terminal con los comando de activacion del sitio](assets/Captura_18.png)
* y Comprobamos que funciona
![Captura de navegador con la pagina web1](assets/Captura_19.png)
### Proxy
* No me ha dado tiempo a terminarlo, esto es el archivo de configuracion que tenia echo antes de la entrega
![Captura de terminal con el archivo proxy](assets/Captura_20.png)







