# Single Page Application (SPA)

Una SPA o Single Page Application es una aplicación web que cabe en una sola página y tiene el propósito de dar una experiencia más fluida a los usuarios, como si fuera una aplicación de escritorio.

En una SPA todos los códigos de HTML, JavaScript y CSS se cargan una sola vez. Los recursos necesarios se cargan en forma dinámica cuando lo requiera la página, normalmente como respuesta a las acciones del usuario.

## Componentes de una SPA

* **Pagina actual**: Es el DOM que se muestra actualmente en la pantalla.
* **Aplicacion principal**: Es un **mediator** entra la pagina actual y el router. Obtiene la ruta actual y renderiza la pagina correspondiente en el HTML. Escucha el evento de cambio de URL en el historial, obtiene los datos de la URL actual y renderiza en el  HTML la pagina correspondiente a la URL actual.
* **Router**: Es una estructura de datos que contiene las paginas que se deben renderizar en funcion de la ruta actual.

## Ventajas y desventajas

**Ventajas de SPA**

- **Mejores tiempos de carga iniciales:** SPA solo requiere que el navegador cargue una sola página web. Esto puede provocar tiempos de carga iniciales más rápidos, especialmente en conexiones lentas.
- **Mayor rendimiento:** SPA puede ofrecer un rendimiento superior a MPA, especialmente en aplicaciones web con mucho contenido dinámico.
- **Mejor experiencia de usuario:** SPA puede ofrecer una mejor experiencia de usuario al permitir a los usuarios interactuar con la aplicación sin tener que esperar a que se carguen nuevas páginas web.

**Desventajas de SPA**

- **Más difícil de desarrollar:** SPA es una arquitectura web más compleja que MPA.
- **Menor SEO:** SPA es más difícil de indexar por los motores de búsqueda que MPA.
- **Menor compatibilidad:** SPA puede no ser compatible con todas las versiones de los navegadores.

