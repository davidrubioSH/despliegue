# Práctica de despliegue con Docker
## Practica de David Rubio

## Objetivo

- Debes desplegar las siguientes aplicaciones:
  - https://github.com/rafacabeza/demoapinode
  - https://github.com/rafacabeza/demoappphp
- Debes usar un contenedor con un proxy.
- Debes usar un contenedor por cada aplicación y dos contenedores de bases de datos.
- Opcionalmente puedes usar contenedores para phpmyadmin
- Las aplicaciones serán app1.local y app2.local.

## Desarrollo de la práctica

- Para hacerlo debes usar un único fichero docker-compose.yml teniendo en cuenta lo siguiente:
  - Inicia el proceso clonando el repositorio entornods(https://github.com/rafacabeza/entornods)
  - Elimina el servicio web1
  - Comprueba que funciona correnctamente el sitio web2.com (deberas editar el fichero hosts)
  - Deja una única red (network) en todos los contenedores. Llámale como consideres.

> [!NOTE]  
> Se ha modificado el archivo /etc/host para incluir los dominios

![Captura de la configuracion del proxy](assets/Captura_proxy_01.png)

### Sitio app1.local

- Añade un servicio db1 (puedes renombrar el servicio db como db1)
  - El volumen de datos debe llamarse volumen1 y debe gestionarlo docker
  - Debes usar una base de datos llamda dbapp1 
  - Debes usar un usuario user1 y contraseña secret
  - Carga el sql correspondiente. Puedes hacerlo con phpmyadmin o mediante consola (docker exec -it <contenedor> mysql ....).

![Captura de la configuracion de la database 1](assets/Captura_app1_db_01.png)

> [!NOTE]  
> Se ha cargado los datos en el contenedor db1

- Añade un servicio app1 para que sirva la aplicación "demoapinode". 
  - Descarga la aplicación en "entornods/demoapinode".
  - Fíjate en el docker-compose.yml que hay en el repositiro, te ayudará a definir el servicio en tu docker-compose pero deberás modificar algunas cosas.
  - Deberás añadir en variable de entorno "VIRTUAL_HOST", fíjate en web2
  - Revisa el resto de parámetros
  
![Captura de la configuracion del la app1](assets/Captura_app1_app_01.png)

> [!NOTE]  
> Se ha modificado el archivo /models/db.js para acceder correctamente a la base de datos

- Comprueba que funciona la ruta: http://app1.local

![Captura del funcionamiento de app1](assets/Captura_app1_funcionando.png)

### Sitio app2.local

- Añade un servicio db2 para la base de datos de "demoappphp"
  - El volumen de datos debe llamarse volumen2 y debe gestionarlo docker
  - Debes usar una base de datos llamda dbapp2 
  - Debes usar un usuario user2 y contraseña secret
  - Carga el sql correspondiente. De nuevo, puedes usar phpmyadmin o la consola.

![Captura de la configuracion de la database 2](assets/Captura_app2_db_01.png)

> [!NOTE]  
> Se ha cargado los datos en el contenedeor db2

- Añade un servicio app2 que sirva la aplicación "demoappphp"
  - Descarga la aplicación en "entornods/demoappphp".
  - Fíjate en el docker-compose.yml que ha en repositorio, te ayudará a definir el servicio en tu docker-compose pero deberás modificar algunas cosas.
  - Deberás añadir en variable de entorno "VIRTUAL_HOST", fíjate en web2

![Captura de la configuracion del la app2](assets/Captura_app2_app_01.png)

> [!NOTE]  
> La direccion de volumenes es erronea, la correcta es ./demoappphp/app:/var/www/html

> [!NOTE]  
> Se ha modificado el archivo /app/index.php para acceder correctamente a la base de datos

- Comprueba que funciona la ruta: http://app2.local/api/deseos

![Captura del funcionamiento de app2](assets/Captura_app2_funcionando.png)



