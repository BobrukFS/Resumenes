# Caracteristicas basicas NextJS

Para crear una aplicacion con nextJS debemos utilizar npm create-next-app nombre de la aplicacion

Next JS es un framework de react que brinda componentes basicos para crear aplicaciones web.

Puede usar React para crear su interfaz de usuario y luego adoptar gradualmente las funciones de Next.js para resolver los requisitos comunes de las aplicaciones, como enrutamiento, obtención de datos e integraciones, todo mientras mejora la experiencia del desarrollador y del usuario final.

NextJS se basa en react y lo une con un backend de nodeJS para que se pueda hacer un renderizado del lado del servidor lo que mejora el CEO y la carga

NextJS permite generar API de backend facilmente.

npm create-next-app para crear un proyecto con next.js y luego nos pregunta como queremos configurarlo


- **`/app`**: Contiene todas las rutas, componentes y lógica de su aplicación; aquí es desde donde trabajará principalmente.
- **`/app/lib`**: Contiene funciones utilizadas en su aplicación, como funciones de utilidad reutilizables y funciones de recuperación de datos.
- **`/app/ui`**: contiene todos los componentes de la interfaz de usuario para su aplicación, como tarjetas, tablas y formularios. Para ahorrar tiempo, hemos prediseñado estos componentes para usted.
- **`/public`**: Contiene todos los activos estáticos de su aplicación, como imágenes.
- **`/script/`**: Contiene un script de inicialización que utilizará para completar su base de datos en un capítulo posterior.
- **Archivos de configuración** : también notará archivos de configuración, como los que `next.config.js`se encuentran en la raíz de su aplicación. La mayoría de estos archivos se crean y preconfiguran cuando inicias un nuevo proyecto usando `create-next-app`. No necesitarás modificarlos en este curso.






## Rutas en NextJS

En la carpeta app va a ser donde va a estar mi aplicacion, page.jsx ees la ruta que visitamos, page puede ser .js o .jsx o tsx. Al crear page se crea un archivo layout

page seria la ruta inicial

Si tengo dos page o quiero tener dos paginas, creo una carpeta por ejemplo about y dentro de esta le pongo un archivo page.jsx

NextJS detecta al archivo page como ruta.

Entonces por ejemplo tengo el localhost:3000/contact y si anido una carpeta dentro de contact con page.jsx puedo poner por ejemplo localhost:3000/tienda/categoria/computadoras

Sistema de enrutamiento routing basado en archivos,

El layout.js este layout puede ser un jsx o tsx el contenedor de toda la aplicacion, el prop children es cada pagina que visitemos, es decir una ruta creo.

El layout es un componente que podemos llamarlo como querramos y dentro vamos a retornar un html, por ejemplo si en el body tenemos un nav bar, ese navbar se vera en todas las paginas que visite, por eso al poner children es cada pagina que nosotros creemos es decir cada carpeta con page.jsx. El layout engloba todas las paginas

Tambien tenemos un export const metadata

Tenemos el const metadata que es donde va lo que seria el head en el html

Next tiene otra forma de añadir el HEAD que es atraves de la metadata

Cualquier archivo que no tenga el nombre layout.jsx o page.jsx sera ignorado para el enrutamiento.
### Link

por ejemplo a href="/about" pero al utilizar a se vuelve a cargar ya que la pagina se pide en el servidor, esto no es ideal para una aplicacion de react ya que este evite que la pagina se reinicie, entonces para evitar esto utilizamos Link para ello importamos Link from 'next/link'

Si busco una pagina que no existe vamos a ver una pagina ya personalizada con un error 404 que viene ya en nextjs. Podemos alterar o crear nuestra pagina not found, creando un archivo not-found.jsx, ahi llegaras al poner una pagina que no existe

### Layout

Lo que nos permite hacer Layout es que nos permite crear varios layout para cada componente que querramos englobar. Por ejemplo, si quiero que en tienda tenga una subnavegacion que solo aparezca en tienda

#### Metadata

Podemos exportar una constante que es metadata, este es un json, que va a tener por ejemplo title: "titulo de la pagina". Nextjs automaticamente  pone un head con la metadata automaticamente. Podemos hacer por ejemplo tambien que en otro layout de otro componente cambie la metadata, por ejemplo el title.

El metadata solo funciona en paginas que son del lado del servidor.
### Fuentes

Con nextJS podemos importar fuentes con google fonts haciendo import {Roboto} from "next/font/google";

Entonces al ser una funcion debemos ejecutarla

Roboto({
weight : ["300", "400"]
})

### React server components

Los manejadores de eventos no pueden pasarse a componentes clientes (de react) como props.

Todos los componentes que cree anteriormente son componentes de servidor, por lo que para que un onclick por ejemplo funcione tiene que ser un componente del lado del cliente. Lo mismo para los hooks de react, o el uso de window ya que window es un objeto del frontend.

Para ello utilizo "use client"

Si un componente esta dentro de otro componente que esta marcado como "use client" hereda esa caracteristica y puede manejar estados, hooks de react, etc. 

Pero tambien puedo indicar "use client" solo al componente que lo necesito.






Para mejorar la experiencia de navegación, el código de Next.js divide automáticamente su aplicación por segmentos de ruta. [Esto es diferente de un React SPA](https://developer.mozilla.org/en-US/docs/Glossary/SPA) tradicional.[](https://developer.mozilla.org/en-US/docs/Glossary/SPA), donde el navegador carga todo el código de su aplicación en la carga inicial.

Dividir el código por rutas significa que las páginas quedan aisladas. Si una determinada página arroja un error, el resto de la aplicación seguirá funcionando.

Además, en producción, siempre que[`<Link>`](https://nextjs.org/docs/api-reference/next/link)Los componentes aparecen en la ventana gráfica del navegador, Next.js **precarga** automáticamente el código para la ruta vinculada en segundo plano. Cuando el usuario hace clic en el enlace, el código de la página de destino ya estará cargado en segundo plano, ¡y esto es lo que hace que la transición de la página sea casi instantánea!