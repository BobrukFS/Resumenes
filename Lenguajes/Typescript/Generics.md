# Generics

Los genéricos en TypeScript son una forma de escribir código que puede funcionar con múltiples tipos de datos, en lugar de limitarse a un solo tipo de datos. Los genéricos le permiten escribir funciones, clases e interfaces que toman uno o más parámetros de tipo, que actúan como marcadores de posición para los tipos de datos reales que se usarán cuando se use la función, clase o interfaz.

Un tipo generico se define mediante corchetes angulares `<T>` y se puede utilizar como marcador de posicion para un tipo de datos especifico.  El tipo de datos real se especifica cuando se utiliza la función o clase.

```ts
//Ejemplo en funciones
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>('Hello');
//Ejemplo en clases
class GenericNumber<T> {
  zeroValue: T;
  add: (x: T, y: T) => T;
}

let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function (x, y) {
  return x + y;
};
```

## Generic constraints

Las restricciones genéricas en TypeScript le permiten especificar los requisitos para los parámetros de tipo utilizados en un tipo genérico. Estas restricciones garantizan que el parámetro de tipo utilizado en un tipo genérico cumpla ciertos requisitos.

Las restricciones se especifican mediante la `extends`palabra clave, seguida del tipo que el parámetro de tipo debe extender o implementar.

```ts
interface Lengthwise {
  length: number;
}

function loggingIdentity<T extends Lengthwise>(arg: T): T {
  // Now we know it has a .length property, so no more error
  console.log(arg.length);

  return arg;
}

loggingIdentity(3); // Error, number doesn't have a .length property
loggingIdentity({ length: 10, value: 3 }); // OK
```