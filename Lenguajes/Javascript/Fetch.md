# Fecth

Fetch es una forma de trabajar con el XMLHttpRequest. Al igual que Ajax te permite enviar informacion al servidor u obtener informacion de un servidor en forma asincronica.  **Cuando trabajamos con fetch siempre nos devuelve una respuesta que es una promesa encapsulada, que es el objeto Response**.

La sintaxis básica es la siguiente:

![[Pasted image 20230122181251.png]]
Si no especificamos ningún options, se ejecutará una simple petición GET, la cual descargará el contenido de lo especificado en el url. Options suele ser util para configurar las api key y poder realizar solicitudes a cierta api que lo requiera y no tenga un string query, tambien sirve para realizar peticiones post.

El navegador lanzará la petición de inmediato y devolverá una promesa (promise) que luego será utilizada por el código invocado para obtener el resultado.

Primero, la promesa devuelta por fetch, resuelve la respuesta con un objeto de la clase incorporada Response tan pronto como el servidor responde con los encabezados de la petición. Podemos chequear el status HTTP para poder ver si nuestra petición ha sido exitosa o no, y chequear los encabezados, pero aún no disponemos del cuerpo de la misma.

La promesa se rechaza si `fetch` no se pudo realizar la solicitud HTTP, por ejemplo, problemas de red, o si no existe dicho sitio. Los estados HTTP anormales, como 404 o 500, no provocan un error. Podemos ver el estado HTTP en las propiedades de respuesta: **status** y **ok**(devuelve true si el codigo de estado http es 200-299).

En segundo lugar, para obtener el cuerpo de la respuesta, necesitamos utilizar una llamada a un método adicional. El objeto Response provee multiples metodos basados en promesas para acceder al cuerpo de la respuesta en distintos formatos:

* **text() :** lee y devuelve la respuesta en formato texto.

* **json():** convierte la respuesta como un JSON.

* **formData() :** devuelve la respuesta como un objeto FormData.

* **blob():** devuelve la respuesta como Blob (datos binarios tipados). El tipo de datos de gran objeto binario ( BLOB ) es un tipo de datos de MySQL que puede almacenar datos binarios como los de archivos de imagen, multimedia y PDF.

* **arrayBuffer() :** devuelve la respuesta como un objeto ArrayBuffer.

**Dato**: Solo podemos elegir un metodo de lectura del cuerpo.

Ejemplo:

![[Pasted image 20230122181300.png]]
Otro ejemplo:

![[Pasted image 20230122181305.png]]
## Realizar peticiones POST con fetch

Para ello tenemos que pasarle como segundo parametro, un objeto con el metodo (method), el cuerpo de la respuesta o peticion y los headers. Tener en cuenta, si la respuesta del body es una cadena de texto, entonces el encabezado Content-Type será especificado como text/plain;charset=UTF-8 por defecto.

Pero, cómo vamos a enviar un objeto JSON, en su lugar utilizaremos la opción headers especificada a application/json, que es la opción correcta Content-Type para información en formato JSON.

Ejemplo:

![[Pasted image 20230122181323.png]]
## FETCH con await y async

Asi fetch sea una funcion asincronica, se suele utilizar con await y asinc para gestionar las respuestas de manera mas legible y efectiva. Usar await con fetch te permite esperar la respuesta antes de continuar con la ejecucion del codigo, lo que facilita el manejo de la respuesta y el manejo de errores de una manera mas estructura y sincrona.

![[Pasted image 20230122181329.png]]

## AbortController

`AbortController` es una API en JavaScript que se utiliza para cancelar solicitudes de red, como las realizadas con `fetch`. Esta API proporciona un mecanismo para abortar una solicitud antes de que se complete, lo que puede ser útil en situaciones donde deseas detener una solicitud en curso debido a cambios en el flujo de tu aplicación o cuando el usuario decide cancelar la solicitud.
