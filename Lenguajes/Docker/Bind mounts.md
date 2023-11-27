# Bind mounts

Un **bind mount** es otro tipo de montaje que nos permite compartir un directorio desde el sistema de archivos del host al contenedor. Cuando trabaja en una aplicación, puede utilizar un montaje de enlace para montar el código fuente en el contenedor. El contenedor ve los cambios que realiza en el código inmediatamente, tan pronto como guarda un archivo. Esto significa que puede ejecutar procesos en el contenedor que detectan cambios en el sistema de archivos y responden a ellos.

El uso de montajes vinculados es común para las configuraciones de desarrollo local. La ventaja es que la máquina de desarrollo no necesita tener instalados todos los entornos y herramientas de compilación. Con un solo comando de ejecución de Docker, Docker extrae dependencias y herramientas.

Para realizar esto podemos utilizar la siguiente secuencia de comandos

```powershell
docker run -dp 127.0.0.1:3000:3000 `
    -w /app --mount "type=bind,src=$pwd,target=/app" `
    node:18-alpine `
    sh -c "npm install && npm run dev"
```

El siguiente es un desglose del comando:

- `-dp 127.0.0.1:3000:3000`: Ejecute en modo independiente (en segundo plano) y cree una asignación de puertos
- `-w /app` : establece el "directorio de trabajo" o el directorio actual desde donde se ejecutará el comando
- `--mount "type=bind,src=$pwd,target=/app"`: enlazar montar el directorio actual desde el host al `/app`directorio en el contenedor
- `node:18-alpine`: la imagen a utilizar. Tenga en cuenta que esta es la imagen base de su aplicación desde Dockerfile.
- `sh -c "npm install && npm run dev"`- El comando. Está iniciando un shell usando `sh`(alpine no tiene `bash`) y ejecutándolo `npm install`para instalar paquetes y luego ejecutando `yarn run dev`para iniciar el servidor de desarrollo. Si miras en `package.json`, verás que con `dev`se inicia el script `nodemon`.