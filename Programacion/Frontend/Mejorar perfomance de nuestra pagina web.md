# Mejorar perfomance de nuestra pagina web

**Con lazy loading**

A las imágenes podemos agregarle un atributo **loading=”lazy”.** Esto es para que se vayan descargando las imágenes a medida que están en nuestra ventana. Sin el lazy se descargan todas las imágenes al abrir la pagina. Para ver como funciona podemos ver en la consola del desarrollador al tocar network.

**Con preload**

Para esto hay que agregarle un **rel=”preload”** .Descargara primero los elementos que creemos necesarios. Si el link es de un lugar externo hay que agregarle **crossorigin=”crossorigin”.**

**Con prefetch**

Con **rel="prefetch"** carga la pagina antes. Sirve para cargar la pagina que pensamos que el usuario visitara. Esto se puede ver con Google analitycs podemos saber estadísticas del usuario en la pagina.

**Con imágenes webp**

Reduce el tamaño de las imágenes. Esto se hace con `<picture> </picture>` donde ponemos un`<source srcset=”url.webp” type= “image/webp”>`

Se puede utilizar **modernirz** que es una librería javascript. Tocamos ADD YOUR DETECTS y buscamos webp, lo añadimos y le damos click a BUILD y lo copiamos -> creamos un archivo modernizar.js y pegamos el contenido copiado. Para vincular HTML con javascript ponemos esto:

![[Pasted image 20221214121529.png]]

Entonces en css ponemos:

![[Pasted image 20221214121539.png]]

Esto quiere decir que si el navegador soporta webp se aplicara un background-image en el header en formato webp. Si el navegador no soporta, será jpg.

**Optimizando imagenes**

Podemos utilizar GIMP

**Dato:** Se puete auditiar el sitio web con **lighthouse** que es una extensión. Hay que subir a netlify nuestra pagina y hacemos auditorias con lighthouse. Esto nos da un reporte de lo que podemos mejorar,etc.

https://developer.mozilla.org/en-US/docs/Web/Performance
https://web.dev/rendering-on-the-web/
https://web.dev/rendering-performance/