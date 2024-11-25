# PRACTICA 2
## Por David Rubio (Dominio: elpais.com)

### Herramienas de diagnostico
* #### Busca la IP asignada
Para ello simplemente ejecutamos el comando: "host elpais.com" 
![Captura de terminal con comando host](assets/IP_Asignada.png)
* #### Quien resuelve su DNS
Para averiguar quien devuelve el DNS ejecutamos el comando "dig elpais.com NS" y nos devuelve con un poco de busqueda en google (whois) que pertenece auna empresa llamada "Akamai Technologies, Inc."
![Captura de terminal con comando dig](assets/DNS%20asignados.png)
* #### Cuál es el servidor de correo electrónico. Si hay varios, determina cual es primero por su prioridad.
Utilizando el comando "host -t MX elpais.com" nos devuelve que hay 2 servidores de correos siendo el 1 el prioritario pues tienes menor numero
![Captura de terminal con comando host MX](assets/Mail_prioridad.png)
* #### Haz la búsqueda de forma autorizada, es decir, que el servidor que contesta sea uno de los registos NS del dominio.
Para realizar una busqueda autorizada le preguntaremos al DNS que nos ha devuelto antes el comando dig
![Captura de terminal con busqueda autorizada DNS](assets/Busqueda_autorizada.png)

### Suplantar DNS localmene
Primero modificaremos el archivo "/etc/host" para añadir los directorios
![Captura del archivo /etc/host editado](assets/DNS_Secuestrado_01.png)
Luego provamos con el comando Host que el cambio funciona
![Captura de terminal con host](assets/DNS_Secuestrado_02.png)
Finalmente le preguntamos a google al respecto
![Captura de terminal con dig con google](assets/DNS_Secuestrado_03.png)
![Captura de terminal con dig con google](assets/DNS_Secuestrado_04.png)
![Captura de terminal con dig con google](assets/DNS_Secuestrado_05.png)

### Configuracion del servidor DNS con BIND9

Empezamos instalando Bind9 en el servidor y habilitando el proceso
![Captura de servidor con el status de bind9](assets/Bind9_instalado.png)
Configuramos la zona
![Captura de servidor con configuracion de zona](assets/Bind9_config_01.png)
![Captura de servidor con el status de bind9](assets/Bind9_config_02.png)
Y comprobamos que se ha formado bien
![Captura de servidor con el status de bind9](assets/Bind9_config_03.png)
Aqui me da un fallo que no consigo solucionar, no se si he instalado algo mal o tengo algun fallo por atras
Si hubiera salido bien habria que comprobarlo con los comandos dig y nslookup los dominios establecidos


