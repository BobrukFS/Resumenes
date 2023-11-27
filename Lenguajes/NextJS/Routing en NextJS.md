# Routing en NextJS
Next.js utiliza enrutamiento del sistema de archivos donde se usan **carpetas para crear rutas anidadas.** Cada carpeta representa un **segmento de ruta** que se asigna a un **segmento de URL** .

![[Pasted image 20231109161026.png]]

Se puede crear UI independientes para cada ruta utilizando archivos `layout.tsx`y `page.tsx`. El archivo page es un archivo Next.JS especial que exporta un componente de React y es necesario para que la ruta sea accesible. El archivo layout lo que hace es crear una interfaz de usuario que se comparte entre varias paginas hijas. El `<Layout />`componente recibe un `children`apoyo. Este hijo puede ser una página u otro diseño. En su caso, las páginas internas `/dashboard`se anidarán automáticamente dentro de un `<Layout />`.

Un beneficio de usar diseños en Next.js es que durante la navegación, solo se actualizan los componentes de la página, mientras que el diseño no se vuelve a representar. Esto se llama **renderizado parcial**. La representación parcial significa que solo los segmentos de ruta que cambian durante la navegación se vuelven a representar en el cliente y se conservan los segmentos compartidos. Por ejemplo, al navegar entre dos rutas hermanas `/dashboard/settings`y `/dashboard/analytics`, las páginas `settings`y `analytics`se representarán y `dashboard`se conservará el layout compartido.

![[Pasted image 20231109162428.png]]Sin una representación parcial, cada navegación haría que la página completa se volviera a representar en el servidor. Representar solo el segmento que cambia reduce la cantidad de datos transferidos y el tiempo de ejecución, lo que mejora el rendimiento.

## Componente Link

En Next.js, puede utilizar el `<Link />`Componente para vincular páginas en su aplicación. `<Link>`le permite realizar navegación del lado del cliente con JavaScript.

Un patrón de interfaz de usuario común es mostrar un enlace activo para indicar al usuario en qué página se encuentra actualmente. Para hacer esto, necesita obtener la ruta actual del usuario desde la URL. Next.js proporciona un gancho llamado [`usePathname()`](https://nextjs.org/docs/app/api-reference/functions/use-pathname)que puede usar para verificar la ruta e implementar este patrón combinandolo con la biblioteca clsx.

[[Route Handlers]]