# Peticiones HTTPS

**HTTPS (HyperTextTransferProtocolSecurity)** es un protocolo de la **capa de aplicación** para la transmision de documentos. Este protocolo fue diseñado para la comunicación entre los navegadores y servidores web que no guarda informacion sobre conexiones anteriores (Protocolo sin estado). Ademas, HTTPS define un conjunto de **metodos de peticion** (get, post, etc) para indicar la accion que desea realizar para un recurso determinado. 

Las diferencias con HTTP y HTTPS es que HTTP trabaja con el puerto 80 mientras que HTTPS trabaja con el puerto 443.

El protocolo esta orientado a transacciones y sigue el esquema de peticion/respuesta entre un cliente y un servidor. El cliente realiza una **peticion** enviando un mensaje con cierto formato al servidor y el servidor le envia un mensaje de **respuesta**. Por defecto, el cliente inicia la comunicacion y el servidor responde. Esto se puede invertir gracias a los **websockets**.

Una **solicitud HTTP** es un mensaje que le dice al servidor cual es el recurso al que el navegador quiere acceder y lo que quiere hacer con el mismo (descargar el documento, procesar informacion,etc.). El mensaje esta compuesto por la URL del recurso, los datos asociados con la solicitud, como la fecha y el idioma, y un cuerpo con informacion adicional. Los pares nombre/valor producidos por un formulario se envian al servidor dentro de estas solicitudes HTTP.  Las solicitudes HTTP son en texto plano lo que hace mas legible y facil de depurar.

**Estos tienen la siguiente estructura:**

-Primero, hay una linea inicial en donde se diferencian dependiendo de si son **peticiones o respuestas**. **Para las solicitudes** la linea comienza con un accion requerida por el servidor, a esto se le denomina **metodo de peticion** (GET, POST, etc.) seguido de la url del recurso y la version http que soporte al cliente, a esto se le suele llamar **request-line**. Para las respuestas, la linea comienza con la version de HTTP seguido por un **codigo de respuesta** y una frase asociada a dicho retorno.

-Tambien los mensajes tienen una **cabecera o header** que son metadatos con informacion diversa y el cuerpo de mensaje que es opcional. Tipicamente este cuerpo tiene los datos que se intercambian entre el cliente y el servidor. Los HEADERS mas conocidos son **content-length** que va a determinar el tamaño del recurso que fuimos a solicitar en bits y **content-type** va a determinar que tipo de recurso estamos pidiendo o enviando (image/jpg, text/html, etc).

![[Pasted image 20230122180707.png]]

Una URL se ve asi

![[Pasted image 20230122180717.png]]

## Tipos de errores

![[Pasted image 20230122180711.png]]
## Metodos de solicitud (HTTP Verbs)

1. **GET:** Utilizado para recuperar información o recursos del servidor. La solicitud GET no debe tener efectos secundarios en el servidor y se considera idempotente.
    
2. **POST:** Utilizado para enviar datos al servidor para que sean procesados. Se utiliza para enviar información y crear nuevos recursos en el servidor. No se considera idempotente, ya que cada solicitud POST puede tener un efecto diferente.
    
3. **PUT:** Utilizado para actualizar o reemplazar completamente un recurso en el servidor. La solicitud PUT envía los datos actualizados completos del recurso. También puede ser utilizado para crear un recurso si la URL específica no existe previamente.
    
4. **PATCH:** Similar a PUT, pero utilizado para actualizar parcialmente un recurso en el servidor. En lugar de enviar los datos completos del recurso, la solicitud PATCH envía solo los cambios o actualizaciones que se especifican en el body de la peticion.
    
5. **DELETE:** Utilizado para eliminar un recurso específico en el servidor.
    
6. **OPTIONS:** Utilizado para obtener información sobre las opciones o capacidades de comunicación disponibles en el servidor para un recurso en particular.

### Metodo GET y POST

#### GET

El metodo **GET** se usa para enviar una cantidad limitada de informacion de forma publica (Los datos pares nombre/valor son incluidos en la URL, la cual no puede contener mas de 255 caracteres, esta url se llama **Query String**). Si los datos se pueden compartir, puede usar el método GET . De esta manera, los datos se agregarán a su historial de navegación tal como se incluyen en la URL. Si el metodo se ha declarado como GET, los pares nombre/valor se agregan al final de la URL

El formulario de tipo GET se utiliza para todo lo que son formularios de busqueda, no se envia informacion sensible. No es recomendable mandar informacion sensible. El metodo get se debe utilizar en los formularios que no modifican la informacion.

```HTML

<!-- Ejemplo formulario de busqueda -->
    
     <form action="https://www.google.com/search" method="GET" target="_blank">

        <label for="">Ingrese la palabra a buscar:</label>

        <input type="text" name="q">

        <button type="submit">Busqueda</button>

    </form>

//Por ejemplo si busco Manzanas, la url en este caso seria https://www.google.com/search?q=manzana


```


Cuando la información se envía con el método GET, los pares nombre/valor se agregan al final de la URL separados por el carácter =, y el primer par es precedido por el carácter ?. Si existe más de un par de valores, los restantes se agregan a la URL separados por el carácter &, como en `www.ejemplo.com/procesar.php?val1=10&val2=20`.

#### POST

El **metodo post** envia los datos para que sean procesados/modificados por el recurso identificado. Los datos enviados se incluiran en el body del HTTP Request,de la peticion y no en la url. Esto puede resultar en la creacion de un nuevo recurso o de las actualizaciones de recursos existentes. El método POST generalmente se utiliza para enviar datos al servidor y no para acceder directamente a archivos. Por otro lado, el metodo POST se utiliza para enviar una cantidad ilimitada de informacion de forma privada y segura (los datos no son visibles al usuario y pueden tener la longitud que necesitemos). Para formularios que procesan datos confidenciales, es recomendable usar el metodo POST. Los datos están encriptados (si usa HTTPS) y solo puede acceder a ellos el script de back-end que procesa la solicitud. Los datos no son visibles en la URL. Un ejemplo común de un formulario que utiliza POST es un formulario de inicio de sesión, envio de estadisticas, etc.

Para practicar formularios post : https://formspree.io/

**Data** : En formsspree.io no poner name= "password" porque nos banean.

![[Pasted image 20230122181110.png]]
[[Cors]]