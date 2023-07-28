# Accesibilidad en HTML

## Modelo de objetos de accesibilidad (AOM)

A medida que el navegador analiza el contenido recibido, crea el modelo de objetos de documento (DOM) y el modelo de objetos CSS (CSSOM). A continuación, también construye un árbol de accesibilidad. Los dispositivos de asistencia, como los lectores de pantalla, utilizan el AOM para analizar e interpretar el contenido. El DOM es un árbol de todos los nodos del documento. El AOM es como una versión semántica del DOM.

## Atributo role
El atributo role describe el rol que tiene un elemento en el contexto del documento. Es un atributo global, lo que significa que es valido en todos los elementos. Los nombres de los roles de los elementos son importantes en la construcción del AOM. La semántica de un elemento, o 'rol', es importante para las tecnologías de asistencia y, en algunos casos, para los motores de búsqueda. Los usuarios de tecnología de asistencia confían en la semántica para navegar y comprender el significado del contenido. La función del elemento permite al usuario acceder rápidamente al contenido que busca y, posiblemente, lo que es más importante, la función informa al usuario del lector de pantalla cómo interactuar con un elemento interactivo una vez que tiene el foco.

Los elementos interactivos, como botones, enlaces, rangos y casillas de verificación, todos tienen roles implícitos, todos se agregan automáticamente a la secuencia de pestañas del teclado y todos tienen soporte de acción de usuario esperado predeterminado. Con el `role`atributo, puede otorgar un rol a cualquier elemento, incluido un rol diferente al que implica la etiqueta. Por ejemplo, `<button>`tiene el rol implícito de `button`. Por ende con role podemos agregarle por ejemplo a un div el role "heading" para indicar semanticamente que es un header.

https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA


[[HTML semantico]]