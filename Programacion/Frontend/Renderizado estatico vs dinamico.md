# Renderizado estatico vs dinamico

## Estatico
Con la representación estática, la obtención y representación de datos se realiza en el servidor en el momento de la compilación (cuando se implementa) o durante la revalidación. Luego, el resultado se puede distribuir y almacenar en caché.

![[Pasted image 20231109220417.png]]
Cada vez que un usuario visita su aplicación, se muestra el resultado almacenado en caché o en un CDN. Hay un par de beneficios del renderizado estático:

- **Sitios web más rápidos** : el contenido prerenderizado se puede almacenar en caché. Esto garantiza que los usuarios de todo el mundo puedan acceder al contenido de su sitio web de forma más rápida y fiable.
- **Carga reducida del servidor** : debido a que el contenido se almacena en caché, su servidor no tiene que generar contenido dinámicamente para cada solicitud de usuario.
- **SEO** : el contenido prerenderizado es más fácil de indexar para los rastreadores de los motores de búsqueda, ya que el contenido ya está disponible cuando se carga la página. Esto puede conducir a una mejor clasificación en los motores de búsqueda.

La representación estática es útil para la interfaz de usuario **sin datos** o **con datos compartidos entre usuarios** , como una publicación de blog estática o una página de producto. Puede que no sea una buena opción para un panel que tenga datos que se actualicen periódicamente.

## Dinamico

Con la representación dinámica, el contenido se presenta en el servidor para cada usuario en el **momento de la solicitud** (cuando el usuario visita la página). Hay un par de beneficios del renderizado dinámico:

- **Datos en tiempo real** : la representación dinámica permite que su aplicación muestre datos en tiempo real o actualizados con frecuencia. Esto es ideal para aplicaciones donde los datos cambian con frecuencia.
- **Contenido específico del usuario** : es más fácil ofrecer contenido específico del usuario, como paneles personalizados o perfiles de usuario, a través de la representación dinámica, ya que los datos se actualizan en función de la interacción del usuario.
- **Solicitar información sobre el tiempo** : la representación dinámica le permite acceder a información que solo se puede conocer en el momento de la solicitud, como las cookies o los parámetros de búsqueda de URL.