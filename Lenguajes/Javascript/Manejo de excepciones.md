# Exception Handling

Por lo general, un script "muere" (se detiene inmediatamente) en caso de error, imprimiendo el error en la consola. Los errores son lanzados por el motor y las excepciones son lanzadas por el desarrollador. 

Sin embargo, hay una construccion sintactica **try... catch** que nos permite "atrapar" errores para que el script pueda manejar los errores. Donde mas vamos a encontrar excepciones es al realizar solicitudes HTTP.

La construccion **try....catch** tiene dos bloques principales: **try** y luego **catch**. La instruccion try indica el grupo de instrucciones que pueden generar errores., si ocurre un error en tiempo de ejecucion, Error se crea y lanza un nuevo objeto a la instrucion catch. Mientras que la instruccion catch indica el grupo de instrucciones que deberian ejecutarse si ocurre un error para poder manejarlo. La variable error (podemos usar cualquier nombre para ella) contendra un objeto de error con detalles sobre lo que sucedio.

```js
try {
	//codigo
} catch (error) {
	// manipulacion de error
}
```

![[Pasted image 20230611161900.png]]

Ejemplo:

```js
let json = 'json malo';

try {
	let user = JSON.parse(json);
	alert(user.name); //No funciona
} catch (error){
	alert("Nuestras disculpas, los datos tienen un error");
	alert(err.name);
	alert(err.message);
}
```

Aquí usamos el bloque `catch` solo para mostrar el mensaje, pero podemos hacer mucho más: enviar una nueva solicitud de red, sugerir una alternativa al visitante, enviar información sobre el error a una instalación de registro.

**Dato:** Para que try..catch funcione, el código debe ser ejecutable. En otras palabras, debería ser JavaScript válido. Try…catch solo funciona para **errores de tiempo de ejecucion,** estos son errores que ocurren en codigo Javascript valido. El motor de JavaScript primero lee el código y luego lo ejecuta. Los errores que ocurren en la fase de lectura se denominan **errores de “tiempo de análisis”** y son irrecuperables (desde dentro de ese código). Eso es porque el motor no puede entender el código.

**Dato**: Try…catch trabaja sincronicamente por lo que si ocurre una excepcion en el codigo “programado” como en setTimeout entonces try…catch no lo detectara, esto se debe a que la funcion en si misma se ejecuta mas tarde, cuando el motor ya ha abandonado la construccion try…catch. Para detectar una excepcion dentro de una funcion programada, try…catch debe estar dentro de esa funcion.

**Dato**: Si no necesitamos detalles del error, el argumento que se la pasa a catch puede ser omitido.

**Dato**: Las variables son locales dentro de try...catch...finally

### Finally

La construccion try...catch puede tener una instruccion **finally**.  La instruccion finally se ejecuta pase lo que pase. Tiene prioridad sobre todo. La cláusula finally a menudo se usa cuando comenzamos a hacer algo y queremos finalizarlo en cualquier resultado.

```js
try {
	//intenta ejecutar el codigo
} catch (err) {
	 //Maneja errores
} finally {
	// Ejecuta siempre
}
```

Por ejemplo, queremos medir el tiempo que tarda una función de números de Fibonacci `fib(n)`. Naturalmente, podemos comenzar a medir antes de que se ejecute y terminar después. ¿Pero qué pasa si hay un error durante la llamada a la función? En particular, la implementación de `fib(n)` en el código siguiente devuelve un error para números negativos o no enteros.

La cláusula `finally` es un excelente lugar para terminar las mediciones, pase lo que pase.

Aquí `finally` garantiza que el tiempo se medirá correctamente en ambas situaciones, en caso de una ejecución exitosa de `fib` y en caso de error.

```js
let num = +prompt("Ingrese un número entero positivo?", 35) 
let diff, result; 
function fib(n) { 
	if (n < 0 || Math.trunc(n) != n) { 
		throw new Error("Debe ser un número positivo y entero."); 
	} 
	return n <= 1 ? n : fib(n - 1) + fib(n - 2); 
} 
let start = Date.now(); 

try { 
	result = fib(num); 
} catch (err) { 
	result = 0; 
} finally { 
	diff = Date.now() - start; 
} 
alert(result || "error ocurrido"); 
alert( `la ejecución tomó ${diff}ms` );
```

La clausula finally funciona para cualquier salida de try...catch. Esto incluye un return explicito. 

Finally se puede utilizar sin la clausula catch, esto es util cuando no queremos manejar errores, pero queremos asegurarnos de que los procesos que comenzamos esten finalizados.

## Lanzando nuestros propios errores

El operador **throw** genera un error. Técnicamente, podemos usar cualquier cosa como un objeto error, podemos usar objetos de error genericos o personalizados. Eso puede ser incluso un primitivo, como un número o una cadena, pero es mejor usar objetos, preferiblemente con propiedades `name` y `message`.

```js 
throw <error object>
```

### Relanzando (rethrowing)

Catch solo debe procesar los errores que conoce y “volver a lanzar” (rethrow) a todos los demás.

1.  Catch captura todos los errores.

2.  En el bloque catch (err) {...} analizamos el objeto error err.

3.  Si no sabemos cómo manejarlo, hacemos 'throw err`.

Por lo tanto, el bloque catch en realidad maneja solo los errores con los que sabe cómo lidiar y “omite” todos los demás.

En ejemplos anteriores vimos try…catch para detectar datos incorrectos pero tambien pueden ocurrir otros tipos de problemas como un error en la sintaxis, por lo que nosotros podemos especificar que error controlar y cuales no sabemos como manejarlo.

Un ejemplo podemos usarlo para que solo maneje el error SyntaxError, ya que verifica si err es una instancia de la clase SyntaxError:

![[Pasted image 20230121211216.png]]

El error lanzado en la línea (`*`) desde el interior del bloque catch cae desde try...catch y puede ser atrapado por una construcción externa try...catch (si existe), o mata al script.

![[Pasted image 20230121211239.png]]

El try catch en programación se utiliza para manejar fragmentos de código que son propensos a fallar, como puede ser: recibir un valor nulo, convertir un tipo de dato a otro o en tu caso, la lectura de un archivo.

## Objeto Error

### Generico

Cuando se produce un error, JS genera un objeto generico que contiene los detalles al respecto. El objeto se pasa como argumento para la instruccion catch. Dicho objeto posee diversas propiedades:

 * **name**: Nombre del error.
 * **message**: Mensaje de texto sobre detalles del error.
 * **stack**: Una cadena con informacion sobre la secuencia de llamadas anidadas que condujeron al error. Utilizado para fines de depuracion.

```js
//Ejemplo
try {
  z
  console.log("Sin error")
  console.log("hola")
} catch (err) {
  console.log(err.name); //ReferenceError
  console.log(err.message); //z is not defined
  console.log(err.stack);// ReferenceError: z is not defined (...call stack)
}
```

JS tiene muchos constructores integrados para manejar errores estandar: Error, SyntaxError, ReferenceError, TypeError y otros. Podemos usarlos para crear objetos de error tambien.

```js

let error = new Error(message); 
let error = new SyntaxError(message); 
let error = new ReferenceError(message);

//Ejemplo

let error = new Error("Estas cosas pasan... o_O"); 
alert(error.name); // Error 
alert(error.message); // Estas cosas pasan... o_O
```


### Personalizado

Cuando desarrollamos algo, a menudo necesitamos nuestras propias clases de error para reflejar cosas especificas que pueden salir mal en nuestras tareas. Nuestros errores deben admitir propiedades de error basicas como message, name y preferiblemente, stack. Pero tambien pueden tener otras propiedades propias, por ejemplo, los objetos HttpError pueden tener una propiedad statusCode como un valor como 404, etc.

JavaScript permite usar `throw` con cualquier argumento, por lo que técnicamente nuestras clases de error personalizadas no necesitan heredarse de `Error`. Pero si heredamos, entonces es posible usar **obj instanceof Error** para identificar objetos error. Entonces es mejor heredar de él.

```js
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
} // Uso

function readUser(json) {
  let user = JSON.parse(json);
  if (!user.age) {
    throw new ValidationError("Sin campo: age");
  }
  if (!user.name) {
    throw new ValidationError("Sin campo: name");
  }
  return user;
} // Ejemplo de trabajo con try..catch 

try { 
	let user = readUser('{ "age": 25 }'); 
} catch (err) { 
	if (err instanceof ValidationError) { 
	  alert("Dato inválido: " + err.message); // Dato inválido: sin campo: nombre                                                                    
	} else if (err instanceof SyntaxError) { // (*) 
	alert("Error de sintaxis JSON: " + err.message); 
	} else { 
	  throw err; // error desconocido, vuelva a lanzarlo (**) 
	} 
}

//La versión `instanceof` es mucho mejor, porque en el futuro vamos a extender `ValidationError`, haremos subtipos de ella, como `PropertyRequiredError`. Y el control `instanceof` continuará funcionando para las nuevas clases heredadas. Entonces eso es a prueba de futuro.
```


## Empacado de excepciones

Es una tecnica generalizada: Una funcion maneja excepciones de bajo nivel y crea errores de alto nivel en lugar de varios errores de bajo nivel. Las excepciones de bajo nivel a veces se convierten en propiedades de ese objeto.

Entonces sirve para saber si hubo un error, el porque ocurrio exactamente es a menudo irrelevante. O, mejor aun, nos gustaria tener una forma de obtener los detalles del error, pero solo si es necesario.

Ejemplo:

1. Crearemos una nueva clase ReadError para representar un error generico de lectura de datos
2. La funcion readUser detectara los errores de lectura de datos que ocurren dentro de ella, como ValidationError y SyntaxError, y generara un ReadError en su lugar.
3. El objeto ReadError mantendra la referencia al error original en su propiedad cause.

```js
class ReadError extends Error {
  constructor(message,cause){
    super(message);
    this.cause = cause;
    this.name = "ReadError";
  }
}

class ValidationError extends Error {
   constructor(message) {
    super(message);
    this.name = "ValidationError";
   }
}

class PropertyRequiredError extends ValidationError {
 constructor(property) {
    super("Sin propiedad: " + property);
    this.name = "PropertyRequiredError";
    this.property = property;
}
}

function validateUser(user){
  if(!user.age){
    throw new PropertyRequiredError("age");
  } 
  if (!user.name){
    throw new PropertyRequiredError("name");
  }
}

function readUser(json){
  let user;
  try {
    user = JSON.parse(json);
  } catch(err) {
    if (err instanceof SyntaxError){
      throw new ReadError("Error de sintaxis", err)
    } else {
      throw err
    }
  }
  try {
    validateUser(user);
  } catch (err){
    if(err instanceof ValidationError){
      throw new ReadError ("Error de validacion", err);
    } else {
      throw err;
    }
  }
}

try {
  readUser(`{"age": 25 }`);
} catch (e){
  if (e instanceof ReadError){
    console.log(e);
    console.log("Error original: " + e.cause)
  } else {
    throw e;
  }
}

```
Entonces el codigo que llama a readUser solo tendra que verificar ReadError, no todo los tipos de errores de lectura de datos. Y si necesita mas detalle de un error, puede verificar su propiedad cause.