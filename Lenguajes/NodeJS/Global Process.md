# Global Process

Este modulo provee informacion sobre el proceso de Node.JS que se esta ejecutando.

Cada proceso de Node.js tiene un conjunto de funcionalidades integradas que son accesibles a través del módulo Global Process. Este no necesita ser requerido, ya que, literalmente, usa una envoltura alrededor del proceso que se está ejecutando.

El módulo `process` es una herramienta muy poderosa para controlar el flujo de ejecución de una aplicación Node.js
## Eventos

Hay dos eventos integrados que vale la pena mencionar: **exit** y **uncaughtException**.

```js
//Exit
//El evento exit se activa siempre que el proceso esta a punto de salir
process.on('exit', function(){
	fs.writeFileSync('/tmp/myfyle', 'this MUST be saved on exit')
})

//uncaughtException
//Se dispara, siempre que haya ocurrido una excepción que no haya sido detectada o tratada en algún otro lugar de su programa. No es la forma ideal de manejar los errores, pero puede ser útil como última línea de defensa si un programa necesita seguir ejecutándose indefinidamente.

process.on('uncaughtException', function(err){
	console.error('An uncaught error ocurred!');
	console.error(err.stack);
})
//El comportamiento predeterminado de uncaughtException es imprimir un seguimiento de la pila y salir. Utilizando lo anterior, su programa mostrará el mensaje proporcionado y el seguimiento de la pila pero no se cerrará.
```

## Propiedades

El objeto Process también proporciona envoltorios para las tres streams:

- **stdin** es el flujo de entrada estándar. Se utiliza para leer datos del usuario. Por ejemplo, se puede utilizar para leer datos de un teclado o de un archivo.
- **stdout** es el flujo de salida estándar. Se utiliza para escribir datos al usuario. Por ejemplo, se puede utilizar para imprimir datos en la consola o en un archivo. Técnicamente, la mayor parte de la salida en Node.js se logra mediante el uso de process.stdout.write(). Algunos ejemplos son : console.log, console.info, util.puts, util.print.
- **stderr** es el flujo de error estándar. Se utiliza para escribir errores al usuario. Por ejemplo, se puede utilizar para imprimir errores en la consola o en un archivo. Cuando escribe en stderr, su proceso se bloquea hasta que se completa la escritura. Algunos ejemplos son: console.warn, console.error, util.debug.

- **Process.cwd**: devuelve el directorio de trabajo actual del proceso. Este suele ser el directorio desde el que se emitió el comando para iniciar el proceso. 

* **Process.chdir**: se utiliza para cambiar el directorio de trabajo actual.

- **process.argv:** Una matriz de argumentos que se pasaron al proceso cuando se inició.

- **process.pid:** El identificador de proceso del proceso actual.
## Metodos

También hay una variedad de métodos adjuntos al objeto Process:

- **process.on():** Registra un manejador de eventos para un evento de proceso.
- **process.emit():** Emite un evento de proceso.
* **process.nextTick()**: Este método acepta un argumento, una devolución de llamada, y lo coloca en la parte superior de la siguiente iteración del bucle de eventos.
* **process.memoryUsage()**: Este metodo permite saber cual es el uso de la memoria.

```js
const process = require('process');

// Obtiene el identificador del proceso actual
const pid = process.pid;

console.log('El identificador del proceso actual es:', pid);
```