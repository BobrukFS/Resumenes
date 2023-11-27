# Interfaces en Typescript

Las interfaces en TypeScript proporcionan una forma de definir un contrato para un tipo, que incluye un conjunto de propiedades, métodos y eventos. Se utiliza para imponer una estructura para un argumento de objeto, clase o función. Las interfaces no se transpilan a JavaScript y TypeScript solo las utiliza en tiempo de compilación para fines de verificación de tipo. Siempre los nombres de las interfaces es en Pascal case.

```ts
interface User {
  readonly name: string; //Solo de lectura, es decir no modificable pero a tiempo de ejecucion si, si quiero que sea inmutable uso object.Freeze
  age?: number; //Opcional
}

interface Alumnos {
	totalAlumnos : (User[] | number),
}

const user: User = {
  name: 'John Doe',
  age: 30,
};
```

TypeScript no tiene en cuenta si las propiedades de dos tipos son `readonly`al comprobar si esos tipos son compatibles, por lo que las propiedades `readonly` también pueden cambiar mediante alias.

```ts
interface Person {
	name: string;
	age: number;

}
interface ReadonlyPerson {
	readonly name: string;
	readonly age: number;
}

let writablePerson: Person = {
	name: "Person McPersonface",
	age: 42,
};

// works
let readonlyPerson: ReadonlyPerson = writablePerson;
console.log(readonlyPerson.age); // prints '42'
writablePerson.age++;
console.log(readonlyPerson.age); // prints '43'
```

**Dato**: Usando modificadores de mapeo , puedes eliminar `readonly`atributos.
## Extendiendo interface

En TypeScript, puede ampliar una interfaz creando una nueva interfaz que herede de la interfaz original utilizando la palabra clave "extiende". La nueva interfaz puede incluir propiedades y métodos adicionales o redefinir los miembros de la interfaz original

```ts
interface Shape {
  width: number;
  height: number;
  getWidth() : number;
}

interface Square extends Shape {
  sideLength: number;
}

let square: Square = {
  width: 10,
  height: 10,
  sideLength: 10,
};
```

## Diferencias entre interface y types

1.  La sintaxis difiere para describir la forma de un objeto o la firma de funciones
2.  A diferencia de una interface, el type se puede utilizar para otros tipos, como primitivas, uniones y tuplas.
3. La sintaxis al extender difiere.

![[Pasted image 20231108123143.png]]

4. En la interface se pueden agregar nuevos campos a una interface existente mientras que en un tipo no se puede cambiar despues de haber sido creado.

![[Pasted image 20231108123221.png]]

5. Una clase puede implementar una interfaz o un alias de tipo, ambos exactamente de la misma manera. Sin embargo, tenga en cuenta que una clase y una interfaz se consideran planos estáticos. Por lo tanto, no pueden implementar/extender un alias de tipo que nombre un tipo de unión.