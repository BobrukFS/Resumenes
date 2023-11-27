# Assert

La función o módulo assert se suele utilizar en todos los lenguajes que la tienen para comprobar que el contenido que se le está pasando a la función es verdadero y debe salir del programa o lanzar un error en caso contrario. Podemos acceder a él con require('assert').

En general los asserts son usados en los tests, dado que permiten comprobar que ciertas condiciones se han cumplido y te permiten mostrar mensajes personalizados.
## Metodos

* **assert.fail(actual, expected, message, operator)**: Evalua si actual es igual a expected usando el operador provisto.
* **assert.ok(value, [message])**: Evalua si el valor es true es equivalente a **assert.equal(true,value,message)**.

* **assert.equal(actual, expected, [message])**: Evalua la igualdad con el operador de comparacion `==`.
* **assert.notEqual(actual, expected, [message] )**: Evalua la no igualdad con el operador de comparacion en negacion `!=`.
* **assert.deepEqual(actual, expected, [message])**: Prueba para los tests de afirmacion de desigualdad profunda.
* **assert.notDeepEqual(actual, expected, [message])**: Prueba para cualquier desigualdad profunda.
* **assert.strictEqual(actual, expected, [message])**: Prueba de igualdad estrictas, segun lo determinado por el operador de igualdad estricta.
* **assert.notStrictEqual(actual, expected, [message])**: Pruebas de no igualdad estrictas, según lo determinado por el operador de no igualdad estricto `(!==)`.
* **assert.throws(block, [error], [message])**: Se espera lanzar un bloque(block) de error. El error puede ser un constructor, expresión regular (regexp) o una función de validación.
* **assert.doesNotThrow(block, [error], [message])**: Se espera un bloque (block) y que no produzca un error. Vea assert.throws para más detalles.
* **assert.ifError(value)**: Comprueba si el valor no es falso, se produce un lanzamiento si el valor es verdadero. Resulta útil cuando se prueba el primer argumento, error en los callbacks.
```js
//Error de validacion personalizado
assert.throws( 
	function() { 
		throw new Error("Wrong value"); 
	}, 
	function(err) { 
		if ( (err instanceof Error) && /value/.test(err) ) { 
			return true; 
		} 
	}, 
	"unexpected error" 
);
```