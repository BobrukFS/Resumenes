Nosotros cada vez que declaramos una variable ya sea en el ambito global o mismo dentro de un ambito local, o como parametro en una funcion tenemos que especificar el tipo de dato que va almacenar dicha variable. En caso que querramos reasignar a la variable un valor con un tipo de dato diferente al tipo de dato especificado, ocurrira un error.

```ts
let mensaje : string = "Hola mundo";
mensaje = 5; // Error

function mensaje (msg : string) {
	return msg
}
```

# Tipo de datos en Typescript

* **Los mismos que vienen en Javascript.**
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
```

## Tipo arrays

```ts
//Usando el tipo inferido
let animales = ["chanchito", "feliz", "felipe"];
// Es equivalente a
let animales: string[] = ["chanchito", "feliz", "felipe"];
// o tambien podemos utilizar
let animales: Array<string> = ["chanchito", "feliz", "felipe"];
```

Una de las funcionalidades de typescript es que el autocompletado sugiere metodos del tipo de dato con el que se esta tratando.

```ts
//Ejemplo
animales3.map(x => x.toUpperCase); //El autocompletado en este caso muestra metodos para objetos strings.
```
## Tipo tupla

Una tupla es un tipo de dato que permite definir un array con un numero fijo de elementos, donde cada elemento puede tener un tipo de dato diferente.

No se le pueden agregar o eliminar elementos o cambiar su tipo de dato.

```ts
//Ejemplo 1
let tupla : [number, string] = [1, "chanchito feliz"];

let tupla : [number, string] = [1, "chanchito feliz", 3]; //Error

//Ejemplo 2

let tupla : [number, string[]] = [2, ["chanchito", "feliz"]];
```

## Tipo Enums
Los **enums** es un tipo de dato que se utiliza para definir un conjunto de constantes con nombre. Es una forma de darle un nombre legible a un conjunto de valores enteros relacionados. Solo puede ser un tipo de dato.

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

## Tipo objetos

Nosotros al crear un objeto tenemos que poner el tipo de dato (al menos que queramos que el compilador lo infiera) que va aceptar el valor de cada propiedad.  Con el **?** podemos indicar una propiedad opcional.

```ts
const objeto : {
	id : number,
	nombre : string,
	edad? : number,
};
```

Nosotros a un objeto podemos modificar sus propiedades pero si le agregamos la palabra clave **readonly** podemos evitar que se modifique una propiedad. Seria la forma simplificada de writable : false en JS.

## Type

**Type** como enum nos permiten crear tipos de datos personalizados. Los type permiten definir un alias para un tipo existente o para una combinacion de tipos existentes.

```ts
//Ejemplo

enum Talla {Chica = "s", Mediana = "m", Grande = "l", Extragrande = "xl"} // Creamos un conjunto de valores constantes con nombres asociados.

let chicos: Talla[] = [Talla.Chica, Talla.Mediana]

type Direccion = { //Creamos el tipo de dato personalizado Direccion.
    numero: number,
    calle: string,
    pais: string,
}

type Persona = { //Creamos el tipo de dato personalizado Persona
    readonly id: number,
    nombre: string,
    talla: Talla,
    direccion : Direccion,
    /* direccion : {
        numero: number,
        calle: string,
        pais: string,
    }
    */
}

  

const objeto: Persona = {
    id : 1,
    nombre: "Hola mundo",
    talla : Talla.Mediana,
    direccion : {
        numero : 1,
        calle : "Siempre viva",
        pais : "Chanchitolandia",
    }
}

let arr: Persona[] = []; //Solo puedo hacer un arrays que sean del tipo de dato Persona, es decir un objeto Persona.
```
