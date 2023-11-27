# Multiples contenedores

En general, cada contenedor debe hacer una cosa y hacerlo bien. Las siguientes son algunas razones para ejecutar el contenedor por separado:

- Es muy probable que tengas que escalar las API y las interfaces de forma diferente a las bases de datos.
- Los contenedores separados le permiten versionar y actualizar versiones de forma aislada.
- Si bien puede utilizar un contenedor para la base de datos localmente, es posible que desee utilizar un servicio administrado para la base de datos en producción. Entonces no querrás enviar tu motor de base de datos con tu aplicación. Por lo que podemos utilizar un contenedor que ejecute una base de datos externas como mysql o supabase.
- La ejecución de múltiples procesos requerirá un administrador de procesos (el contenedor solo inicia un proceso), lo que agrega complejidad al inicio/apagado del contenedor.

Mediante la creacion de redes podemos permitir que un container se comunique con otro. Si hay dos container en la misma red, se van a poder comunicar.

Hay dos formas de colocar un contenedor en una red:

- Asigne la red al iniciar el contenedor.
- Conecte un contenedor que ya se esté ejecutando a una red.

Para crear una red utilizamos el siguiente comando

```powershell
docker network create todo-app
```

Para ver las redes que hay utilizamos:

```powershell
docker network ls
```

Para ver los contenedores que hay en una red utilizamos:

```powershell
docker network inspect my-network
```

Para que otro contenedor se conecte a la red lo que hacemos es lo siguiente:

```powershell
docker run -d `
    --network todo-app --network-alias mysql `
    -v todo-mysql-data:/var/lib/mysql ` 
    -e MYSQL_ROOT_PASSWORD=secret ` //variables
    -e MYSQL_DATABASE=todos ` //variables
    mysql:8.0

```

Notarás un volumen nombrado `todo-mysql-data`en el comando anterior que está montado en `/var/lib/mysql`, que es donde MySQL almacena sus datos. Sin embargo, nunca ejecutaste un  comando `docker volume create`. Docker reconoce que desea utilizar un volumen con nombre y crea uno automáticamente.

Otro ejemplo:

```powershell
docker run -it --network todo-app nicolaka/netshoot
```

Luego para confirmar que tengo la base de datos en funcionamiento, me conecto a la base de datos con el siguiente comando. El comando `exec` es para ingresar a un contenedor.

```powershell
docker exec -it <mysql-container-id> mysql -u root -p
```

Y ahi ya puedo utilizar comandos SQL, para salir del shell MySQL pongo exit.

[[Docker compose]]