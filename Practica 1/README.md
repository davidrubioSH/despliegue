# PRACTICA 1
## Por David Rubio

### Configuración del Ubuntu Server

* 1º Cambiamos el nombre de la maquina a server12 (12 por que es mi numero de clase) para realizar esto lo haremos con el comando "hostnamectl set-hostname server12"
* 2º Configuraremos las tarjetas de red, editando un fichero localizado /etc/netplan/00-instaler-config.yaml
![Captura de archivo de configuracion de red ya editado](/assets/Configuracion_ubuntu_server_01.png)
* 3º Confirmaremos los cambios con "netplan apply" y comprobamos que se han cambiando la ip con "ip a"
![Captura de informacion de ip de las tarjetas de red](/assets/Configuracion_ubuntu_server_02.png)

### Configuración del Ubuntu Cliente

* 1º Cambiamos el nombre de la maquina editando los ficheros de /etc/hosts y /etc/hostname
![Captura de archivo hosts editado](/assets/Configuracion_ubuntu_cliente_01.png)
![Captura de archivo hostname editado](/assets/Configuracion_ubuntu_cliente_02.png)
* 2º Ahora cambiamos manualmente la ip de la maquina mediante la ventana de dialogo en configuracion de red
![Captura de ventana de configuracion de red](/assets/Configuracion_ubuntu_cliente_03.png)
* 3º Finalmente revisamos que todo esta bien con el comando "ip a" y el "ping" 
![Captura de terminal con los comandos](/assets/Configuracion_ubuntu_cliente_04.png)

### Configuración del Windows Cliente

* 1º Cambiamos el nombre de la maquina desde la ventana en configuracion de equipo
![Captura de configurancion antes de cambiarse](/assets/Configuracion_windows_cliente_01.png)
![Captura de configuracion ya cambiada](/assets/Configuracion_windows_cliente_02.png)
* 2º Seguimos cambiando la ip de la maquina
![Captura de configuracion de ip](/assets/Configuracion_windows_cliente_03.png)
* 3º Finalizamos comprobando que se ha cambiado y que hay conexion
![Captura de terminal con los comando necesarios](/assets/Configuracion_windows_cliente_04.png)

### Configuración de Servidor DHCP

* 1º Configuramos la nueva tarjeta de red en /etc/netplan/00-instaler-config.yaml
![Captura de archivo de configuracion de red ya editado](/assets/DHCP_01.png)
![Captura de terminal mostrando los cambios](/assets/DHCP_02.png)
* 2º Instalamos el dhcp server y configuramos el rango de las ips, reiniciamos y vemos que funciona y que pasa con el puerto 67
![Captura de archivo de configuracion editado](/assets/DHCP_03_b.png)
![Captura de terminal mostrando el estado del servidor](/assets/DHCP_03.png)
![Captura de terminal mostrando el estado del servidor](/assets/DHCP_04.png)
* 3º Configuramos el cliente de Windows 10 
![Captura de terminal revocando la ip](/assets/DHCP_05.png)
![Captura de terminal renovando la ip](/assets/DHCP_06.png)
* 4º Configuramos el cliente de Ubuntu 
![Captura de terminal revocando la ip](/assets/DHCP_07.png)
![Captura de terminal renovando la ip](/assets/DHCP_08.png)
* 5º Consultamos las ip prestadas desde el servidor
![Captura de terminal mostrando las ips prestadas](/assets/DHCP_09.png)
* 6º Configuramos el equipoexterno de ip fija con la direccion mac del cliente de windows
![Captura de archivo de configuracion editado](/assets/DHCP_10.png)
* 7º Comprobamos en el cliente de Windows la ip asignada despues de renovar
![Captura de terminal mostrando la nueva ip](/assets/DHCP_11.png)
* Si se apaga el servidor la ip no varia en las maquinas salvo que se renueven o se reseten 

