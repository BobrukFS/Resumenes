# Objeto Math

Algunos objetos en JS no tienen la funcion de almacenar valores, si no la de proveer propiedades y metodos para procesar valores de otros objetos. Este es el caso del objeto **Math**. Este objeto no incluye un constructor para crear mas objetos, pero define varias propiedades y metodos a los que podemos acceder desde su definicion para obtener los valores de constantes matematicas y realizar operaciones aritmeticas.

```javascript
var numeroalazar = Math.random() * (11 - 1) + 1;
numeroalazar = Math.round(numeroalazar);
console.log(numeroalazar);

// Genera un numero aleatorio dentro de un rango
function randomRange(myMin, myMax) {
  return Math.floor(Math.random() * (myMax - myMin + 1 ) + myMin);

}
```

* **Math.random()** : Genera un numero aleatorio entre 0 y 1.

* **Math.floor()** : Redondea un numero con decimales hacia abajo.
* **Math.sqrt()**: Retorna la raiz cuadrada de un numero.
* **Math.min(valor1, valor2,)** : Devuelve el menor de cero o mas valores.