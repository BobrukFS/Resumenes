# [[Call Stack]] en Javascript

## ¿Como funciona?
El motor de Javascript va a estar leyendo el codigo de nuestro programa y cada vez que se encuentra con el llamado a una funcion va a crear un registro o frame con informacion asociada a esta funcion (ambito lexico, nombre del archivo que pertenece, la funcion y el numero de la proxima linea a ejecutar) y lo va agregar a la **pila de llamadas**.

## Ejemplo
En este ejemplo podemos ver la pila de llamadas, donde tenemos (Anonymous) y hacerEnsaladaMixta. Podemos ver que tenemos un registro donde vemos el nombre del archivo y la próxima línea a ejecutar (ensalada_mixta.js:17), tenemos el contexto de ejecución (scope).

![[Pasted image 20221104160003.png]]

Cualquier función o funciones que sean llamadas por esa función son añadidas arriba de la pila de llamadas y serán ejecutadas cuando su llamada sea alcanzada. Cuando la función actual termina, el intérprete la elimina de la pila y reanuda la ejecución donde se quedó. Si la pila necesita más espacio del que se le asignó, se producirá un error de **"desbordamiento de pila"**. El motor de JS puede ejecutar una sola cosa a la vez. 

![[Pasted image 20221104160154.png]]

Cuando ejecutamos un programa en JS la primera función que se agrega a la pila es una **función anónima**(Anonymous)  que engloba a todo el programa, es como si fuera el hilo principal del programa, cuando esa función salga de la pila significa que termino la ejecución del programa principal.

**Dato:** En la devtool entramos a la pestaña Source, vamos a la sección de snippets y creamos un snippets. Podemos poner un breakpoint es una señal stop, la ejecución del programa se va a detener en esa línea.

**Dato**: La secuencia de llamadas que se fueron dando en la ejecución de un programa hasta que sucedió un error se llama **Stacktrace**.