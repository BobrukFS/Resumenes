# Eventos en JS
HTML provee atributos para ejecutar codigo JavaScript cuando ocurre un evento, estos se llaman **Event Handlers**.

Estos atributos, como cualquier otro atributo, se pueden configurar desde JS. Esto se debe a que, los atributos de los elementos se convierten en propiedades de los objetos Element y, por lo tanto, podemos definir sus valores desde codigo JS.

Esto evita incluir atributos de eventos dentro de los elementos HTML, ya que lo declaramos en el codigo de Javascript.

* **addEventListener(evento, listener, captura) :** Este metodo prepara un elemento para responder a un evento. El primer atributo es el nombre del evento (sin el prefijo **on y en comillas**, ejemplo : “click”**)** , el segundo atributo es una referencia a la funcion que responde al evento (llamada **listener**) y el tercer atributo es un valor booleano que determina si el evento va a ser capturado por el elemento o se propagara a otros elementos (Generalmente se ignora o se declara como false).

* **removeEventListener(evento, listener) :** Este metodo elimina el listener de un elemento. Puede servir para eliminar el entorno lexico de la funcion asi no sigue ocupando espacio innecesariamente.

**Dato:** Las funciones listener no pueden ser de flecha y tampoco pueden tener parametros salvo un parametro que es el objeto event. Aunque si puede ser flecha si declaramos la funcion como parametro en el .addEventListener.
## Flujos de eventos o event flow
En DOM se considera que un evento se origina en el exterior de la página web y se propaga de alguna manera hasta los elementos internos de la página. Un posible ejemplo de esta propagación es:

![[Pasted image 20230121192410.png]]
Siguiendo esta idea, se establecen tres etapas: **_captura_**, la cual se da cuando el evento se está trasladando a su destino. **_Blanco_**, que ocurre cuando llega al blanco, o sea que llega a su destino. Este destino es el objeto en el cual se va a crear una reacción a este evento. Finalmente, la etapa de **_burbujeo_** que ocurre cuando el evento «regresa» a su posición original.

* **Event Bubbling  :** Este orden viene por defecto. Se ejecutan los eventos del mas especifico hacia el menos especifico.

* **Event Capturing :** Este orden se activa poniendo como valor del tercer argumento true en addEventListener. Se ejecutan los eventos del menos especifico hacia el mas especifico.
## Eventos
### Mouse
Algunos de los **eventos del mouse**:

* **click :** Este evento ocurre cuando se da un click.

* **dbclick :** Este evento ocurre cuando se da un doble click seguido(medio segundo).

* **mouseover :** Este evento ocurre cuando el puntero se mueve sobre un elemento o sobre uno de sus hijos.

* **mouseout :** Este evento ocurre cuando el puntero se mueve fuera de un elemento o de sus elementos hijos.

* **contextmenu :** Este evento ocurre con un click en el boton derecho en un elemento para abrir un boton contextual.

* **mouseenter :** Este evento ocurre cuando el puntero se mueve sobre un elemento.

* **mouseleave :** Este evento ocurre cuando el puntero se mueve fuera de un elemento.

* **mousedown:** Ocurre cuando un usuario apreta un boton del mouse sobre un elemento.

* **mouseup :** Este evento ocurre cuando un usuario suelta un boton del mouse sobre un elemento.

* **mousemove :** Este evento ocurre cuando el puntero se mueve mientras esta sobre un elemento.
### Teclado

* **keydown :** Este evento ocurre cuando una tecla se deja de presionar.

* **keypress :** Este evento ocurre cuando una tecla se presiona.

* **onkeyup :** Este evento ocurre despues de que los dos eventos anteriores (keypress y keydown) hayan
### Interfaz

*  **error :** Este evento ocurre cuando sucede un error durante la carga de un archivo multimedia.

* **load :** Este evento ocurre cuando un objeto se ha cargado.

* **beforeunload :** El evento beforeunload es disparado cuando la ventana, el documento y sus recursos están a punto de ser descargados.

* **unload** El evento unload se activa cuando se descarga el documento o un recurso secundario.

* **resize :** Este evento ocurre cuando se cambia el tamaño de la vista del documento.

* **scroll :** Este evento ocurre cuando se desplaza la barra de desplazamiento de un elemento.

* **select :** Este evento ocurre despues de que el usuario selecciona algun texto que se encuentra en `<input>` o `<textarea>`.
## Objeto evento
**Cada funcion que responde a un evento recibe un objeto que contiene informacion acerca del evento(Parametro de la funcion listener)**. Aunque algunos eventos tienen sus propias objetos, existe un objeto llamado **Event** que es comun a cada evento.

Las siguientes son algunas de sus propiedades y metodos:

* **target :** Esta propiedad devuelve una referencia al objeto que ha recibido el evento (generalmente es un objeto Element).

* **type :** Esta propiedad devuelve una cadena de caracteres con el nombre del evento.

* **preventDefault() :** Este metodo cancela el evento para prevenir que el sistema realice tareas por defecto.

* **stopPropagation() :** Este metodo detiene la propagacion del evento a otros elementos, de modo que solo el primer elemento que recibe el evento puede procesarlo (normalmente se aplica a elementos que superponen y pueden responder al mismo evento).

Algunos eventos generan valores unicos que se pasan a la funcion listener para ser procesados. Estos eventos trabajan con sus propios tipos de objetos que heredan del objeto Event

Los **eventos del raton** envian un objeto **MouseEvent** a la funcion. Estas son algunas de sus propiedades:

* **button :** Esta propiedad devuelve un entero que representa el botón que se ha pulsado (0 = botón izquierdo).

* **ctrlKey :** Esta propiedad devuelve un valor booleano que determina si la tecla Control se ha pulsado cuando ha ocurrido el evento.

 * **altKey :** Esta propiedad devuelve un valor booleano que determina si la tecla Alt (Option) se ha pulsado cuando ha ocurrido el evento.

* **shiftKey :** Esta propiedad devuelve un valor booleano que determina si la tecla Shift se ha pulsado cuando ha ocurrido el evento.

* **metaKey :** Esta propiedad devuelve un valor booleano que determina si la tecla Meta se ha pulsado cuando ha ocurrido el evento (la tecla Meta es la tecla Windows en teclados Windows o la tecla Command en teclados Macintosh).

* **clientX :** Esta propiedad devuelve la coordenada horizontal donde estaba ubicado el ratón cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace referencia al área que ocupa la ventana.

* **clientY :** Esta propiedad devuelve la coordenada vertical donde estaba ubicado el ratón cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace referencia al área que ocupa la ventana.

* **offsetX :** Esta propiedad devuelve la coordenada horizontal donde estaba ubicado el ratón cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace referencia al área que ocupa el elemento que ha recibido el evento.

* **offsetY :** Esta propiedad devuelve la coordenada vertical donde estaba ubicado el ratón cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace referencia al área que ocupa el elemento que ha recibido el evento.

* **pageX :** Esta propiedad devuelve la coordenada horizontal donde el ratón estaba ubicado cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace relación al documento. El valor incluye el desplazamiento del documento.

* **pageY :** Esta propiedad devuelve la coordenada vertical donde el ratón estaba ubicado cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace relación al documento. El valor incluye el desplazamiento del documento.

* **screenX :** Esta propiedad devuelve la coordenada horizontal donde el ratón estaba ubicado cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace relación a la pantalla.

* **screenY :** Esta propiedad devuelve la coordenada vertical donde el ratón estaba ubicado cuando ha ocurrido el evento. La coordenada se devuelve en píxeles y hace relación a la pantalla.

* **movementX :** Esta propiedad devuelve la diferencia entre la posición actual y la anterior del ratón en el eje horizontal. El valor se devuelve en píxeles y hace relación a la pantalla.

* **movementY** : Esta propiedad devuelve la diferencia entre la posición actual y la anterior del ratón en el eje vertical. El valor se devuelve en píxeles y hace relación a la pantalla.

El objeto MouseEvent nos da las coordenadas del ratón cuando ha ocurrido el evento, pero debido a que cada área tiene su propio sistema de coordenadas, se obtienen diferentes valores.

Otros eventos que producen sus propios objetos Event son los que estan  relacionados con el teclado. El objeto es de tipo **KeyboardEvent** e incluye las siguientes propiedades:

* **key :** Esta propiedad devuelve una cadena de caracteres que identifica la tecla o las teclas que han desencadenado el evento.

* **ctrlKey :** Esta propiedad devuelve un valor booleano que determina si se ha pulsado la tecla Control cuando ha ocurrido el evento.

* **altKey :** Esta propiedad devuelve un valor booleano que determina si se ha pulsado la tecla Alt (Option) cuando ha ocurrido el evento.

* **shiftKey :** Esta propiedad devuelve un valor booleano que determina si se ha pulsado la tecla Shift cuando ha ocurrido el evento.

* **metaKey :** Esta propiedad devuelve un valor booleano que determina si se ha pulsado la tecla Meta cuando ha ocurrido el evento (la tecla Meta es la tecla Windows en los teclados Windows o la tecla Command en los teclados Macintosh).

* **repeat :** Esta propiedad devuelve un valor booleano que determina si el usuario pulsa la tecla continuamente.
## Evento error
Con el proposito de ayudar al codigo a detectar errores y corregirse a si mismo, JS ofrece el evento **error.** Este evento esta disponible en varias API, pero tambien como un evento global al que podemos respondes desde el objeto **Window.**

Al igual que otros eventos, el evento error crea su propio **Event** llamado **ErrorEvent**, para trasmitir informacion a la funcion. Este objeto incluye las siguientes propiedades:

* **error :** Esta propiedad devuelve un objeto con informacion sobre el error.

* **message:** Esta propiedad devuelve una cadena de caracteres que describe el error.

* **lineno :** Esta propiedad devuelve la linea en el documento donde ha ocurrido el error.

* **colno :** Esta propiedad devuelve la columna donde comienza la instrucción que ha producido el error.

* **filename :** Esta propiedad devuelve la URL del archivo donde ha ocurrido el error.

Ejemplo:

![[Pasted image 20230121203407.png]]
![[Pasted image 20230121203412.png]]
