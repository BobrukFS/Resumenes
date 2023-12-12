# Caracteristicas basicas NextJS

Para crear una aplicacion con nextJS debemos utilizar npm create-next-app nombre de la aplicacion

Next JS es un framework de react que brinda componentes basicos para crear aplicaciones web.

Puede usar React para crear su interfaz de usuario y luego adoptar gradualmente las funciones de Next.js para resolver los requisitos comunes de las aplicaciones, como enrutamiento, obtención de datos e integraciones, todo mientras mejora la experiencia del desarrollador y del usuario final.

NextJS se basa en react y lo une con un backend de nodeJS para que se pueda hacer un renderizado del lado del servidor lo que mejora el CEO y la carga

NextJS permite generar API de backend facilmente.

npx create-next-app para crear un proyecto con next.js y luego nos pregunta como queremos configurarlo

## Arquitectura de carpetas en un proyecto NextJS

- **`/app`**: Contiene todas las rutas, componentes y lógica de su aplicación; aquí es desde donde trabajará principalmente.
- **`/app/lib`**: Contiene funciones utilizadas en su aplicación, como funciones de utilidad reutilizables y funciones de recuperación de datos a una base de dato o api.
- **`/app/ui`**: contiene todos los componentes de la interfaz de usuario para su aplicación, como tarjetas, tablas y formularios. Para ahorrar tiempo, hemos prediseñado estos componentes para usted.
- **/app/pages**: Pages Router tiene un enrutador basado en un sistema de archivos construido sobre conceptos de páginas. Cuando se agrega un archivo a este directorio, está disponible automáticamente como ruta.
- **`/public`**: Contiene todos los activos estáticos de su aplicación, como imágenes, videos, etc.
- **`/script/`**: Contiene un script de inicialización que utilizará para completar su base de datos en un capítulo posterior.

- **Archivos de configuración** : también notará archivos de configuración, como :
	* **next.config.js**
	* **pacckage.json**
	* **instrumentation.ts**
	* **middleware.ts**
	* **.env**
	* **eslintrc.json**
	* **.gitignore**
	* **tsconfig.json**
	



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