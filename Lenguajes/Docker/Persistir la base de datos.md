# Persistir la base de datos
Cuando se ejecuta un contenedor, utiliza las distintas capas de una imagen para su sistema de archivos. Cada contenedor también tiene su propio "espacio temporal" para crear/actualizar/eliminar archivos. Los cambios no se verán en otro contenedor, incluso si usan la misma imagen. Con los volúmenes, puedes cambiar todo esto.
## Volumenes

Los volúmenes brindan la capacidad de conectar rutas específicas del sistema de archivos del contenedor a la máquina host. Si monta un directorio en el contenedor, los cambios en ese directorio también se ven en la máquina host. Si monta ese mismo directorio al reiniciar el contenedor, verá los mismos archivos.

Los volúmenes se utilizan a menudo para almacenar datos que deben persistir entre reinicios del contenedor, como datos de usuario, archivos de configuración o archivos de registro. También se pueden utilizar para compartir datos entre contenedores.

Para crear un volumen utilizamos `docker volume create nombreVolume` o podemos utilizar la interfaz de Docker Desktop.

Luego iniciamos el contenedor de la aplicacion pero agregando la flag `--mount` para especificar un montaje de volumen.

Ejemplo:

```powershell
docker run -dp 127.0.0.1:3000:3000 --mount type=volume,src=todo-db,target=/etc/todos getting-started
```

Para saber donde almacena Docker mis datos cuando uso un volumen utilizo `docker volume inspect`. Mountpoint es la ubicacion real de los datos en el disco.

[[Bind mounts]]