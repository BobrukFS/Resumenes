# Modulo Timers

  
El módulo `timers` en Node.js proporciona funciones para programar la ejecución de funciones en un momento futuro. El módulo `timers` es un objeto global, lo que significa que está disponible en todos los módulos de Node.js.

* **setTimeout(funcion, tiempo, argumento, argumento2, ...)** : Es una funcion para ejecutar una funcion con x numeros de argumentos luego de un numero especifico de milisegundos **ms**.
* **setImmediate(funcion, argumento, argumento2, ...)**: Es una funcion que se utiliza para ejecutar codigo asincronico en la proxima interacion del ciclo de eventos. Se ejecuta despues del codigo sincrono pero tiene prioridad entre todos los eventos asincronos que esten pendientes a ejecutarse.
* **setInterval(funcion, milisegundos, argumentos) :** Este **metodo asincronico** es similar a setTimeout(), pero llama a la funcion constantemente. El objeto window tambien ofrece el metodo **clearInterval()** para cancelar el proceso.

```js
//Ejemplo setTimeout
const timers = require('timers'); // Programa la ejecución de una función después de 2 segundos 
timers.setTimeout(() => { 
	console.log('Hola, mundo!'); 
}, 2000);
```