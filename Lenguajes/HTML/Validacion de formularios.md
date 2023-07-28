# Validacion de formularios

Podemos ayudar a los usuarios definiendo reglas de validacion y comunicandolas, asi los usuarios saben que campos son obligatorios y las limitaciones de dichos campos. Si la información tiene el formato correcto, la aplicación permite enviar los datos al servidor y (normalmente) guardarlos en una base de datos; si la información no tiene el formato correcto, le da al usuario un mensaje de error que explica lo que debe corregirse y le permite volver a intentarlo.

Esto se denomina **validacion de formulario del lado del cliente**. Sin embargo, la validacion del lado del cliente no debe considerarse una medida de seguridad exhaustiva. Sus aplicaciones siempre deben realizar comprobaciones de seguridad en los datos enviados por el formulario tanto en el lado del servidor (**validacion de formulario del lado del servidor**) como en el lado del cliente, ya que la validacion del lado del cliente es demasiado facil de eludir.

## Validacion del lado del cliente

### Validacion de formularios integrada

Utiliza funciones de validacion de formularios HTML. La validacion de formulario integrada tiene un mejor rendimiento que JavaScript, pero no es tan personalizable como la validacion de JavaScript.

* **required** : Este es un atributo booleano que indica al navegador que el usuario debe seleccionar o insertar un valor en el elemento para validar el formulario. Le obliga al usuario a ingresar el valor. El navegador también comprueba si los datos introducidos coinciden con el formato del archivo `type`´.

* **novalidate** : Este es un atributo booleano para el elemento `<form>` que indica que el formulario no debería ser validado.

* **formnovalidate** : Este es un atributo booleano para los elementos `<button>` e `<input>` de tipo submit e image que indica que el formulario al que pertenecen no debería ser validado.

* **pattern=”…”** : Este atributo define una expresión regular que el navegador debe usar para validar el valor insertado en el campo. Por ejemplo, `pattern="[a-z]{2-20}"`, el usuario solo puede ingresar al menos dos caracteres y no mas de veinte, en letras minusculas.

* **aria-describedby**: Nos permite conectar el control de formulario con un elemento ya sea div u otro que explique las reglas de validacion. El id del input debe coincidir con el aria-describedby del elemento que va a explicar las reglas.

**Algunos atributos dependiendo el valor del atributo type para validar:**

* Text

	* **maxlength="..."**: Este atributo especifica el numero maximo de caracteres que se permite introducir en el campo.
	
	* **minlength="..."**: Este atributo especifica el minimo numero de caracteres que se permite introducir en el campo.

* Range o Number

	* **min="..."**: El valor de este atributo determina el valor minimo que acepta el campo.
	
	* **max="..."**: El valor de este atributo determina el valor maximo que acepta el campo.

Cuando un elemento es valido o invalido, las siguientes cosas son verdaderas:

* Si es valido, el elemento coincide con la pseudoclase **:valid**, que le permite aplicar un estilo especifico a elementos validos. Por lo contrario, si es invalido, el elemento coincide con la pseudo clase **:invalid** lo que le permite aplicar un estilo especifico a los elementos no validos.

* Si es valido y el usuario intenta enviar los datos, el navegador enviara el formulario, siempre que no haya nada mas que le impida hacerlo. Por lo contrario, si es invalido, no se podraran enviar los datos y se mostrara un mensaje de error.

**Dato** : Puedo modificar el estilo de validacion mediante diferentes pseudoclases.

### Validacion del lado del cliente

Se codifica mediante JavaScript. Esta validacion es completamente personalizable, pero debemos crearla toda (o usar una biblioteca)


[[Validacion de formularios con JS]]

