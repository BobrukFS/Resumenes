# Promises

Las promesas son una forma mucho mejor de trabajar con código asincrónico en JavaScript que el antiguo enfoque de devolución de llamada propenso a errores. Usando promesas, podemos administrar código asincrónico extremadamente complejo con una configuración rigurosa de manejo de errores, escribir código en un estilo más o menos sincrónico y evitar encontrarnos con el llamado infierno de devolución de llamadas.

**Una promesa** es un objeto JavaScript que representa el resultado de una operación asíncrona. Las operaciones asíncronas son aquellas que tardan un tiempo en completarse, y que pueden ejecutarse en segundo plano sin bloquear la interfaz de usuario.

**El código de producción** es el código que realiza la operación asíncrona. Este código puede ser una función que realiza una solicitud HTTP, una función que accede a una base de datos, o cualquier otra función que tarde un tiempo en completarse.

**El código de consumo** es el código que usa el resultado de la operación asíncrona. Este código puede ser una función que muestra el resultado en la interfaz de usuario, o una función que almacena el resultado en una variable.

La sintaxis del constructor para un objeto promesa es:   

![[Pasted image 20230121220829.png]]
**Para crear una promesa**, utilizamos el constructor `Promise()`. El constructor `Promise()` acepta una función como argumento, que se denomina `ejecutor`. La función `ejecutor` es responsable de establecer el estado de la promesa. Cuando se crea **new Promise**, el ejecutor corre automaticamente. 

Sus argumentos **resolve** y **reject** son devoluciones de llamada proporcionadas por el propio Javascript. Cuando el ejecutar obtiene el resultado, debe llamar a uno de estos callbacks.

* **resolve(value) :**  Representa la terminacion de una operación asincrona, con resultado **value**.

* **reject (error) :** Representa el fracaso de una operación asincrona.

Entonces en resumen, el ejecutor se ejecuta automaticamente e intenta realizar un trabajo. Cuando termina con el intento, llama resolve si fue exitoso o reject si hubo un error.

El objeto promise devuelto por el constructor new Promise tiene estas propiedades internas:

* **state :** inicialmente **“pending”,** luego cambia a “**fulfilled”** cuando resolve se llama o **“rejected”** cuando reject se llama.

* **result :** inicialmente undefined, luego cambia a value cuando se llama resolve(value) o error cuando reject(error) se llama.

Ejemplo:

![[Pasted image 20230121220845.png]]
Entonces, el ejecutor eventualmente se mueve a uno de estos dos estados

![[Pasted image 20230121220856.png]]
Solo puede haber un unico resultado o un error, es decir se tendra en cuenta el primer resolve o reject. El ejecutor debe llamar solo un resolve o un reject. Cualquier cambio de estado es definitivo.

Se recomienda usar el objeto Error como argumento de reject.

Un objeto Promise sirve como enlace entre el ejecutor (el codigo productor) y **las funciones consumidoras, que recibiran el resultado o el error**. Las funciones de consumo se pueden registrar utilizando los metodos de promesa **.then**, **.catch** y **.finally.**
### Then

El metodo **then()** retorna una promise, y se ejecuta dependiendo si la promesa se marca como resolve o reject.

La sintaxis es then(functionResolve, functionReject).

![[Pasted image 20230121220914.png]]
El primer argumento de .then es una funcion que se ejecuta cuando se resuelve la promesa y recibe el resultado.

El segundo argumento de .then es una funcion que se ejecuta cuando se rechaza la promesa y recibe el error.

Si solo nos interesan las finalizaciones exitosas, entonces podemos proporcionar solo un argumento de funcion para .then. En cambio podemos utilizar el segundo argumento de then para manejar los errores aunque eso tambien lo podemos realizar con catch que es el que comunmente se utiliza ya que permite un manejo mas global de errores en toda la cadena de promesas.
### Catch

El método **catch()** retorna una Promise y solo se ejecuta en los casos en los que la promesa se marca como Reject.

Si solo nos interesan los errores, podemos usar null como primer argumento, es decir .then(null, errorHandlingFunction). O podemos usar .catch(errorHandlingFuncion), que es exactamente lo mismo.

![[Pasted image 20230121220933.png]]
Tambien sirve para controlar los errores en conjunto con .then, ejemplo:

![[Pasted image 20230121220942.png]]
**Dato:** La llamada **.catch(f)** es un analogo completo de **.then(null,f)**
### Finally

La llamada **.finally(f)** es similar a **.then(f, f)** en el sentido de que f siempre se ejecuta cuando se termina la promesa, ya sea reject o resolve.

Un controlador finally no tiene argumentos. En finally no sabemos si la promesa tiene éxito o no. Está bien, ya que nuestra tarea suele ser realizar procedimientos de finalización "generales".

Un controlador finally pasa los resultados y los errores al siguiente controlador, aca tenemos un ejemplo de como lo pasa a then:

![[Pasted image 20230121220954.png]]
**¿Para que se utilizan las promesas?**

Por ejemplo, tu usas promesas comunmente para hacer peticiones HTTP, las cuales tu sabes que van a funcionar por que tienes un compañero en el trabajo que se encargo de esto o tu mismo lo hiciste pero puede suceder que falle y necesitas manejar ese error por que si no tu aplicación se rompe.

## Encadenamiento de promesas
Para esto cada llamada a .then devuelve una promise, de modo que podemos llamar al siguiente .then,

![[Pasted image 20230121221030.png]]
### Devolviendo promesas

Un .then puede crear y devolver una promesa (Es un objeto con los mismos metodos que una promesa pero no es una promesa). En ese caso, los controladores adicionales esperan hasta que se asiente y luego obtienen su resultado.

Devolver promesas nos permite construir cadenas de acciones asincrónicas.
![[Pasted image 20230121221042.png]]
## Manejo de errores con promises
Las cadenas de promesas son excelentes para el manejo de errores. Cuando se rechaza una promesa, el control salta al controlador de rechazo más cercano. La forma más fácil de detectar todos los errores es agregar .catch al final de la cadena ya que si alguna de las promesas anteriores se rechaza, entonces lo detectaria. Podemos tener tantos manejadores .then como queramos y luego usar uno solo .catch al final para manejar los errores en todos ellos.

### Try…catch implicito

El codigo de un ejecutor de promesas y de los controladores de promesas tienen un invisible try…catch a su alrededor. Si ocurre una excepcion se detecta y se trata como un rechazo.

Ejemplo:

![[Pasted image 20230121221227.png]]
Esto sucede no solo en la función ejecutora, sino también en sus controladores.

Ejemplo:

![[Pasted image 20230121221238.png]]
### Rethrowing

Al igual que en try…catch podemos analizar el error y volver a lanzarlo si no podemos manejarlo.

Si lo arrojamos dentro de.catch el error, entonces el control va al siguiente controlador de errores más cercano. Y si manejamos el error y terminamos normalmente, continúa con el siguiente controlador .then exitoso más cercano.

![[Pasted image 20230121221249.png]]
Si no manejamos los errores, el codigo muere, por ende siempre hay que tenerlos manejados. En cualquier caso, deberíamos tener el unhandledrejection controlador de eventos (para navegadores y análogos para otros entornos) para rastrear errores no manejados e informar al usuario (y probablemente a nuestro servidor) sobre ellos, para que nuestra aplicación nunca “muera”.

Si se produce un error, y no hay un .catch, se dispara unhandledrejection, y se obtiene el objeto event el cual contiene información sobre el error, por lo que podemos hacer algo con el error (manejar el error).
## Metodos para promises

Hay 6 metodos estaticos en la clase Promise :

* **Promise.all**

Sirve por ejemplo para que muchas promesas se ejecuten en paralelo  y esperar hasta que todas ellas esten listas.

La sintaxis es:

![[Pasted image 20230121221312.png]]
Promise.all toma un iterable (usualmente un array de promesas) y devuelve una nueva promesa. Esta nueva promesa es resuelta en cuanto todas las promesas listadas se resuelven, y el array de aquellos resultados se vuelve su resultado. El orden de los miembros del array es el mismo que el de las promesas que los originan.

* **Promise.reject**

El método Promise.reject(reason) retorna un objeto Promise que es rechazado por la razón específicada.

* **Promise.resolve**

El método Promise.resolve(value) retorna un objeto Promise que es resuelto con el valor dado.
## Promisificacion
La promisificacion es la conversion de una funcion que acepta un callback a una funcion que devuelve una promesa. Así que la promisificación está solo pensada para funciones que llaman al callback una vez. Las llamadas adicionales serán ignoradas.
## Microtareas
Los controladores de promesas .then/ .catch/ .finall y siempre son asincrónicos.

### Cola de microtareas

·         La cola es primero en entrar, primero en salir: las tareas que se ponen en cola primero se ejecutan primero.

·         La ejecución de una tarea se inicia solo cuando no se está ejecutando nada más.

Cuando una promesa está lista, sus . controladores then/catch/finally se ponen en cola; aún no se ejecutan. Cuando el motor de JavaScript se libera del código actual, toma una tarea de la cola y la ejecuta.

Si necesitamos garantizar que un fragmento de código se ejecute después .de then/catch/finally , podemos agregarlo a una llamada .then encadenada.

Los controladores de promesa siempre pasan por esta cola interna.

Si hay una cadena con múltiples .then/catch/finally, cada uno de ellos se ejecuta de forma asíncrona. Es decir, primero se pone en cola, luego se ejecuta cuando el código actual está completo y los controladores previamente en cola han terminado.
## Async/await

`async/await`es una sintaxis especial para trabajar con promesas de una manera más cómoda. Usamos `async`una palabra clave para declarar una función asíncrona que devuelve una Promesa, y la `await`palabra clave hace que una función espere una Promesa.
### Async

Tenemos la palabra clave async que puede ser ubicada delante de una funcion:

![[Pasted image 20230121221627.png]]

La palabra async ante una funcion significa que la funcion siempre devolvera una promesa.Otros valores seran envueltos y resueltos en una promesa automaticamente.

![[Pasted image 20230121221637.png]]

Se podria explicitamente devolver una promesa, lo cual seria lo mismo:

![[Pasted image 20230121221647.png]]
Async se asegura de que la funcion devuelva una promesa, o envuelve las no promesas y las transforma en una.

Para declarar un método de clase async, simplemente se le antepone async:

![[Pasted image 20230121221657.png]]
### Await

La palabra clave **await** funciona solo dentro de funciones async.

La sintaxis es :

![[Pasted image 20230121221710.png]]
Await hace que JS espere hasta que la promesa responda y devuelve su resultado.

![[Pasted image 20230121221721.png]]
Await literalmente suspende la ejecución de la función hasta que se establezca la promesa, y luego la reanuda con el resultado de la promesa. Eso no cuesta ningún recurso de CPU, porque el motor de JavaScript puede hacer otros trabajos mientras tanto: ejecutar otros scripts, manejar eventos, etc.

En los navegadores modernos, await de nivel superior funciona, siempre que estamos dentro de un módulo. Si no usamos modulos, podemos envolverlos en una funcion async anonima.

![[Pasted image 20230121221733.png]]
### Manejo de errores

Si una promesa se resuelve normalmente, entonces await promise devuelve el resultado. Pero en caso de rechazo, dispara un error, tal como si hubiera una instrucción throw en aquella línea.

![[Pasted image 20230121221748.png]]
En situaciones reales, la promesa tomará algún tiempo antes del rechazo. En tal caso habrá un retardo antes de que await dispare un error.

Podemos atrapar tal error usando try..catch, de la misma manera que con un throw normal:
![[Pasted image 20230121221800.png]]
En el caso de un error, el control salta al bloque catch. Podemos también envolver múltiples líneas:

![[Pasted image 20230121221810.png]]
Si no tenemos try..catch, entonces la promesa generada por el llamado de la función async f() se vuelve rechazada. Podemos añadir .catch para manejarlo.

![[Pasted image 20230121221821.png]]
Si olvidamos añadir .catch allí, obtendremos un error de promesa no manejado (visible en consola). Podemos atrapar tales errores usando un manejador de evento global unhandledrejection