# Clases en Typescript

```ts
class Animal {
  readonly name: string;
  constructor(private name: string) {
    this.name = name;
  }

  makeSound(): void {
    console.log(`${this.name} is making a sound`);
  }
}

const dog = new Animal('Dog');
dog.makeSound(); // Output: Dog is making a sound
```

## Modificadores de acceso

En TypeScript, los parámetros del constructor se pueden declarar con modificadores de acceso (por ejemplo `public`, `private`, `protected`) y/o anotaciones de tipo. Luego, los parámetros se asignan automáticamente a propiedades del mismo nombre dentro del constructor y se puede acceder a ellos dentro de la clase. Por ejemplo:

En TypeScript, los modificadores de acceso son palabras clave que se utilizan para controlar la visibilidad y accesibilidad de las propiedades y métodos de la clase. Hay tres modificadores de acceso en TypeScript:

- `public:`Este es el modificador de acceso predeterminado. Se puede acceder a las propiedades y métodos declarados como públicos desde cualquier lugar, tanto dentro como fuera de la clase.
- `private:`Solo se puede acceder a las propiedades y métodos declarados como privados dentro de la misma clase. No son accesibles desde fuera de la clase.
- `protected:`Se puede acceder a las propiedades y métodos declarados como protegidos dentro de la clase y sus subclases. 
## Sobrecarga de constructores

En TypeScript, puede lograr la sobrecarga del constructor utilizando múltiples definiciones de constructor con diferentes listas de parámetros en una sola clase.

```ts
class Point {
  // Overloads
  constructor(x: number, y: string);
  constructor(s: string);
  constructor(xs: any, y?: any) {
    // TBD
  }
}
```

## Clases abstractas

Las clases abstractas en TypeScript son clases de las que no se pueden crear instancias por sí solas y deben ser subclasificadas por otras clases para asi poder instanciar dichas subclases. Las clases abstractas proporcionan un modelo para otras clases y pueden tener métodos abstractos, que son métodos sin cuerpo y deben ser anulados por la subclase. Estas clases son útiles para definir una interfaz común o una funcionalidad básica que otras clases pueden heredar y desarrollar.

```
abstract class Animal {
  abstract makeSound(): void;

  move(): void {
    console.log('moving...');
  }
}

class Dog extends Animal {
  makeSound(): void {
    console.log('bark');
  }
}
```
## Herencia y polimorfismo

En TypeScript, la herencia se logra utilizando la palabra clave extends.

El polimorfismo se refiere a la capacidad de un objeto de adoptar muchas formas. Esto permite que los objetos de diferentes clases sean tratados como objetos de una clase común, siempre que compartan una interfaz común o una jerarquía de herencia. En TypeScript, el polimorfismo se logra mediante la anulación y sobrecarga de métodos.

```ts
class Animal {
  makeSound(): void {
    console.log('Making animal sound');
  }
}

class Dog extends Animal {
  makeSound(): void {
    console.log('Bark');
  }
}

class Cat extends Animal {
  makeSound(): void {
    console.log('Meow');
  }
}

let animal: Animal;

animal = new Dog();
animal.makeSound(); // Output: Bark

animal = new Cat();
animal.makeSound(); // Output: Meow
```

## Clases que implementan interfaces

Una clase puede implementar una interface mediante la palabra clave **implements**

```ts
interface Avenger {
	name: string
	powerScore: number,
	wonBattles: number,
	age: number
}

class AvengerHero implements Avenger{
	constructor(name: string, powerScore:number){
		this.name = name,
		this.powerScore = powerScore
	}
}
```
## Getters and setters

Las clases tambien pueden tener accesores. Si `get`existe pero no `set`, la propiedad es automáticamente`readonly`