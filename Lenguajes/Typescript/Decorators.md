# Decorators

Los decoradores son una característica de TypeScript que le permite modificar el comportamiento de una clase, propiedad, método o parámetro. Son una forma de agregar funcionalidad adicional al código existente y se pueden usar para una amplia gama de tareas, incluido el registro, la optimización del rendimiento y la validación. Para utilizarlo antes en el tsconfig.json debemos poner

```json
{
    "compilerOptions": {
      "target": "ES5",
      "experimentalDecorators": true
    }
  }
```

Y ademas en la terminal

```npm
tsc --target ES5 --experimentalDecorators
```

```ts
// Definición del decorador `log()`
function log(
  target: Object,
  propertyKey: string | symbol,
  descriptor: PropertyDescriptor
) {
  // Captura el valor original del método `add()`
  const originalMethod = descriptor.value;

  // Redirige el método `add()` para que registre las llamadas
  descriptor.value = function (...args: any[]) {
    console.log(`Calling ${propertyKey} with arguments: ${args}`);
    return originalMethod.apply(this, args);
  };

  // Devuelve el descriptor modificado
  return descriptor;
}

// Definición de la clase `Calculator`
class Calculator {
  // Aplica el decorador `log()` al método `add()`
  @log
  add(a: number, b: number): number {
    // Devuelve la suma de los dos números
    return a + b;
  }
}

// Instanciación de una nueva calculadora
const calculator = new Calculator();

// Llama al método `add()`
calculator.add(1, 2);

```