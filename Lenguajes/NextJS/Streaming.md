# Streaming

La transmisión por secuencias es una técnica de transferencia de datos que le permite dividir una ruta en "fragmentos" más pequeños y transmitirlos progresivamente desde el servidor al cliente a medida que estén listos.

![[Pasted image 20231109202649.png]]

Al transmitir, puede evitar que las solicitudes de datos lentas bloqueen toda su página. Esto permite al usuario ver e interactuar con partes de la página sin esperar a que se carguen todos los datos antes de poder mostrarle cualquier interfaz de usuario.

La obtención y representación de datos se inician en paralelo, por lo que el usuario puede ver la interfaz de usuario cuando esté lista. Esto es diferente del enfoque tradicional en cascada, donde la obtención y el procesamiento de datos se inician secuencialmente, bloqueando el procesamiento de la interfaz de usuario hasta que todos los datos estén listos.

![[Pasted image 20231109202741.png]]
Hay dos formas de implementar la transmisión en Next.js:

1. A nivel de página, con el `loading.tsx`archivo.
2. Para componentes específicos, con `<Suspense>`.

## Loading

1. `loading.tsx`es un archivo especial Next.js creado sobre Suspense, que le permite crear una interfaz de usuario de carga para mostrarla como reemplazo mientras se carga el contenido de la página.
2. Si nosotros tenemos componentes estaticos estos se mostraran inmediatamente, por lo que el usuario puede interactuar mientras se carga el contenido dinamico.
3. El usuario no tiene que esperar a que la página termine de cargarse antes de navegar (esto se llama navegación interrumpible).

Podemos agregar "esquelos de carga" para mejorar la experiencia del usuario. Muchos sitios web los utilizan como marcador de posición (o respaldo) para indicar a los usuarios que el contenido se está cargando. Cualquier interfaz de usuario que incruste `loading.tsx`se integrará como parte del archivo estático y se enviará primero. Luego, el resto del contenido dinámico se transmitirá desde el servidor al cliente.

Al momento de cargar se aplicara tambien a las paginas subyacentes debido a que esta a un nivel superior en el sistema de archivos, por lo que para evitarlo podemos crear una nueva carpeta llamada por ejemplo /(overview) y movelos los archivos loading.tsx y page.tsx dentro de la carpeta, por lo que ahora el loading.tsx solo se aplica a la pagina del mismo nivel jerarquico y no a la subyacentes. A esto se le llama **grupos de Rutas**.

Los grupos de rutas permiten organizar archivos en grupos lógicos sin afectar la estructura de la ruta URL. Cuando crea una nueva carpeta usando paréntesis (), el nombre no se incluirá en la ruta URL. Así /dashboard/(overview)/page.tsx se convierte /dashboard y no en /dashboard/overview.
## Suspense

Suspense le permite diferir la renderización de partes de su aplicación hasta que se cumpla alguna condición (por ejemplo, que se carguen los datos). Puede envolver sus componentes dinámicos en Suspense. Luego, pásele un componente alternativo para mostrarlo mientras se carga el componente dinámico. En el atributo fallback se pasa el componente esqueleto de carga, entonces mientras no cargue se muestra dicho componente, y si carga se renderiza lo de dentro del suspense.  

Este metodo esta bueno porque podemos mover la recuperación de datos a los componentes que los necesitan, puediando crear asi límites de Suspense más granulares. Esto le permite transmitir componentes específicos y evitar que la interfaz de usuario se bloquee.