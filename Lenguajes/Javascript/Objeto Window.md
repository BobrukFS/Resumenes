# Objeto Window
Cada vez que abrimos el navegador o iniciamos una nueva pestaña se crea un objeto global llamado **Window** para referenciar la ventana del navegador y proveer algunas propiedades y metodos esenciales. El objeto Window se almacena en una propiedad del objeto global de javascript llamada **window**. A traves de esta propiedad podemos conectarnos con el navegador y el documento desde nuestro codigo. Este objeto es el objeto de mayor jerarquia en javascript. Window hereda las propiedades de **EventTarget**.

El objeto Window controla aspectos de la ventana, su contenido, y los datos asociados a la misma, como la ubicación del documento actual, el tamaño, el desplazamiento, etc.

El objeto Window a su vez incluye otros objetos con los que provee informacion adicional relacionada con la ventana y el documento. Algunos de estos son:

* **location :** Esta propiedad contiene un objeto **Location** con propiedades y metodos con informacion acerca del origen del documento. Algunas propiedades y metodos del objeto location: Tenemos la propiedad **href** que devuelve la url de la pagina actual. Tenemos **hostname** que devuelve el nombre de dominio del servidor web. Tenemos **pathname** que devuelve la ruta y el nombre de archivo de la pagina actual. Tenemos **protocol** que devuelve el protocolo web utilizado (http: o https :) y por ultimo tenemos **assign(url)** que carga un nuevo documento. Ejemplo window.location.href.

* **history :** Esta propiedad contiene un objeto **History** con propiedades y metodos para manipular el historial de navegacion.

* **navigator :** Esta propiedad contiene un objeto **Navigator** con propiedades y metodos con informacion acerca de la aplicación y el dispositivo. Una de las propiedades de este objeto es la **geolocation**.

* **document :** Esta propiedad contiene un objeto **Document**, que provee acceso a los objetos que representan los elementos HTML en el documento. Este objeto tiene sus propios metodos y propiedades.

* **screen :** Este propiedad contiene un objeto screen que tiene ciertas propiedades de la pantalla.

Ademas de estos objetos, el objeto window tambien ofrece sus propias propiedades y metodos. Los que mas se usan son:

* **innerWidth :** Esta propiedad devuelve el ancho de la ventana en pixeles.

* **innerHeight :** Esta propiedad devuelve la altura de la ventana en pixeles.

* **screenLeft :** Esta propiedad devuelve la distancia horizontal entre el borde izquierdo del navegador y el borde izquierdo de la pantalla del monitor. Esta es una propiedad de lectura.

* **devicePixelRatio :** Devuelve la relacion de tamaño (vertical) de un pixel fisico en el dispositivo de visualizacion real respecto de un dispositivo de tamaño de pixel independiente.

* **screenTop :** Esta propiedad devuelve la distancia vertical entre el borde superior del navegador y el borde superior de la pantalla del monitor. Esta es una propiedad de lectura.

* **scrollX :** Esta propiedad devuelve el numero de pixeles en los que el documento se ha desplazado horizontalmente.

* **scrollY :** Esta propiedad devuelve el numero de pixeles en los que el documento se ha desplazado verticalmente.

* **scroll(ejex, ejey) :** Este metodo desplaza la ventana a un lugar particular en el documento. Esto se desplaza un valor absoluto. Para desplazamiento relativos tenemos **scrollBy(), scrollByLines(), scrollByPages().**

* **Alert(valor) :** Este metodo muestra una ventana emergente en la pantalla que muestra el valor entre parentesis.

* **Confirm(mensaje) :** Este metodo es similar a alert(), pero ofrece dos botones, Aceptar y Cancelar, para que el usuario elija que hacer. El metodo devuelve true o false, según a la respuesta del usuario.

* **Prompt(mensaje, default) :** Este metodo muestra una ventana emergente con un campo de entrada para permitir al usuario introducir un valor. El metodo devuelve el valor que inserte el usuario.El parametro Default es el valor que aparecera preescrito.

* **setTimeout(funcion, milisegundos) :** Este metodo ejecuta la funcion especificada en el primer atributo cuando haya pasado el tiempo especificado por el segundo atributo. El objeto window tambien ofrece el metodo **clearTimeout()** para cancelar este proceso.

* **setInterval(funcion, milisegundos) :** Este metodo es similar a setTimeout(), pero llama a la funcion constantemente. El objeto window tambien ofrece el metodo **clearInterval()** para cancelar el proceso.

* **open(URL, ventana, parametros) :** Este metodo abre un documento en una nueva ventana. El atributo **URL** es la URL del documento que queremos abrir, el atributo **ventana** es el nombre de la ventana donde queremos mostrar el documento (si el nombre no se especifica o la ventana no existe, el documento se abre en una nueva ventana), y el atributo **parametros** es una lista de parametros de configuracion separados por comas que configuran las caracteristicas de la ventana (por ejemplo, “resizable = no, scrollbars = no”). El objeto Window tambien ofrece el metodo **close()** para cerrar una ventana abierta con este metodo.

* **closed :** Esta es una propiedad que nos devuelve true si la ventana referenciada esta cerrada o false si esta abierta.

* **stop()** : Este metodo detiene la carga de recursos en el contexto de navegacion actual.

* **print() :**  Este metodo abre el cuadro de dialogo Imprimir para Imprimir el documento actual.

* **resizeBy() :** Este metodo cambia el tamaño de la ventana actual en una cantidad especifica.

* **resizeTo() :** Este metodo redimensiona dinamicamente la ventana.

* **moveBy() :** Este metodo mueve la ventana en una ubicación relativa.

* **moveTo() :** Este metodo mueve la ventana en una ubicación absoluta.

Ademas de asignar una nueva URL a la propiedad location, tambien podemos manipular la ubicación desde los metodos provistos por el objeto location.

* **Assign(URL) :** Este metodo le pide al navegador que cargue el documento en la ubicación especificada por el atributo URL.

* **Replace(URL) :** Este metodo le pide al navegador que reemplace el documento actual con el documento en la ubicación indicada por el atributo URL. Difiere del metodo **assign()** en que no agrega la URL al historial del navegador.

* **Reload(valor) :** Este metodo le pide al navegador que actualice el documento actual. Aceptar un valor booleano que determina si el recurso se tiene que descargar desde el servidor o se puede cargar desde el cache del navegador (true o false).

**Dato:** El objeto Window no hace falta ser llamado. Es decir podemos utilizar alert() en vez de window.alert().