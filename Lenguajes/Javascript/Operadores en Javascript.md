# [[Operadores]] en Javascript
## Operadores aritméticos

```javascript
//1- +(Suma)

let concatenar = "Con" + "Ca" + "Te" + "Nar"; //concatenar

let suma = 5 + 3; //8

//2- -(Resta)

let resta = 5 - 3; //2

//3- *(Multiplicacion)

let multiplicacion = 5 * 3; //15

//4- /(Division)

let division = 5 / 3; //1.66

//5- %(resto). Da el resto de la division de dos numeros. Puede servir para comprobar si un numero es impar o par comprobando el resto de la division del numero x entre 2. Si el resto es 1, es impar, si es 0 es par.

let resto = 5 % 3; //2

//6- ++(Incremento). Este puede ser anterior o posterior.

let incrementoPosterior = 10;
let resultado = incrementoPosterior++ * 2 // Resultado = 20 y incrementoPosterior = 11. Incremento unitario después de operar.

let incrementoAnterior = 10;
let resultado = ++incrementoAnterior * 2 // Resultado = 21 y incrementoPosterior = 11. Incremento unitario después de operar.

//7- -- (Decremento)

let decrementoPosterior = 10;
let resultado = decrementoPosterior-- * 2 // Resultado = 20 y incrementoPosterior = 9. Incremento unitario después de operar.

let decrementoAnterior = 10;
let resultado = ++decrementoAnterior * 2 // Resultado = 18 y incrementoPosterior = 9. Incremento unitario después de operar.

//8- **(Potencia)

let potencia = 3**3 //9
```

## Operadores de comparación

Se compara el operando de la izquierda con el de la derecha. Se utiliza para comparar valores y devuelven true o false.

```javascript
//1- == (Igualdad, realiza conversion de tipo). Utiliza el algoritmo isLooselyEqual

let igualdad = 10 == "10"; //true

//2- != (Desigualdad)

let desigualdad = 10 != "11"; //true

//3- >= (Mayor o igual que)

let mayorIgualQue = 10 >= 10; //true

//4- > (Mayor)

let mayor = 10 > 11; //false

//5- < (Menor)

let menor = 10 < 11; //true

//6- =< (Menor o igual que)

let menorIgualQue  = 10 <= 11; //true

//7- === (Igualdad de valor y tipo de dato). Utiliza el algoritmo isStrictlyEqual

let ejemplo21  = 10 === "10"; //false

//8- !== (Desigualdad de valor o tipo de dato)

let ejemplo22  = 10 !== "10"; //true

//9- instanceof (Determina si un objeto es una instancia de otro objeto)

console.log(auto instanceof Car); //true

//10- in (Determina si un objeto tiene una propiedad determinada)

console.log(marca in auto); //true
```

Para comparar cadenas hay que comparar el primer caracteres de ambas cadenas. Si el primer caracter de la primera cadena es mayor (o menor) que el de la otra cadena, entonces la primera cadena es mayor (o menor) que la segunda, asi sucesivamente. Hay que tener en cuenta que "Z" > "A" es true.

### SameValueZero

- Compara si dos valores son estrictamente iguales, utilizando el algoritmo SameValueZero.

- Es similar al operador de igualdad estricta (`===`) en JavaScript.

- Devuelve `true` si los valores son iguales y `false` si son diferentes.

- No realiza la conversión de tipos antes de realizar la comparación.

- Trata a los valores `NaN` como iguales entre sí.

- No considera a `-0` y `+0` como iguales entre sí.

- Es utilizado en operaciones como `Map`, `Set`, `Array.includes`, `Array.indexOf`, entre otros.

### SameValue

Para ello utilizamos **Object.is(value, value)**.

- Compara si dos valores son iguales, utilizando el algoritmo SameValue.

- Realiza la conversión de tipos antes de realizar la comparación.

- Devuelve `true` si los valores son iguales y `false` si son diferentes.

- Considera a `-0` y `+0` como iguales entre sí.

- Considera a `NaN` como diferente a cualquier otro valor, incluyendo a `NaN` mismo.

## Operadores de asignación

```javascript
let operacion1 = 10;
operacion1++; //11

let operacion2 = 10;
operacion2--; //9

let operacion3 = 10;
operacion3 += 3; //13

let operacion4 = 10;
operacion4 -= 3; //7

let operacion5 = 10;
operacion5 *= 3; //30

let operacion6 = 10;
operacion6 /= 2; //5

let operacion6 = 10;
operacion6 %= 2; //2
```

**Dato**: Si hay algunos cálculos a la derecha del operador =, se realizan antes de que el valor se asigne a la variable a la izquierda del operador.

## Operadores lógicos

```javascript
//1-||(or) Si cualquiera de sus argumentos es true, retorna true, de lo contrario retorna false. 
//Este operador evalua los operandos de izquierda o derecha. Para cada operando, convierte el valor a booleano. 
//Si el resultado es true, se detiene y retorna el valor original de ese operando. Si todos los operandos han sido evaluados (Todos eran false), retorna el ultimo operando.

let ejemplo1 = 8;

if(ejemplo1 < 4 || ejemplo1 % 7 == 0){
    console.log("Se cumple alguna condiciones");
} else{
    console.log("No se cumple ninguna condicion");
}

//2-&&(and) Si ambos operandos son valores verdaderos retorna true, en cualquier otro caso retorna false. 
//Si el resultado es false, se detiene y retorna el valor original de dicho operando. 
//Si todos los operandos fueron valores verdaderos, retorna el ultimo operando.

let ejemplo2 = 8;

if(ejemplo2 < 4 && ejemplo2 % 7 == 0){
    console.log("Se cumplen ambas condiciones");
} else{
    console.log("No se cumple una de las condiciones");
}

//3-!(not)

let ejemplo3 = !true; // false

let ejemplo3 = !0; // true

//Si tengo varios operadores
/*Primero se agrupan todos los and y luego se resuelven los or. Or separa las instrucciones en distintas evaluaciones. And implicitamente agrupa todas las expresiones continuas.*/
```

## Otros operadores

```jsx
//1- Operador ternario condicional. 
//La sintaxis de este operador es: Condición? Valor1 : Valor2;.
//Si la condición es verdadera, el operador tomara el valor 1, de lo contrario tomara el valor 2. No se puede utilizar la palabra clave return dentro de este operador ternario.
// Es el remplazo de if, else. Se puede utilizar multiples operadores ternarios anidados para simular un else if.

return a > b ? "A es mayor que B" : "B es mayor que A";

let ejemplo1 = 8;
ejemplo1 > 10? ejemplo1 = "Es mayor que 10" : ejemplo1 = "Es menor que 10"; //Es menor que 10

//Podemos tener multiples operadores ternarios. Es importante indentarlo bien para la mejor lectura.

function checkSign(num) {
  return num > 0 ? "positive" 
  : (num < 0 ? "negative" : "zero");
}

//Es equivalente a

function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}

//2- Operador typeof.
//Nos permite ver que tipo de dato esta almacenado en una variable.

let ejemplo2 = "Hola";
typeof ejemplo2; //string

//3- Operador Nullish coalescing
// Este operador se escribe con un doble signo de cierre de interrogación ??.  Devuelve el primer argumento cuando este no es null ni undefined. En caso contrario, devuelve el segundo. Sirve para evaluar si una variable o expresion es nula o indefinida.

let a = undefined;
let b = 5
a ?? b; //b

```

**Dato**: Si realizamos una operacion matematica con una variable undefined y un numero, el resultado sera NaN (Not a Number). Si realizamos una concatenacion con una variable undefined y un string, obtendremos undefined.

### Operador coma

El operador coma **,** evalua cada uno de sus operandos (de izquierda a derecha) y devuelve el valor del ultimo operando. Esto permite crear una expresion compuesta en la que se evaluan varias expresiones, siendo el valor final de la expresion compuesta el valor de la expresion mas a la derecha de sus miembros. Debido a que todas las expresiones excepto la última se evalúan y luego se descartan, estas expresiones deben tener efectos secundarios para ser útiles. Las expresiones comunes que tienen efectos secundarios son asignaciones, llamadas a funciones y operadores ++ y --.

```js
let a, b, c;
a = b = 3, c = 4; // Returns 4
console.log(a); // 3 (left-most)

let x, y, z;
x = (y = 5, z = 6); // Returns 6
console.log(x); // 6 (right-most)

//Usando el operador coma en un bucle for

const a = Array.from({ length: 10 }, () =>
  Array.from({ length: 10 }, Math.random),
); // A 10×10 array of random numbers

for (let i = 0, j = 9; i <= 9; i++, j--) {
  console.log(`a[${i}][${j}] = ${a[i][j]}`);
}//Incrementa i y decrementa j a la vez, imprimiendo asi los valores de los elementos diagonales de la matriz.

```

El operador "," se usa comunmente para proporcionar multiples actualizaciones a la ocurrencia tardia de un bucle for.

Otro ejemplo que se podria hacer con el operador coma es procesar antes de devolver.

```js
function myFunc() {
  let x = 0;

  return (x += 1, x); // the same as return ++x;
}

//Es util especialmente para funciones flecha de una linea

let sum = 0;
const squares = [1, 2, 3, 4, 5].map((x) => ((sum += x), x * x));
console.log(squares); // [1, 4, 9, 16, 25]
console.log(sum); // 15

```


## Precedencia de operadores

**Operadores unarios >Operadores aritméticos > Operadores relacionales > Operadores lógicos > Operador coma** 

Dentro de los operadores lógicos el orden en el cual los operadores son evaluados:

**Not > And > Or**

Se puede utilizar **paréntesis** para indicar mayor precedencia.


