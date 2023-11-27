# Docker Remoto

Para compartir imágenes de Docker, se debe utilizar un registro de Docker. El registro predeterminado es Docker Hub y es de donde provienen todas las imágenes que ha utilizado.

Un registro de Docker almacena imágenes de Docker. Docker Hub es un registro público que cualquiera puede usar y Docker busca imágenes en Docker Hub de forma predeterminada. Incluso puedes ejecutar tu propio registro privado.

Cuando usa los comandos `docker pull` (para traer una imagen ) o `docker run` (traer una imagen y crea un container), Docker extrae las imágenes requeridas de su registro configurado o de otros registros que se pueden buscar en dockerhub como por ejemplo el de mysql o node. Cuando usa el `docker push` comando, Docker envía su imagen a su registro configurado.

Para iniciar sesion en Docker Hub usamos el comando `docker login -u nombreUsuario`

Podemos utilizar `docker tag nombre tag nombreImage/repositorio` para ponerle una etiqueta a nuestra imagen. Si no especifica una etiqueta, Docker usa una etiqueta llamada `latest`.

Luego para iniciar un contenedor remoto utilizamos `docker run -dp puestos nombreUsuario/nombreRepositorio:nombreEtiquetaImagen`

Ejemplo

```poweshell
docker run -dp 0.0.0.0:3000:3000 YOUR-USER-NAME/repositorio:etiqueta
```