
Los ejecutores de tareas ejecutan automáticamente comandos y llevan a cabo procesos entre bastidores. Esto ayuda a automatizar su flujo de trabajo al realizar tareas mundanas y repetitivas que, de otro modo, perdería una gran cantidad de tiempo repitiéndolas.

Task Runner son herramientas para simplificar ciertas tareas tediosas de desarrollo, como la automatización de la compilación sass/scss, la agrupación de activos, el código fuente de linting y la recarga en caliente del servidor local.

Una forma es creando un archivo **script.sh** y luego ejecutarlo en la consola. 

**Dato**: Puedo crear un archivo script.sh que tenga comandos de git para poder crearme la estructura de carpetas de mi proyecto. Luego debo poner ./url del archivo script.sh y ejecuto.

```sh
//Ejemplo
#!/bin/bash

mkdir -p src

# Crear las carpetas assets y css dentro de src. Tambien crear las carpetas sass

mkdir -p src/assets

mkdir -p src/css

mkdir -p src/assets

mkdir -p src/assets/img

mkdir -p scss

# Crear los archivos de css

touch src/css/style.css

touch src/css/normalize.css

touch src/index.html

touch scss/main.scss

touch scss/_variables.scss
```


[[NPM scripts]]