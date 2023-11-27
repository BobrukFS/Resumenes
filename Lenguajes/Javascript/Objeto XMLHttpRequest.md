
# Objeto XMLHttpRequest

Es una API que nos proporciona un objeto nativo del navegador que proporciona una forma fácil de obtener información de una URL sin tener que recargar la página completa. Puede ser usado para recibir cualquier tipo de informacion. 

Para utilizarlo lo primero que hacemos es crear una instancia de **XMLHttpRequest**.

![[Pasted image 20230122180845.png]]
## Propiedades del objeto XMLHttpRequest

#### Propiedad response y responseText

La propiedad `response` es una propiedad que contiene la respuesta de la solicitud HTTP tal como está, sin procesar. Puede contener diferentes tipos de datos, como texto, JSON, XML, ArrayBuffer, Blob, entre otros, según el tipo de contenido que se haya devuelto por el servidor y cómo se haya especificado en los encabezados de la respuesta.

Por otro lado, la propiedad `responseText` es específica para obtener la respuesta de la solicitud HTTP como una cadena de texto. Si la respuesta es de tipo texto, `responseText` contendrá el contenido de la respuesta como una cadena de texto. Sin embargo, si la respuesta es de otro tipo (como JSON o XML), `responseText` mostrará la representación de la respuesta en formato de texto plano, sin procesar.

La propiedad responseText es una propiedad de solo lectura que lo que va hacer es devolver la respuesta de la solicitud HTTP como una cadena de texto.  La propiedad `responseText` es útil cuando se espera que la respuesta del servidor sea texto plano, como en el caso de obtener contenido HTML, texto sin formato u otros formatos de texto. Sin embargo, si se espera que la respuesta sea en un formato estructurado como JSON, es recomendable utilizar la propiedad `response` junto con `JSON.parse()` para obtener un objeto JavaScript a partir de la respuesta.

En la propiedad responseText de XMLHttpRequest tenemos el resultado, es decir la informacion.  

Es importante destacar que para obtener un objeto JavaScript a partir de una respuesta JSON, por ejemplo, es necesario utilizar `JSON.parse()` en la propiedad `responseText`. De esta manera, se puede convertir la cadena de texto JSON en un objeto JavaScript para trabajar con él de forma más conveniente.
#### ResponseType

La propiedad responseType nos permite asignar el formato de la respuesta que queremos recibir o enviar.

![[Pasted image 20230526215644.png]]
#### Status

La propiedad **status** es el codigo de estado HTTP.

1. Respuestas informativas (`100`–`199`),
2. Respuestas satisfactorias (`200`–`299`),
3. Redirecciones (`300`–`399`),
4. Errores de los clientes (`400`–`499`),
5. y errores de los servidores (`500`–`599`).
#### ReadyState

Si la propiedad readyState es 3 o 4, y el status es 200 o 201 la informacion se puede utilizar.

**readyState** tiene 4 estados, el primero significa que la solicitud se crea correctamente, el segundo dice que la solicitud se envio correctamente, el tercero dice que se esta procesando la informacion, el cuarto dice que nos dio una respuesta y que el resultado se puede utilizar. Hay un evento que detecta el cambio de ReadyState, este metodo es “**readystatechange**”.

![[Pasted image 20231016220044.png]]

Sabiendo que para poder manejar la informacion que obtenemos al realizar la peticion necesitamos un status de 200 y que el readyState sea 3 o 4 podemos realizar una validacion.

![[Pasted image 20230122180924.png]]

Pero esta forma ya no se utiliza ya que podemos utilizar el evento “load”. El evento load se dispara cuando un recurso y sus recursos dependientes han terminado de cargar.

![[Pasted image 20230122180931.png]]

Los estados podemos seguirlos mediante el evento **readystatechange**.
#### timeout

La propiedad timeout nos permite especificar un tiempo limite. Si la solicitud no es realizada con exito dentro del tiempo dado, se cancela y el evento timeout se activa.

```js
xhr.timeout = 0; //No esperamos ningun timeout
xhr.timeout = 1; //Si en 1ms no se completa el pedido, se cancela todo el pedido.
```

Podemos utilizar el evento **timeout** para avisar que ha excedido el tiempo el pedido.
#### ResponseURL

Esta propiedad contiene la URL a donde realizamos la peticion.
## Metodos objeto XMLHttpRequest

* **open()** : Para inicializa una peticion utilizamos el metodo **open()**. Este método es para ser usado desde código JavaScript. Tiene tres parametros, el tipo de metodo de peticion (en mayusculas), la url y por ultimo un parametro opcional que es async, como predeterminado viene true, es decir la XMLHttpRequest se procesa de forma asincrona, de lo contrario el proceso se realiza de forma sincrona.

![[Pasted image 20230122180911.png]]

* **send() :** Envía la solicitud. Si la solicitud es asíncrona (que es el valor predeterminado), este método regresa tan pronto como se envía la solicitud. Si la solicitud es síncrona, este método no regresa hasta que llega la respuesta. Podemos tener un parametro adicional **body** que contiene el cuerpo de la solicitud, como por ejemplo al utilizar POST, que es lo que queremos enviar. Si solo estamos utilizando lectura no va ningun parametro.

* **abort()** : Nos permite terminar la solicitud en cualquier momento. Evitando descargar la informacion.

* **setRequestHeader(name, value)**: Nos permite asignar la cabecera de la solicitud con los valores name y value provistos.

```js
xhr.setRequestHeader('Content-type', 'application/json; charset=utf-8');
```

* **getResponseHeader(name)**: Obtiene la cabecera de la respuesta con el name dado.

```js
xhr.getResponseHeader('Content-Type')
```

* **getAllResponseHeaders()**: Devuelve todas las cabeceras de la respuesta. Las cabeceras se devuelven como una sola linea.
## Interfaz ProgressEvent

La interfaz ProgressEvent representa eventos que miden el progreso de un proceso subyacente, como una solicitud HTTP.

* **load**: Cuando la solicitud esta completa, y la respuesta se descargo por completo.
* **error**: Cuando la solicitud no pudo ser realizada satisfactoriamente, por ejemplo red caida o una URL invalida.
* **progress**: Se dispara periodicamente mientras la respuesta esta siendo descargada, reporta cuando se ha descargado

![[Pasted image 20230526215515.png]]
## Formularios POST

Podemos utilizar el objeto FormData nativo. La interfaz FormData proporciona una forma de construir fácilmente un conjunto de pares clave/valor que representan campos de formulario y sus valores, que luego pueden enviarse fácilmente utilizando el método XMLHttpRequest.send(). Utiliza el mismo formato que un formulario usaría si el tipo de codificación se configura como "multipart/form-data"

```js
let formData = new FormData([form]); // crea un objeto, opcionalmente se completa con un <form> formData.append(name, value); // añade un campo
```

![[Pasted image 20230527004905.png]]

El método **append()** de la interfaz FormData agrega un nuevo valor a una clave existente dentro de un objeto FormData, o agrega la clave si aún no existe. La diferencia entre FormData.set y append() es que si la clave especificada ya existe, FormData.set sobrescribirá todos los valores existentes con el nuevo, mientras que append() agrega el nuevo valor al final del conjunto existente de valores.

El formulario fue enviado con codificacion multipart/form-data pero podemos enviarlo como JSON.
![[Pasted image 20230527004941.png]]
## Objeto upload

El objeto upload sirve para rastrear los eventos de subida. Este objeto tiene diversas propiedades:

* loadstart : carga iniciada
* progress: se dispara periodicamente durante la subida
* abort: carga abortada
* error: error no HTTP
* load : carga finalizada con exito
* timeout: carga caducada (si la propiedad timeout esta asignada)
* loadend : carga finalizada con exito o error.

![[Pasted image 20230528031257.png]]
## ActiveXObject

AJAX no es soportado por todo los navegadores, por lo que tenemos que trabajar por un objeto parecido que es para internet explorer, y para ello tenemos que verificar que internet explorer este utilizado por el cliente.

Entonces para ello utilizamos:

![[Pasted image 20230122180938.png]]
En caso de que no exista XMLHTTPrequest, creamos ActiveXObject que es el mismo pero para microsoft explorer.






