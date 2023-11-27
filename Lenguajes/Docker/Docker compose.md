# Docker compose

Docker Compose es una herramienta que le ayuda a definir y compartir aplicaciones de múltiples contenedores. Con Compose, puedes crear un archivo YAML para definir los servicios y con un solo comando, puedes activar o desactivar todo.

La gran ventaja de usar Compose es que puede definir la pila de su aplicación en un archivo, mantenerla en la raíz del repositorio de su proyecto (ahora tiene control de versión) y permitir fácilmente que otra persona contribuya a su proyecto.

Se debe crear un archivo llamado **compose.yaml**

```json
services: //Se crean los servicios
  app: //Servicio app
    image: node:18-alpine
    command: sh -c "yarn install && yarn run dev"
    ports:
      - 127.0.0.1:3000:3000
    working_dir: /app
    volumes:
      - ./:/app
    environment:
      MYSQL_HOST: mysql
      MYSQL_USER: root
      MYSQL_PASSWORD: secret
      MYSQL_DB: todos
  mysql: //Servicio mysql
    image: mysql:8.0
    volumes:
      - todo-mysql-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: todos
volumes:
  todo-mysql-data:


//Notarás que Docker Compose creó el volumen y también una red. De forma predeterminada, Docker Compose crea automáticamente una red específica para la pila de aplicaciones (razón por la cual no definió una en el archivo Compose).
```

Una vez creado el compose.yaml se utiliza `docker compose up -d`. 

Podemos utilizar `docker compose logs -f` para ver los registros de cada uno de los servicios entrelazados en una sola secuencia.

Para eliminar toda la pila podemos utilizar `docker compose down`

