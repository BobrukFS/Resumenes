# Tipo de datos en Typescript

Nosotros cada vez que declaramos una variable ya sea en el ambito global o mismo dentro de un ambito local, o como parametro en una funcion tenemos que especificar el tipo de dato que va almacenar dicha variable. En caso que querramos reasignar a la variable un valor con un tipo de dato diferente al tipo de dato especificado, ocurrira un error.

En TypeScript, las funciones se pueden escribir de diferentes maneras para indicar los parámetros de entrada y el tipo de retorno de la función.

**Dato**: En TS debemos evitar de definir la menor cantidad de tipos, es deicr, es mejor que se infiera.

```ts
let mensaje : string = "Hola mundo";
mensaje = 5; // Error

function mensaje (msg : string):string {
	return msg
}
```


* **any**
* **unknown**
* **never**
* **arrays**
* **tuplas**
* **enums**
## Tipos inferidos

Cuando nosotros inicializemos una variable, typescript va a ser lo suficientemente inteligente para saber que tipo de dato queremos almacenar en ella sin tener que especificarle el tipo de dato. Es decir el compilador de TS deduce automaticamente el tipo de una variable a partir de su valor y del contexto en el que se usa.

Si nosotros no inicializamos una variable, esta sera de tipo **any** que permite asignarle cualquier valor a la variable, esta no se utiliza porque elimina completamente el proposito de utilizar typescript.

```ts
//Usando el tipo inferido
let mensaje = "Hola mundo";
//Es equivalente a 
let mensaje: string = "Hola mundo";

mensaje = 5; //Error, ya que TSC lo infiere

//Si nosotros no especificamos tipo de dato. Esto nunca se usa.
let mensaje; //Any

//Mejor tipo comun
//Cuando se realiza una inferencia de tipos a partir de varias expresiones, los tipos de esas expresiones se utilizan para calcular el "mejor tipo común".

let x = [0, 1, null] // : number | null
```

## Tipos primitivos

* **Los mismos que vienen en JavaScript**

Con `strictNullChecks`desactivado, los valores a los que se puede `null`o `undefined`se puede acceder normalmente, y los valores `null`y `undefined`se pueden asignar a una propiedad de cualquier tipo. Esto es similar a cómo `null`se comportan los lenguajes sin comprobaciones. La falta de verificación de estos valores tiende a ser una fuente importante de errores; TypeScript siempre recomienda que las personas activen `strictNullChecks`. Con `strictNullChecks`on, cuando un valor es `null`o `undefined`, deberá probar esos valores antes de usar métodos o propiedades en ese valor

### Tipo void

El tipo `void` representa el valor de retorno de funciones que no devuelven un valor. Es el tipo inferido cada vez que una función no tiene `return` declaraciones o no devuelve ningún valor explícito de esas declaraciones de retorno. En JavaScript, una función que no devuelve ningún valor devolverá implícitamente el valor `undefined`. Sin embargo, `void`y `undefined`no son lo mismo en TypeScript.

Void se utiliza comúnmente para funciones que realizan acciones, como imprimir mensajes en la consola o modificar variables. Mientras que indefinido es un valor especial que representa la ausencia de un valor.
## Tipo arrays

```ts
//Usando el tipo inferido
let animales = ["chanchito", "feliz", "felipe"];
// Es equivalente a
let animales: string[] = ["chanchito", "feliz", "felipe"];
// o tambien podemos utilizar
let animales: Array<string> = ["chanchito", "feliz", "felipe"];
//o tambien
let animales : string[] | number[] = ["chanchito", "feliz"];
let animales : string[] | number[] = [1, 2]; //Nos dice que todos los elementos pueden ser de tipo numero o string, en este caso todos los elementos son de numeros

//O tambien
let animales2 : (string | number)[] = [];
animales2.push("hola")
```

Una de las funcionalidades de typescript es que el autocompletado sugiere metodos del tipo de dato con el que se esta tratando.

```ts
//Ejemplo
animales3.map(x => x.toUpperCase); //El autocompletado en este caso muestra metodos para objetos strings.
```

### Matrices

```ts
type CellValue = "X" | "O" | "";

type GameBoard = [
	[CellValue, CellValue, CellValue],
	[CellValue, CellValue, CellValue],
	[CellValue, CellValue, CellValue]
]

const gameBoard: GameBoard = [ //Esto seria una tupla
	["X", "O", "X"],
	["X", "O", "X"],
	["X", "", "X"]
]
```
## Tipo tupla

Una tupla es un tipo de dato que permite definir un array con un numero fijo de elementos, donde cada elemento puede tener un tipo de dato diferente.

No se le pueden agregar o eliminar elementos o cambiar su tipo de dato.

```ts
//Ejemplo 1
let tupla : [number, string] = [1, "chanchito feliz"];

let tupla : [number, string] = [1, "chanchito feliz", 3]; //Error

let tupla : [number, string, number] = [1, "chanchito feliz", 3]

//Ejemplo 2

let tupla : [number, string[]] = [2, ["chanchito", "feliz"]];
```

## Tipo Enums

Los **enums** es un tipo de dato que se utiliza para definir un conjunto de constantes con nombre. Es una forma de darle un nombre legible a un conjunto de valores enteros relacionados. Solo puede ser un tipo de dato. Debe ser finito.

Los enums también pueden ser utilizados como tipos de datos en TypeScript, lo que permite hacer que las funciones acepten solo ciertos valores predefinidos y evita errores de tipado en tiempo de compilación.

Para crear un enum se utiliza la palabra clave enum seguida del nombre en Pascal Case.

```ts
// Asi seria si fuera sin enum
const chica = "s";
const mediana = "m";
const grande = "l";
const extragrande = "xl";

//Es equivalente con enum

enum Talla {Chica = "s", Mediana = "m", Grande = "l", Extragrande = "xl"}

const variable = Talla.Grande; // L

//Utilizando los enum como tipo de datos

let chicos: Talla[] = [Talla.Chica, Talla.Mediana];
```

Si se coloca const delante de un enum en TypeScript, se convierte en un **enum constante**. Esto significa que los miembros del enum no se pueden modificar después de su definición y también se elimina la creación de un objeto namespace para el enum, lo que reduce el tamaño del archivo JavaScript generado.

```ts
const enum Talla {Chica = "s", Mediana = "m", Grande = "l", Extragrande = "xl"}
```

Si el enum se va a consumir desde el exterior, conviene no poner el const pero en todos los otros casos si conviene const.
## Tipo object

Nosotros al crear un objeto tenemos que poner el tipo de dato (al menos que queramos que el compilador lo infiera) que va aceptar el valor de cada propiedad.  Con el **?** podemos indicar una propiedad opcional.

```ts
const objeto : {
	readonly id : number, //Solo de lectura
	nombre : string,
	edad? : number, //Opcional
} = {
	id : 21,
	nombre : "Exequiel"
}
```

Nosotros a un objeto podemos modificar sus propiedades pero si le agregamos la palabra clave **readonly** podemos evitar que se modifique una propiedad. Seria la forma simplificada de writable : false en JS.

## Tipo unknow

El tipo **unknow** representa un valor cuyo tipo exacto no se conoce. Se utiliza principalmente para trabajar con valores que provienen de fuentes externas o que no se han tipado explícitamente. Por ejemplo, si se recibe un valor de una API externa, es posible que no se sepa el tipo exacto del valor, por lo que se puede asignar el tipo `unknown` para indicar que el tipo es desconocido.

A diferencia del tipo `any`, el tipo `unknown` no permite acceder directamente a las propiedades o métodos del valor. Esto ayuda a evitar errores de tiempo de ejecución causados por el acceso a propiedades o métodos inexistentes. Para acceder a las propiedades o métodos de un valor de tipo `unknown`, es necesario primero afirmar el tipo del valor a un tipo más específico.

```ts
// Ejemplo de uso de unknown con valores de una API externa
function obtenerDatosDeAPI(): unknown {
  // Solicitar datos a la API
  const respuesta = fetch("https://api.example.com/datos");
  // Convertir la respuesta a JSON
  const datosJSON = respuesta.json();
  return datosJSON;
}

const datosAPI = obtenerDatosDeAPI();
console.log(datosAPI); // Imprime el valor de datosAPI, que es de tipo unknown

// Ejemplo de afirmar el tipo de un valor unknown
function getNombre(valor: unknown): string | undefined {
  if (typeof valor === "object" && valor.nombre) {
    return valor.nombre;
  }
  return undefined;
}

const nombre = getNombre(datosAPI);
console.log(nombre); // Imprime el valor de nombre, que es de tipo string o undefined

```

## Tipo any

El tipo `any` en TypeScript representa un valor de cualquier tipo. Esto significa que una variable o expresión de tipo `any` puede almacenar cualquier tipo de valor, incluyendo números, cadenas, objetos, funciones, etc.
## Tipo never

El tipo **never** representa el tipo de valores que nunca ocurren. Por ejemplo, `never`es el tipo de retorno para una expresión de función o una expresión de función de flecha que siempre arroja una excepción o una que nunca finaliza.

```ts
// Function returning never must not have a reachable end point
function error(message: string): never {
  throw new Error(message);
}

// Inferred return type is never
function fail() {
  return error('Something failed');
}

// Function returning never must not have a reachable end point
function infiniteLoop(): never {
  while (true) {}
}
```

[[Assertions]]
[[Compatibilidad de tipos]]
[[Type aliases]]
[[Interfaces en Typescript]]
[[Combinando tipos]]
[[Type guards - Narrowing]]