# Formularios

Los **formularios** son herramientas que podemos incluir en un documento para permitir a los usuarios insertar información, tomar decisiones, comunicar datos y cambiar el comportamiento de una aplicación. El propósito principal de los formularios es permitir al usuario seleccionar o insertar información y enviarla al servidor para ser procesada.

* **`<form></form>`**: El elemento **form** se utiliza para crear un formulario, todos los elementos del formulario van dentro de estas etiquetas. Algunos atributos del elemento form son:

	* **name="..."**: El atributo **name** especifica el nombre del formulario. 
	
	* **method="..."**: El atributo **method** determina el metodo a utilizar para enviar la informacion al servidor. Existen dos valores disponibles: **GET** y **POST**.  El valor predeterminado es GET.
	
	* **action="..."**: El atributo **action** declara la URL del archivo en el servidor que va a procesar la informacion enviada por el formulario. Es decir a donde se va a enviar la informacion.  Esta aplicacion tambien se encarga de generar la respuesta que muestra el servidor. Otro nombre de esa URL es Endpoint, point, route, resource.
	
	* **target="..."**: El atributo **target** determina donde se mostrara la respuesta recibida desde el servidor. Los valores disponibles son \_blank (nueva ventana), \_self (mismo recuadro),\_parent (recuadro padre), y \_top (la ventana que contiene el recuadro). El valor \_self se declara por defecto, lo que significa que la respuesta recibida desde el servidor se mostrará en la misma ventana.

###  Elementos que pueden ir dentro de form

Un formulario puede incluir diferentes herramientas para permitir al usuario seleccionar o insertar información. HTML incluye múltiples elementos para crear estas herramientas dentro de nuestra etiqueta `<form>`. Los siguientes son los más utilizados:

* **`<input>`**: El elemento input crea un campo de entrada para la informacion o tambien puede ser un boton.  Algunos atributos de input:

	* **type="..."** : Este atributo indica que tipo de dato va a recibir como entrada el elemento input (text, file,  email, search, url, tel, number, range, submit, reset, password, radio, checkbox, etc).
	
	* **value="..."**: El atributo **value** determina un valor ya definido pero que se puede cambiar y es el que se enviara al servidor, por ejemplo en checkbox, etc.
	
	* **placeholder=”…”** : Este atributo muestra un texto en el fondo del elemento que indica al usuario el valor que debe introducir.

	* **name** : Identifica los datos que el usuario ingresa con el input. Si envia el formulario, este nombre se incluye en la solicitud


* **`<textarea></textarea>`**: El elemento **textarea** crea un campo de entrada para insertar multiples lineas de texto. El elemento textarea tiene varios atributos:

	* **maxlength="..."**: Este atributo especifica el numero maximo de caracteres que se permite introducir en el campo.
	
	* **minlength="..."**: Este atributo especifica el minimo numero de caracteres que se permite introducir en el campo.

* **`<label></label>`**: El elemento **label** crea un etiqueta/titulo para identificar un elemento de formulario. Se utiliza en conjunto con el atributo **for="id del elemento"** para que cuando al tocar label, se seleccione tambien el elemento del formulario con el mismo id al que hace referencia for.

* **`<select></select>`**: Este elemento crea una lista de opciones que el usuario puede elegir. Trabaja junto con el elemento **`<option>…</option>`** para definir cada opción y el elemento **`<optgroup>…</optgroup>`** para organizar las opciones en grupos.

	* **value="..."**: El valor de este atributo determina un valor ya definido pero que se puede cambiar y es el que se enviara al servidor.
	* **selected** : Para que aparezca una opcion seleccionada.

* **`<fieldset></fieldset>`**: El elemento **fieldset** agrupa otros elementos del formulario. Se usa para crear secciones dentro de formulario extensos. El elemento fieldset debe contener un elemento **`<legend></legend>`** para definir el titulo de la seccion.

* **`<button></button>`**: El elemento **button** crea un boton. Incluye el atribute **type** para definir el proposito del boton. Los valores disponibles para el atributo type son **submit** para enviar el formulario (este viene por defecto), **reset** para reiniciar el formulario, y **button** para realizar tareas personalizadas. Con el atributo **value="..."** le asignamos un nombre al boton. Un boton no puede ir dentro de un elemento `<a>`. El boton cumple el mismo proposito que un input submit.

* **`<output></output>`**: El elemento **output** representa un resultado producido por el formulario. Se implementa por medio de codigo Javascript para mostrar el resultado de una operacion al usuario.

* **`<meter></meter>`**: El elemento **meter** representa una medida o el valor actual de un rango.

* **`<progress></progress>`**: El elemento **progress** representa el progreso de una operacion. El elemento progress se usa para informar del progreso en la ejecucion de una tarea.

	* **value="..."**: El atributo **value** indica el progreso logrado hasta el momento.
	
	* **max="..."**: El atributo **max** declara el valor que necesitamos alcanzar para dar por finalizada la tarea.

* **`<datalist></datalist>`**: El elemento **datalist** crea un listado de valores disponibles para otros controles. Trabaja junto con el elemento **`<option>`** para definir cada valor.

### Atributos globales para formularios

Estos atributos son exclusivos de los elementos de formulario:

* **disabled** : Este es un atributo booleano que desactiva el elemento. Cuando el atributo está presente, el usuario no puede introducir valores o interactuar con el elemento. El atributo disabled normalmente se implementa cuando queremos mostrar al usuario que el elemento puede estar disponible en otras condiciones, como cuando el control no es aplicable en el país del usuario.
* **readonly** : Este atributo booleano indica que el valor del elemento no se puede modificar. Se implementa cuando solo existe un valor posible y no queremos que el usuario lo cambie.
* **placeholder=”…”** : Este atributo muestra un texto en el fondo del elemento que indica al usuario el valor que debe introducir.
* **autocomplete=”…”** : Este atributo activa o desactiva la función de autocompletar. Los valores disponibles son on y off. Los navegadores pueden identificar el tipo de datos a completar al observar los atributos de control de formulario: name, id y types.
* **multiple** : Este es un atributo booleano que indica al navegador que se pueden insertar múltiples valores en el campo (se aplica a elementos `<input>` de tipo email y file).
* **autofocus** : Este atributo booleano solicita al navegador que mueva el foco al elemento tan pronto como se carga el documento.
* **form=”…”** : Este atributo asocia el elemento con un formulario. Se usa para conectar un elemento con un formulario cuando el elemento no se define entre las etiquetas `<form>`. El valor asignado a este atributo debe ser el mismo asignado al atributo id del elemento `<form>`.
* **spellcheck=”…”** : Este atributo solicita al navegador que compruebe la ortografía y gramática del valor introducido en el campo. Los valores disponibles son true (verdadero) y false (falso).



## Enviando formularios

Cuando se envia un formulario, los datos introducidos se envian al servidor usando la sintaxis **nombre/valor** para cada elemento, donde nombre es el valor asignado al atributo **name** del elemento y **valor** es el valor que introduce el usuario. Por ejemplo, si insertamos el texto Exequiel en un campo de entrada con el atributo name=“myname”, el par nombre/valor que se envia al servidor sera myname/Exequiel.

Los navegadores usan dos metodos para enviar esta informacion: GET y POST. Los navegadores se comunican con el servidor usando un protocolo llamado HTTP. Cuando el navegador quiere acceder a un documento, envia una solicitud HTTP al servidor. 

Mas informacion sobre formularios en https://web.dev/learn/forms/

[[Validacion de formularios]]
[[Peticiones HTTPS]]












