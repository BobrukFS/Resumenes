# Type guards - Narrowing

Las protecciones de tipo son una forma de limitar el tipo de una variable. Esto es util cuando quieres hacer algo diferente dependiendo del tipo de variable.

Los type guards se pueden utilizar en una variedad de situaciones, como:

- Para verificar el tipo de una variable o expresión antes de utilizarla.
- Para restringir el tipo de una variable o expresión a un valor específico.
- Para controlar el flujo de ejecución del código en función del tipo de una variable o expresión

Existen varios tipos de type guards en TypeScript, incluyendo:

- **Operadores de comprobación de tipo**, como `typeof (para tipos)`, `instanceof (para instancias)` y `in`.
- **Expresiones regulares**.
- **Funciones de tipo guard o predicados de tipo**.

**Dato**: Se suelen utilizar operadores logicos y de comparacion, ademas de estructuras condicionales y switch.

**Dato**: Si por ejemplo tengo dos instancias con la propiedad nombre y el mismo tipo, no da porlbemas, solo da problema en las que difiere.

```ts
//Operados de comprobacion de tipo
function padLeft(padding: number | string, input: string) {
	if (typeof padding === "number") {
		return " ".repeat(padding) + input;
	}
	return padding + input;
}
//Functions de tipo guard.

function isGreaterThan10(x: number): boolean {
  return x > 10;
}
let x: number;
x = 11;
if (isGreaterThan10(x)) {
  console.log("x es mayor que 10");
}
//Ejemplo completo
//type guard
function isString(value: unknown): value is string { //is lo que hace es verificar si value es string
  return typeof value === 'string';
}

function example(x: unknown) {
  if (isString(x)) {
    // We can now call any 'string' method on 'x'.
    x.toUpperCase();
  } else {
    console.log(x);
  }
}
```

**Dato**: Los typeguard habria que evitarlos porque son muy verbosos.