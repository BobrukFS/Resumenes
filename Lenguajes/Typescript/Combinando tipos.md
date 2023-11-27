# Combinando tipos

## Tipo union

Un tipo de unión **|** es un tipo formado a partir de dos o más tipos diferentes, que representan valores que pueden ser _cualquiera_ de esos tipos. _Nos referimos a cada uno de estos tipos como miembros_ de la union .

```ts
type stringOrNumber = string | number;
let value: stringOrNumber = 'hello';

value = 42;

//Otro ejemplo

type a = {
    number: number,
    string: string
}

type b ={
    boleean : boolean
}

type c = a | b;

let d: c = {
    number : 23,
    string : "exe",
    boleean: true, //No es obligatorio que esten los dos tipos, puede estar uno u el otro, o ambos
  };
```

TypeScript solo permitirá una operación si es válida para _todos_ los miembros del sindicato. Por ejemplo, si tiene la unión `string | number`, no puede usar métodos que solo estén disponibles en `string`. La solución es _limitar_ la unión con el código, igual que lo haría en JavaScript sin anotaciones de tipo. _La limitación_ ocurre cuando TypeScript puede deducir un tipo más específico para un valor basado en la estructura del código.

```ts
function printId(id: number | string) {
	if (typeof id === "string") {
		// In this branch, id is of type 'string'
		console.log(id.toUpperCase());

	} else {
		// Here, id is of type 'number'
		console.log(id);
	}
}
```

### keyof operator

El operador **keyof** se utiliza para obtener la union de las claves de un tipo de objeto.

```ts
interface User {
  name: string;
  age: number;
  location: string;
}

type UserKeys = keyof User; // "name" | "age" | "location"
const key: UserKeys = 'name';
```
## Tipo interseccion

El operador de intersección **&** se utiliza para intersectar dos o más tipos en un solo tipo que representa las propiedades de todos los tipos.

```ts
//Ejemplo 1
interface A {
  a: string;
}

interface B {
  b: number;
}

type AB = A & B;
let value: AB = { a: 'hello', b: 42 };

//Ejemplo 2

type a = {
    number: number,
    string: string
}

type b ={
    boleean : boolean
}

type c = a & b;

let d: c = {
    number : 23,
    string : "exe",
    boleean: true,
  };
```

