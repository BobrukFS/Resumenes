# Type Aliases

**Type** como enum nos permiten crear tipos de datos personalizados. Los type permiten definir un alias para un tipo existente o para una combinacion de tipos existentes. Siempre los nombres de los tipos es en Pascal case.

```ts
//Ejemplo

enum Talla {Chica = "s", Mediana = "m", Grande = "l", Extragrande = "xl"} // Creamos un conjunto de valores constantes con nombres asociados.

let chicos: Talla[] = [Talla.Chica, Talla.Mediana]

type Direccion = { //Creamos el tipo de dato personalizado Direccion.
    numero: number,
    calle: string,
    pais?: string,//opcional
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

//Otro ejemplo con id, podemos especificar que tipo de cadena de texot queremos

type HeroId = `${string}-${string}-${string}-${string}-${string}`
```

## Type indexing

El tipo de indexación en TypeScript es una característica que permite especificar el tipo de los elementos que se pueden acceder a través de una propiedad indexada. Esto es útil para garantizar que se acceda a los valores correctos y para evitar errores en tiempo de ejecución.

```ts
type Persona = {
    id : number,
    nombre: string,
    talla : number,
    direccion : {
        numero : number,
        calle : string,
        pais : string,
    }
}

const direccionPersona: Persona["direccion"] ={ 
	
}
```
## Type from value

Con el typeof podemos extraer el tipo de objetos, variables, y funciones. Podemos crear tipos a partir de codigo que ya tengamos.

```ts
const direccion = {
        numero : 2366,
	calle : "dr arturo illia",
	pais : "Argentina"
    }
    
type Address = typeof direccion;

const direccionArgentina :Address ={
  numero : 23,
  calle : "hola",
  pais : "argentina"
}

//Ejemplo pero con funciones

function createAddress(){
	return {
		planet : "Tierra",
		city : "Barcelona"
	}
}

type Address = ReturnType<typeof createAddress>

```

Con `ReturnType<typeof funcion>` podemos obtener el tipo de retorno de una función. Esto es útil para comprobar el tipo de valor que se va a devolver por una función, o para crear tipos personalizados que representen el valor de retorno de una función.
## Extendiendo un type

```ts
type Animal = {
	raza : string,
}

type Bear = Animal & {
	color : string,
}

const osito : Bear = {
	raza : "Pardo",
	color : "Marron",
}
```