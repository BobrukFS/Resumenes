# Variables en Javascript

Las [[Variables]] se **declaran** (se declara el alcance de la variable) con la palabra clave **~~var~~**, **let**, o **const**, seguido del nombre de la variable y el carácter **=** y seguido del valor inicial para poder **inicializarla**. Nosotros **podemos reasignar su valor** todas las veces que queramos.

```javascript
let variable = "Hola mundo";
```

Después de que una variable haya sido definida, su nombre puede usarse como una **expresión** (fragmento de código que produce un valor). El valor de tal expresión es el valor que la variable mantiene actualmente pudiendo ser modificado con el operador =.

```javascript
let variable = 500;//La variable es 500.
variable = 1000;//La variable es 1000.

let variable1 = variable + 500//La variable1 es 1500.
```

Se puede asignar como valor de una variable otra variable:

```js
let a = 5; //5
let b = 5; //5
```

Para declarar multiples variables- 

```javascript
let var1 = 5, var2 = 10;
```

**Dato**: A las variables se les puede asignar tambien una condicion para que se guarde en ellas.

## ¿Diferencia entre let y const?

**Let** nos permite inicializar una variable sin valor y nos permite reasignar un valor a una variable. Se suele utilizar para variables que pueden ser modificadas en un futuro.

**Const** no permite inicializar una variable sin valor y no nos permite reasignar a un valor a una variable, es decir que la variable que declaremos con const será constante. Se suele utilizar para clases y objetos. Es una **variable de solo lectura**. Sin embargo si una constante es un objeto o una matriz, sus propiedades o elementos se pueden actualizar o eliminar.

```js
let variable = "Hola"; // Hola
variable = "chau"; //chau

const variable2 = "Hola"; // Hola
variable2 = "chau"; // Error

let variable; //undefined
variable = 2; //2

const variable2 //error
```

**Dato**: Javascript solo guarda las variables que seran utilizadas en la funcion.
## Formas de escribir una variable

```javascript
nombre_producto //Underscore.
nombreProducto //Canelcase, es la que mas se utiliza.
NombreProducto//Pascalcase.
array_push //snake_casing, es tambien muy utilizada
```

Los nombres de una variable no pueden ser palabras reservadas, tampoco con caracteres(excepto $ y _ ) ni números.

Las variables deben tener nombres descriptivos pero no demasiado largo. Debe ser preciso.

**Dato**: Es común que los desarrolladores usen identificadores de variables en mayúsculas para valores inmutables (constantes) y minúsculas o camelCase para valores mutables (objetos y matrices).

**Dato**: Todas las variables que empiecen con $ hacen referencia a un elemento del DOM.

[[Scopes en javascript]]
[[Hoisting]]
