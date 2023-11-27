# Objetos Docker
## Imagenes

Una imagen es una plantilla de solo lectura con instrucciones para crear un contenedor Docker. A menudo, una imagen se basa en otra imagen, con alguna personalización adicional. Por ejemplo, puede crear una imagen basada en la  imagen `ubuntu`, pero instala el servidor web Apache y su aplicación, así como los detalles de configuración necesarios para ejecutar su aplicación. 

La imagen debe contener todo lo necesario para ejecutar una aplicación: todas las dependencias, configuraciones, scripts, archivos binarios, etc. La imagen también contiene otras configuraciones para el contenedor, como variables de entorno, un comando predeterminado ejecutar y otros metadatos.

Puede crear sus propias imágenes o utilizar únicamente aquellas creadas por otros y publicadas en un registro. Para crear su propia imagen, cree un archivo Dockerfile con una sintaxis simple para definir los pasos necesarios para crear la imagen y ejecutarla. Cada instrucción en un Dockerfile crea una capa en la imagen. Cuando cambia el Dockerfile y reconstruye la imagen, solo se reconstruyen aquellas capas que han cambiado. Esto es parte de lo que hace que las imágenes sean tan livianas, pequeñas y rápidas en comparación con otras tecnologías de virtualización.

Para ejecutar correctamente otros comandos, debo estar en el directorio que contiene mi archivo Dockerfile.

```dockerfile
# Start your image with a node base image
FROM node:18-alpine

# The /app directory should act as the main application directory
WORKDIR /app

# Copia los archivos de tu proyecto al directorio de trabajo
COPY package*.json ./

# Copy local directories to the current local directory of our docker image (/app)
COPY ./src ./src
COPY ./public ./public

# Install node packages, install serve, build the app, and remove dependencies at the end
RUN npm install \
    && npm install -g serve \
    && npm run build \
    && rm -fr node_modules
EXPOSE 3000
# Start the app using serve command
CMD [ "serve", "-s", "build" ]
```

Cuando se ejecuta el comando `docker build .`, las instrucciones del archivo Dockerfile se ejecutan secuencialmente para crear la imagen. Se puede utilizar `dobker build -t nombreImagen` para nombrar a la imagen.

Ejemplo:

```powershell
docker build -t getting-started .
```

Para ver las imagenes se utiliza `docker image ls`.

Para eliminar una imagen utilizamos `docker image rm nombreImagen`
## Contenedores

Un contenedor es una instancia ejecutable de una imagen. Puede crear, iniciar, detener, mover o eliminar un contenedor mediante la API o CLI de Docker. Puede conectar un contenedor a una o más redes, adjuntarle almacenamiento o incluso crear una nueva imagen basada en su estado actual.

Un contenedor se define por su imagen, así como por las opciones de configuración que le proporciona cuando lo crea o inicia. Cuando se elimina un contenedor, cualquier cambio en su estado que no esté almacenado en un almacenamiento persistente desaparece.

- Es una instancia ejecutable de una imagen. Puede crear, iniciar, detener, mover o eliminar un contenedor mediante la API o CLI de Docker.
- Puede ejecutarse en máquinas locales, máquinas virtuales o implementarse en la nube.
- Es portátil (y puede ejecutarse en cualquier sistema operativo).
- Está aislado de otros contenedores y ejecuta su propio software, binarios, configuraciones, etc.

Para ver los contenedores que tenemos UP podemos utilizar `docker ps` o `docker container ls`.

Una vez que se haya construido la imagen, se puede ejecutar un contenedor mediante la interfaz visual de Docker Desktop o utilizando los siguiente comandos 

Para solo crear un container y no iniciarlo, ademas agregarle un nombre:

```powershell
docker create --name contenedorName nombreImagen
```

Para iniciar un container utilizamos:

```powershell
docker start contenedorName
```

Para crear el container y ejecutarlo:

Ejemplo: 

```js
docker run -dp 127.0.0.1:3000:3000 getting-started

/* La `-d`bandera (abreviatura de `--detach`) ejecuta el contenedor en segundo plano. La `-p`bandera (abreviatura de `--publish`) crea una asignación de puertos entre el host y el contenedor, es decir mapeamos un puerto de nuestra pc al container. La `-p`bandera toma un valor de cadena en el formato de `HOST:CONTAINER`, donde `HOST`es la dirección en el host y `CONTAINER`es el puerto en el contenedor. El comando publica el puerto 3000 del contenedor en `127.0.0.1:3000`( `localhost:3000`) en el host. */
```

**Dato**: Solo un proceso en la máquina (incluidos los contenedores) puede escuchar un puerto específico.

Para detener el contenedor utilizamos `docker stop id_container` y luego lo podemos eliminar mediante `docker rm id_container`. Podemos realizar ambas acciones al mismo tiempo mediante
`docker rm -f id_container`.

Para ver los logs de los containers uso `docker logs -f containerID`

