# Objeto Document
Cuando se carga un documento HTML, el navegador crea una estructura interna para procesarlo. La estructura se llama **DOM** y esta compuesta por multiples objetos de tipo **Element** (u otros tipos mas especificos que heredan de Element), que representan cada elemento en el documento.

Los **objetos Element** mantienen una conexión permanente con los elementos que representan. Cuando se modifica un objeto, su elemento tambien se modifica y el resultado se muestra en pantalla. Para ofrecer acceso a estos objetos y permitirnos alterar sus propiedades desde nuestro codigo JS, los objetos se almacenan en un objeto llamado **Document** que se asigna a la propiedad **document** del objeto Window.

El objeto document incluye las siguientes **propiedades para tener acceso rapido a los objetos Element:**

* **forms :** Esta propiedad devuelve un array con referencias a todos los objetos Element que representan los elementos `<form>` en el documento.

* **images**  :Esta propiedad devuelve un array con referencias a todos los objetos Element que representan los elementos `<img>` en el documento.

* **links :** Esta propiedad devuelve un array con referencias a todos los objetos Element que representan los elementos `<a>` en el documento.

El objeto Document tambien incluye los siguientes **metodos para acceder a objetos individuales element u obtener listas de objetos element** a partir de otros parametros.

* **getElementById("id") :** Este metodo devuelve una referencia al objeto Element que representa el elemento identificado con el valor especificado por el atributo (el valor asignado al atributo id).

* **getElementsByClassName("clase") :** Este metodo devuelve un array con referencias a los objetos Element que representan los elementos identificados con la clase especificada por el atributo (el valor asignado al atributo clase). getElementsByClassName devuelve un objeto similar a un array (HTML colection) por lo que hay que especificar cual queremos utilizar utilizando [].

· **getElementsByName("nombre") :** Este metodo devuelve un array con referencias a los objetos Element que representan los elementos identificados con el nombre especificado por el atributo (el valor asignado al atributo name). getElementsByName devuelve un objeto similar a un array por lo que hay que especificar cual queremos utilizar utilizando [].

* **getElementsByTagName("tipo") :** Este metodo devuelve un array con referencias a los objetos Element que representan el tipo de elementos especificados por el parametro. El parametro es el nombre que identifica a cada tipo de elemento, como **h1, p, img, div,** etc. getElementsByTagName devuelve un objeto similar a un array por lo que hay que especificar cual queremos utilizar utilizando [].

* **querySelector("selector") :** Este metodo devuelve una referencia al objeto Element que representa el elemento que coincide con el selector especificado por el atributo. El metodo devuelve el primer elemento en el documento que coincide con el selector CSS.  Si especificamos de esta forma **selector-posicion** seleccionamos el elemento de x posicion que tenga ese selector.

* **querySelectorAll("selectores") :** Este metodo devuelve un array con referencias a los objetos **Element** que representan los elementos que coinciden con los selectores especificados por el atributo. Se pueden declarar uno o mas selectores separados por comas. querySelectorAll devuelve un objeto similar a un array (Node List) por lo que hay que especificar cual queremos utilizar utilizando [].

**Dato:** Si queremos acceder al body, no hace falta utilizar los metodos anteriores, ya con poner **document.body** lo estamos seleccionando. Si queremos acceder al elemento raiz, es decir el elemento HTML, utilizamos **document.documentElement**.

Accediendo a los objetos Element en el DOM , podemos leer y modificar los elementos en el documento. El navegador lee el documento de forma secuencial y no podemos referenciar un elemento que aun no se ha creado. La mejor solucion a este problema es ejecutar el codigo Javascript solo cuando ocurre el evento load. Los navegadores disparan el evento despues de que se ha cargado el documento y todos los objetos en el DOM se han creado y son accesibles.

Otros metodos del objeto Document:

* **write(texto) :** Este metodo permite escribir en nuestro documento, el texto o codigo que esta dentro del atributo **texto.**

* **createElement(nombre) :** Este metodo crea un nuevo objeto Element del tipo especificado por el atributo nombre. Tiene que ser todo el nombre en mayuscula.

* **createTextNode(texto):** Crea un texto dentro del item.

* **createDocumentFragment() :** Crea un nuevo DocumentFragment vacio, dentro del cual un nodo del DOM puede ser adicionado para construir un nuevo arbol DOM fuera de pantalla. Esto es para optimizar recursos.

```js
document.body.onload = addElement;

function addElement () {
  // crea un nuevo div
  // y añade contenido
  var newDiv = document.createElement("div");
  var newContent = document.createTextNode("Hola!¿Qué tal?");
  newDiv.appendChild(newContent); //añade texto al div creado.

  // añade el elemento creado y su contenido al DOM
  var currentDiv = document.getElementById("div1");
  document.body.insertBefore(newDiv, currentDiv);
}

```