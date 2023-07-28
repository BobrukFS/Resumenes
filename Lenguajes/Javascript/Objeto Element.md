# Objeto Element
#### Propiedades
Los objetos **Element** contienen **propiedades** para manipular y definir los estilos de los elementos y sus contenidos.

* **id :** Indica el identificador del elemento (es el valor del atributo id).

* **name :** Nombre del elemento(atributo name).

* **tagName :**  Nombre de la etiqueta HTML que tiene el elemento.

* **attributes :** Devuelve una colección con todos los atributos HTML que tenga definidos el elemento. Cada atributo sera un objeto con las propiedades name y value.

* **style :** Representa un objeto con todos los estilos del elemento. Podremos consultar y modificar cualquier propiedad CSS.

* **innerHTML :** Permite acceder al contenido del elemento, como un string, incluyendo todas las etiquetas HTML de los elementos anidados.

* **outerHTML :** Es similar a innerHTML pero incluye ademas las etiquetas del propio elemento.

* **textContent :** Esta propiedad devuelve el texto de cualquier nodo.

* **firstChild :** La propiedad de sólo lectura Node.firstChild devuelve el último hijo del nodo. Si su padre es un elemento, entonces el hijo es generalmente un nodo de element, nodo de texto o un nodo de comentario. Devuelve null si no hay elementos hijos. Si hay espacios devuelve texto, por lo que hay que estar atento. Podemos utilizar **firstElementChild** para que encuentre como primer nodo un elemento.

* **lastChild :** La propiedad de sólo lectura Node.lastChild devuelve el último hijo del nodo. Si su padre es un elemento, entonces el hijo es generalmente un nodo de element, nodo de texto o un nodo de comentario. Devuelve null si no hay elementos hijos. Si hay espacios devuelve texto, por lo que hay que estar atento. Podemos utilizar **lastElementChild** para que encuentre como ultimo nodo un elemento.

* **childNodes :** La propiedad de solo lectura Node.childNodes  devuelve una colección de hijos nodes del elemento dado donde el primer nodo hijo es asignado un índice 0. Esto no es un array, es una lista de nodos. Sin embargo lo podemos recorrer con un forEach porque es un objeto.


* **children :** La propiedad de solo lectura children devuelve un live HTMLCollection que contiene todos los elementos secundarios elements del elemento sobre el que se invocó. Element.children incluye solo nodos de elementos. Una HTMLCollection la podemos recorrer con un for of.

* **parentElement :** La propiedad de sólo lectura de  Nodo.parentElement devuelve el nodo padre del DOM  Element, o null, si el nodo no tiene padre o si el padre no es un ElementDOM .

* **parentNode :** La propiedad de sólo lectura node.parentNode devuelve el padre del nodo especificado en el árbol.

* **nextSibling :** La propiedad de sólo lectura Node.nextSibling devuelve el siguiente nodo hermano con respecto al indicado en la lista de nodos ( childNodes) a la que este pertenece o nullsi el nodo especificado es el último en dicha lista.

* **previousSibling :** La propiedad de sólo-lectura  Node.previousSibling devuelve el nodo hermano inmediatamente anterior al especificado en la lista de nodos childNodesde su padre, o  null si el nodo especificado es el primero en dicha lista.

* **nextElementSibling :** La propiedad nextElementSibling devuelve el siguiente elemento en el mismo nivel de árbol.

* **previousElementSibling :** La propiedad nextElementSibling devuelve el anterior elemento en el mismo nivel de árbol.

Una de estas propiedades es **style**, el cual contiene un objeto llamado **Styles** que a su vez incluye propiedades para modificar los estilos de los elementos. La sintaxis seria **element.style.propiedad.**

Los nombres de los estilos en Javascript no son los mismos que en CSS. Las siguientes son las propiedades que mas se usan:

* **color :** Esta propiedad declara el color del contenido del elemento.

* **background :** Esta propiedad declara los estilos del fondo del elemento. Tambien podemos trabajar con cada estilo de forma independiente usando las propiedades asociadas **backgroundColor, backgroundImage, backgroundRepeat, backgroundPosition y backgroundAttachment.**

* **border:** Esta propiedad declara los estilos del borde del elemento. Podemos modificar cada estilo de forma independiente con las propiedades asociadas **borderColor, borderStyle, borderWidth,** o modificar cada borde individualmente usando las propiedades asociadas **borderTop (borderTopColor, borderTopStyle, borderTopWidth), borderBottom (borderBottomColor, borderBottomStyle, borderBottomWidth), borderLeft (borderLeftColor, borderLeftStyle, y borderLeftWidth), y borderRight (borderRightColor, borderRightStyle, y borderRightWidth).**

* **margin :** Esta propiedad declara el margen del elemento. Tambien podemos usar las propiedades asociadas **marginBottom, marginLeft, marginRight, y marginTop.**

* **padding :** Esta propiedad declara el relleno del elemento. También podemos usar las propiedades asociadas **paddingBottom, paddingLeft, paddingRight, y paddingTop.**

* **width :** Esta propiedad declara el ancho del elemento. Existen dos propiedades asociadas para declarar el ancho máximo y mínimo de un elemento: **maxWidth y minWidth.**

* **height :** Esta propiedad declara la altura del elemento. Existen dos propiedades asociadas para declarar la altura máxima y mínima de un elemento: maxHeight y minHeight.

* **visibility :** Esta propiedad determina si el elemento es visible o no.

* **display :** Esta propiedad define el tipo de caja usado para presentar el elemento.

* **position :** Esta propiedad define el tipo de posicionamiento usado para posicionar el elemento.

* **etc**

Para modificar los valores de estas propiedades es sencillo. Debemos obtener una referencia al objeto Element que representa el elemento que queremos modificar, y luego asignar un nuevo valor a la propiedad del objeto Styles que queremos cambiar. La unica diferencia con CSS, ademas de los nombres de las propiedades es que los **valores se tienen que asignar entre comillas.**

Ejemplo :

![[Pasted image 20230120152706.png]]
Las propiedades del objeto Style son independientes de los estilos CSS asignados al documento. Si intentamos leer una de estas propiedades pero aun no le hemos asignado ningun valor desde JavaScript, el valor que devuelve sera una cadena de caracteres vacia. Para proveer informacion acerca del elemento, los objetos Element incluyen propiedades adicionales. Las siguientes son las que mas se usan:

* **clientWidth :** Esta propiedad devuelve el ancho del elemento, incluido el relleno.

* **clientHeight :** Esta propiedad devuelve la altura del elemento, incluido el relleno.

* **offsetTop :** Esta propiedad devuelve el numero de pixeles que se ha desplazado el elemento desde la parte superior de su contenedor.

* **offsetLeft :** Esta propiedad devuelve el numero de pixeles que se ha desplazado el elemento desde el lado izquierdo de su contenedor.

* **offsetWidth :** Esta propiedad devuelve el ancho del elemento, incluidos el relleno y el borde.

* **offsetHeight :** Esta propiedad devuelve la altura del elemento, incluidos el relleno y el borde.

* **scrollTop :** Esta propiedad devuelve el numero de pixeles en los que el contenido del elemento se ha desplazado hacia arriba.

* **scrollLeft :** Esta propiedad devuelve el numero de pixeles en los que el contenido del elemento se ha desplazado hacia la izquierda.

* **scrollWidth** **:** Esta propiedad devuelve el ancho del contenido del elemento.

* **scrollHeight :** Esta propiedad devuelve la altura del contenido del elemento.

* **getBoundingClientRect()** :  es un método en JavaScript que puedes utilizar para obtener la posición y el tamaño de un elemento en relación con la ventana gráfica o el documento. Esta función devuelve un objeto `DOMRect` que contiene información sobre las coordenadas del elemento, como el valor `top` , `left` , `right` y `bottom` , así como el ancho y alto del elemento.

Estas son propiedades de solo lectura, pero podemos obtener el valor que necesitamos leyendo estas propiedades y despues usar las propiedades del objeto Styles para asignarles uno nuevo.

Las **clases** se definen de forma permanente en hojas de estilo CSS, pero los objetos Element incluyen las siguientes propiedades para **asignar una clase diferente a un elemento y, por lo tanto, modificar sus estilos todos a la vez.**

* **className :** Esta propiedad declara o devuelve el valor del atributo class.

* **classList :** Esta propiedad devuelve un array con la lista de las clases asignadas al elemento.

El array que devuelve la propiedad classList es de tipo **DOMTokenList,** que incluye los siguientes metodos para modificar las clases de la lista. La sintaxis seria **element.classList.metodo();**

* **add(clase) :** Este metodo agrega una clase al elemento

* **remove(class) :** Este metodo elimina una clase del elemento.

* **toggle(clase, decision) :** Este metodo agrega o elimina una clase dependiendo del estado actual. Si la clase ya se ha asignado al elemento, la elimina, y en caso contrario la agrega.Si en el parametro decision (opcional) le agregamos false, en caso de que no este no la agregara, y si agregamos true, si la clase se encuentra, no la eliminara.

* **contains(clase) :** Este metodo detecta si se ha asignado la clase al elemento o no, y devuelve **true o false** respectivamente.

* **replace(old, new) :** Este metodo reemplaza una clase por otra.

* **item(indice) :** Este metodo devuelve la clase del indice especificado

#### Metodos

* **appendChild(elemento hijo) :** Este metodo inserta el elemento representado por un objeto Element, como hijo de un elemento existente en el documento. El atributo debe ser una referencia del elemento hijo a insertarse.

* **removeChild(elemento hijo) :** Este metodo elimina un elemento hijo de otro elemento. El atributo debe ser una referencia del hijo a eliminarse.

* **replaceChild(new, old) :** Este metodo reemplaza un elemento HTML por otro nuevo.

* **remove(elemento) :** El método  Element.remove() elimina el elemento del DOM. Tiene que ser todo en mayuscula.

* **hasChildNodes() :** El método Node.hasChildNodes()devuelve un valor  booleano  que indica si el Node(nodo) actual tiene nodos hijos o no.

* **closest(selector) :** El método  closest() de la interfaz Element devuelve el ascendente más cercano al elemento actual (o el propio elemento actual) que coincide con el selector proporcionado por parámetro. Si no existe dicho ascendente, devuelve  null.

* **insertBefore(new node, referenceNode)**: inserta un nodo antes del nodo de referencia como hijo de un nodo padre indicado.

Tambien hay otras formas para modificar, obtener y definir un atributo:

* **setAttribute(attribute, value) :** Añade un atributo al elemento con el nombre y valor indicado.

* **getAttribute(attribute) :** Nos devuelve el valor del atributo que indiquemos.

* **removeAttribute(attribute) :** Elimina del elemento el atributo con el mismo nombre.

* **insertAdjacentHTML("ubicación", contenido) :** Este metodo inserta contenido en una ubicación determinada por el atributo **ubicación**. Los valores disponibles son **beforebegin** (antes del elemento), **afterbegin** (dentro del elemento, antes del primer elemento hijo), **beforeend** (dentro del elemento, despues del ultimo elemento hijo) y **afterend**(despues del elemento).



