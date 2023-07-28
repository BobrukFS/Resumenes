# Vite

Vite es una herramienta de compilacion que tiene como objetivo proporcionar una experiencia de desarrollo mas rapida y agil para proyectos modernos.

* Nos da un servidor de desarrollo que proporciona amplias mejores de caracteristicas sobre los modulos ES nativos, por ejemplo, Hot Modulo Replacement (HMR) extremadamente rapido lo que permite que no se vuelva a pintar toda la pagina si no el componente que se cambia.

* Un comando de compilacion que agrupa su codigo con Rollup, preconfigurado para generar activos estaticos altamente optimizados para produccion.

## Iniciando vite

Al utilizar **npm create vite@latest nombre del desktop** creamos una nueva plantilla del proyecto que estara lista para su desarrollo. El comando automatizara la configuracion inicial, lo que significa que no tenemos que establecer manualmente la estructura del proyecto o las dependencias basicas. Si nosotros en vez del nombre del desktop le ponemos **.** se creara en la carpeta actual. Ademas, podemos utilizar plantillas creadas por la comunidad, para ello utilizamos **npx degit user/project#main my-project**.

Luego podemos utilizar **npm install** para installar las dependencias (package.json) y **npm run dev** para levantar el servidor de desarrollo.

**Dato**: Para terminar el servidor de desarrollo hago control + c.

Luego de terminado el proyecto debemos usar **npm run build** para convertirlo en una **version de distribucion** con lo que voy a subir a internet, es decir lo buildea en una carpeta llamada **dist**. Es decir para construir el proyecto para subirlo al servidor.

**Dato**: Para configurar debo crear un archivo **vite.config.js** para activar cosas que no esten activas. Ejemplo css devSourcemap, a true que agrega el css al style.

**Dato**: Vite ya viene con postCSS y le puedo instalar otras dependencias como SASS, etc. Para usar postCSS tengo que agregar .postcssrc.json y agregarle

```json
{
    "map": true,
    "plugins": {
      "autoprefixer": {}
    }
  }
```


https://vitejs.dev/