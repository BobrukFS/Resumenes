# Recursion

Una funcion que se llama a si misma es llamada **recursiva**. Una funcion se puede llamar a si misma siempre y cuando no lo haga tantas veces que desborde la pila. Es utilizada esta forma para resolver problemas que contienen subproblemas mas pequeños. Evita tener que utilizar ciclos.

Las funciones recursivas deben tener un **caso base** asi cuando son llamadas devuelven un valor y finaliza la recursion, en caso que no tengan un caso base la recursividad seria infinita y nunca terminaria de ejecutarse.

La recursividad puede dar un código más corto, más fácil de entender y soportar. No se requieren optimizaciones en todos los lugares, principalmente necesitamos un buen código, por eso se usa.

```javascript
//Ejemplo 1 : Comenzando con el número 1 y sumando repetidamente 5 o multiplicando por 3, se puede producir un conjunto infinito de números. ¿Cómo escribirías una función que, dado un número, trate de encontrar una secuencia de tales sumas y multiplicaciones que produzca ese número?

function encontrarSolucion(objetivo) {
     function encontrar(actual, historia) {
          if (actual == objetivo) {
               return historia;
          } else if (actual > objetivo) {
               return null;
          } else {
               return encontrar(actual + 5, `(${historia} + 5)`) ||
                    encontrar(actual * 3, `(${historia} * 3)`);
          }
     }
     return encontrar(1, "1");
 }

 console.log(encontrarSolucion(19)); // → ((((1 * 3) * 3) + 5) + 5)


//1º se ejecuta la funcion encontrar solucion con un objetivo de 19 y retorna la funcion encontrar con argumentos 1 y "1".
//2º al 1 no ser igual a 19, ni ser mayor, la funcion encontrar retorna a la funcion encontrar con distintos argumentos, actual (1) + 5 e historia("1") + 5 ò
//actual(1) * 3 e historia("1") * 3.
//3º retornara dichas funciones hasta que actual == objetivo o actual > objetivo.
```

```javascript
//Ejemplo 2

function potencia(base, exponente) {
    if (exponente == 0) {
        return 1;
    } else {
        return base * potencia(base, exponente - 1);
    }

}

console.log(potencia(2, 3)); // → 8

//1º se ejecuta la funcion potencia(2,3). Al no ser el exponente igual a 0, se retorna la base * potencia(2, 3 - 1).
//2º al volverse a llamar la funcion potencia y el exponente de esta no ser igual a 0, se vuelve a retornar base * potencia(base, 2 - 1).
//3º al volverse a llamar la funcion potencia y el exponente de esta no ser igual a 0, se vuelve a retornar base * potencia(base, 1 - 1).
//4º al volverse a llamar la funcion potencia, el exponente es igual a 0 por lo que se retorna uno.
//5º El acumulado quedaria base * base * base * 1.

//La funcion anterior es equivalente a:

let base1 = 2

let resultado = base1

for (let exponente1 = 3; exponente1 > 1; exponente1--) {
    resultado *= base1;
}

console.log(resultado); // → 8
```

El número máximo de llamadas anidadas (incluida la primera) se denomina profundidad de recursión. La profundidad de recursion maxima esta limitada por el motor JS pero puede que sea 10000.

**Dato**: Cualquier recursión puede reescribirse como un bucle. La variante de bucle generalmente se puede hacer más eficaz debido a que al llamar a una funcion se crea un contexto de funcion en la memoria, por lo que n llamadas a funciones necesita n contextos..