# Routing en NextJS
Next.js utiliza enrutamiento del sistema de archivos donde se usan **carpetas para crear rutas anidadas.** Cada carpeta representa un **segmento de ruta** que se asigna a un **segmento de URL** .

![[Pasted image 20231109161026.png]]

Se puede crear UI independientes para cada ruta utilizando archivos `layout.tsx`y `page.tsx`. El archivo **page** es un archivo Next.JS especial que exporta un componente de React y es necesario para que la ruta sea accesible. El archivo layout lo que hace es crear una interfaz de usuario que se comparte entre varias paginas hijas. El componente `<Layout />` recibe un prop `children`. Este children puede ser una página u otro diseño. En su caso, las páginas internas `/dashboard` se anidarán automáticamente dentro de un `<Layout />`.

Un beneficio de usar diseños en Next.js es que durante la navegación, solo se actualizan los componentes de la página, mientras que el diseño(layout) no se vuelve a representar. Esto se llama **renderizado parcial**. La representación parcial significa que solo los segmentos de ruta que cambian durante la navegación se vuelven a representar en el cliente y se conservan los segmentos compartidos. Por ejemplo, al navegar entre dos rutas hermanas `/dashboard/settings`y `/dashboard/analytics`, las páginas `settings`y `analytics`se representarán y `dashboard` conservará el layout compartido.

![[Pasted image 20231109162428.png]]Sin una representación parcial, cada navegación haría que la página completa se volviera a representar en el servidor. Representar solo el segmento que cambia reduce la cantidad de datos transferidos y el tiempo de ejecución, lo que mejora el rendimiento.

### Page
Una **página** es una interfaz de usuario exclusiva de una ruta.

```tsx
export default function Page({
  params,
  searchParams,
}: {
  params: { slug: string }
  searchParams: { [key: string]: string | string[] | undefined }
}) {
  return <h1>My Page</h1>
}
```

### Layout
Un **diseño** es una interfaz de usuario que se comparte entre rutas.

```tsx
export default function DashboardLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return <section>{children}</section>
}
```

El layout en el directorio raiz se utiliza para definir etiquetas html y body y otras IU compartidas globalmente

```tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}
```

#### Metadata

Podemos exportar una constante que es metadata, este es un json, que va a tener por ejemplo title: "titulo de la pagina". Nextjs automaticamente  pone un head con la metadata automaticamente. Podemos hacer por ejemplo tambien que en otro layout de otro componente cambie la metadata, por ejemplo el title. El metadata solo funciona en paginas que son del lado del servidor.
## Componente Link

En Next.js, puede utilizar el `<Link />`Componente para vincular páginas en su aplicación. `<Link>` le permite realizar navegación del lado del cliente con JavaScript.

Un patrón de interfaz de usuario común es mostrar un enlace activo para indicar al usuario en qué página se encuentra actualmente. Para hacer esto, necesita obtener la ruta actual del usuario desde la URL. Next.js proporciona un gancho llamado [`usePathname()`](https://nextjs.org/docs/app/api-reference/functions/use-pathname)que puede usar para verificar la ruta e implementar este patrón combinandolo con la biblioteca clsx.

Si visitamos una pagina que no existe, vamos a ver un error o un error personalizado mediante la creacion de un archivo **not-found.tsx**. 

```tsx
import Link from 'next/link'
 
export default function NotFound() {
  return (
    <div>
      <h2>Not Found</h2>
      <p>Could not find requested resource</p>
      <Link href="/">Return Home</Link>
    </div>
  )
}
```
## Loading





















[[Route Handlers]]
[[Routing Conventions]]