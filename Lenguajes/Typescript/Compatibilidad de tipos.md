# Compatibilidad de tipos

TypeScript utiliza tipificación estructural para determinar la compatibilidad de tipos. Esto significa que dos tipos se consideran compatibles si tienen la misma estructura, independientemente de sus nombres. Solo se tienen en cuenta los miembros del tipo de destino al comprobar la compatibilidad. 

```ts
interface Point {
    x: number;
    y:number;
}
let p1 : Point = {x: 10, y:20};
let p2: {x: number, y: number} = p1;
console.log(p2.x)//10

//Otro ejemplo, en este caso daria error en Java, pero en typescript no, porque utiliza tipificacion estructural, es decir tienen la misma estructura (numero de miembros y mismos tipos).

interface Pet {
	name: string;
	age? : number; //al ser opcional no afecta
}
class Dog {
	name: string;
}

let pet: Pet;
pet = new Dog();

//Ejemplo 3

interface Pet {
	name: string;
	age : number; 
}
class Dog {
	name: string;
}

let pet: Pet;
pet = new Dog(); //Error

//Pero si hacemos esto no da error

interface Pet {
	name: string;
 
}
class Dog {
	name: string;
		age : number;
}

let pet: Pet;
pet = new Dog(); //OK
pet = new Dog(name: "Lassie", age: 11); //Error

```

## Comparando dos funciones

```ts
let x = (a: number) => 0;
let y = (b: number, s: string) => 0;
y = x; // OK
x = y; // Error
```

## Comparando clases

Las clases funcionan de manera similar a los tipos literales de objetos y las interfaces con una excepción: tienen un tipo estático y uno de instancia. Al comparar dos objetos de un tipo de clase, solo se comparan los miembros de la instancia. Los miembros estáticos y los constructores no afectan la compatibilidad.

```ts
class Animal {
	feet: number;
	constructor(name: string, numFeet: number) {}
}

class Size {
	feet: number;
	constructor(numFeet: number) {}
}

let a: Animal;
let s: Size;
a = s; // OK
s = a; // OK
```

