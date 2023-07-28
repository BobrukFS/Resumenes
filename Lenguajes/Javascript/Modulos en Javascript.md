# [[Modulos]] en Javascript
## Export e Import
Los modulos pueden cargarse entre si y usar directivas especiales **export** e **import** para intercambiar funcionalidad. **Tenga en cuenta que las declaraciones de import/export no funcionan si están dentro `{...}`.**

* **export** : Etiqueta las variables y funciones que deberian ser accesibles desde fuera del modulo actual. Las exportaciones se crearan solo una vez y se comparten entre los importadores.

* **import** : Permite importar funcionalidades de otros modulos.

Para aprovechar los modulos, debemos crear un script con un **type** de **module**

```javascript
<script src="modulos.js" type="module"><script>
```

Un script que utilice type module ahora podra utilizar las caracteristicas de import y export. 

### Export

Podemos colocar export antes de las sentencias o despues.

```js
//Exportacion de a uno, en linea

// 📁 sayHi.js 
export function sayHi(user) { alert(`Hello, ${user}!`); }

//Exportacion de 2 o mas, por separado

// 📁 sayHi.js 
function sayHi(user) { alert(`Hello, ${user}!`); }
let nombre = "Tomas";
export {sayHi, nombre}

//Exportar con as, sirve para Exportar bajo nombres diferentes
//  📁 sayHi.js
export {sayHi as hi, sayBye as bye};
// 📁 main.js 
import * as say from './say.js'; 
say.hi('John'); // Hello, John! 
say.bye('John'); // Bye, John!
```

Si nosotros exportamos una clase o funcion en la misma linea, no hace falta agregar punto y coma al final.

```javascript
export function sayHi(user) {
alert(`Hello, ${user}`)
} // no ; en el final
```

#### Export default

En la practica existen dos tipos de modulos:

1. Modulos que contienen una libreria, paquetes de funciones.
2. Modulos que declarar una entidad simple, por ejemplo una clase.

Se prefiere el segundo enfoque, de modo que cada cosa reside en su propio modulo. Esto requiere muchos archivos, ya que todo requiere su propio modulo. Esto hace que la navegacion de codigo se vuelva mas facil si los archivos estan bien nombrados y estructurados en carpetas.

Los modulos proporcionan una sintaxis especial **export default** para que la forma de una cosa por modulo se vea mejor. Sólo puede existir un sólo `export default` por archivo.

```javascript

// 📁 user.js 
export default class User { // sólo agregar "default" 
	constructor(name) { 
		this.name = name; 
	} 
}
```

Y luego podemos importarlo sin llaves.

```js
// 📁 main.js 
import User from './user.js';  // no {User}, sólo User 
new User('John');
```

![[Pasted image 20230414170808.png]]

No dar un nombre está bien, porque solo hay un “export default” por archivo, por lo que “import” sin llaves sabe qué importar.

```js
//Ejemplo:
export default class { 
// sin nombre de clase 
constructor() { 
... } 
}
```

En algunas situaciones, la palabra clave default se usa para hacer referencia a la exportacion predeterminada.

```js
function sayHi(user) { 
alert(`Hello, ${user}!`); 
} // lo mismo que si agregamos "export default" antes de la función 
export {sayHi as default};
```

Otro caso, es que se exporte una cosa principal default y algunas otras cosas.

```javascript
// 📁 user.js 
export default class User { constructor(name) { this.name = name; } } 

export function sayHi(user) { alert(`Hello, ${user}!`); }
//
//Aquí la manera de importar la exportación predeterminada junto con la exportación con nombre:
// 📁 main.js 
import {default as User, sayHi} from './user.js'; 
new User('John');
```

##### Caracteristicas negativas

Las exportaciones con nombre a diferencia de las default, nombran exactamente lo que importan, asi que tenemos esa informacion de ellos. Ademas obligan a usar exactamente el nombre correcto para importar.  Mientras que en una exportacion default siempre elegimos el nombre al importar lo que puede generar confusiones entre los miembros del equipo. Por lo general, para evitar eso y mantener el codigo consistente, existe una regla que establece que las variables importadas deben corresponder a los nombres de los archivos.
### Import

Debemos colocar import siempre al principio de un modulo. El navegador busca y evalua automaticamente el modulo importado(y sus importaciones), y luego ejecuta el script.

```javascript
//Importar 1
// 📁 main.js 
import {sayHi} from './say.js';
sayHi('John'); // Hello, John!
sayBye('John'); // Error

//Importar 2 o mas
// 📁 main.js 
import {sayHi, sayBye} from './say.js';

sayHi('John'); // Hello, John! 
sayBye('John'); // Bye, John!

//Importar todos
// 📁 main.js
import * as say from './say.js';
say.sayHi('John'); say.sayBye('John');

//Importar con as, sirve para importar bajo nombres diferentes
// 📁 main.js 
import {sayHi as hi, sayBye as bye} from './say.js';
hi('John'); // Hello, John! 
bye('John'); // Bye, John!
```

**¿Porque deberiamos listar explicitamente lo que necesitamos importar si podemos importar todo?**

1.  Listar explícitamente qué importar da nombres más cortos: `sayHi()` en lugar de `say.sayHi()`.

2.  La lista explícita de importaciones ofrece una mejor visión general de la estructura del código: qué se usa y dónde. Facilita el soporte de código y la refactorización.

No hay que tener miedo de importar demasiado, ya que se cuenta con herramientas de empaquetado modernas como webpack que construyen los modulos juntos y optimizan la velocidad de carga. Tambien eliminan las importaciones no usadas. Por ejemplo, si importas `import * as library` desde una librería de código enorme, y usas solo unos pocos métodos, los que no se usen no son incluidos en el paquete optimizado.

#### Import default

Si importamos todo como un objeto, entonces la propiedad default es exactamente la exportacion predeterminada:

```js
// 📁 main.js 
import * as user from './user.js'; 
let User = user.default; // la exportación predeterminada 
new User('John');
```

## Caracteristicas de los modulos

* Los modulos siempre trabajan en modo estricto.

* Cada modulo tiene su propio alcance de nivel superior. En otras palabras, las variables y funciones de nivel superior de un modulo no se ven en otros script.

* Un codigo de modulo se evalua solo la primera vez cuando se importa. Si el mismo modulo se importa en varios otros modulos, su codigo se ejecuta solo una vez: en el primer import. Luego, sus exportaciones se otorgan a todos los importadores que siguen.

Si ejecutar un codigo de modulo trae efectos secundarios (como mostrar un mensaje, etc), importarlo varias veces lo activara solo una vez, la primera.

```javascript
// 📁 alert.js 
alert("Módulo es evaluado!");

// Importar el mismo módulo desde archivos distintos 

// 📁 1.js 
import `./alert.js`; // Módulo es evaluado! 

// 📁 2.js 
import `./alert.js`; // (no muestra nada porque el modulo ya fue evaluado).
```

El codigo de modulos del nivel superior debe ser usado para la inicializacion y creacion de estructuras de datos internas especificas del modulo. Si necesitamos algo que pueda ser llamado varias veces debemos exportarlo como una funcion.

```javascript
// 📁 admin.js 
export let admin = { name: "John" };

// 📁 1.js 
import {admin} from './admin.js'; admin.name = "Pete"; 
// 📁 2.js 
import {admin} from './admin.js'; alert(admin.name); // Pete 

// Ambos 1.js y 2.js hacen referencia al mismo objeto admin 
// Los cambios realizados en 1.js son visibles en 2.js
```

Esto es porque el modulo se ejecuta solo una vez. Los exports son generados y luego compartidos entre importadores, entonces si algo cambia en el objeto `admin`, otros importadores lo verán.

Ejemplo: Un módulo puede brindar una funcionalidad genérica que necesite ser configurada. Por ejemplo, la autenticación necesita credenciales. Entonces se puede exportar un objeto de configuración esperando que el código externo se lo asigne.

Aquí está el patrón clásico:

1.  Un módulo exporta algún medio de configuración, por ejemplo un objeto configuración.

3.  En el primer import lo inicializamos, escribimos en sus propiedades. Los scripts de la aplicación de nivel superior pueden hacerlo.

5.  Importaciones posteriores usan el módulo

```js
//Por ejemplo, el módulo `admin.js` puede proporcionar cierta funcionalidad (ej. autenticación), pero espera que las credenciales entren al objeto `admin` desde afuera:

// 📁 admin.js, Aquí `admin.js` exporta el objeto `config` (inicialmente vacío, pero podemos tener propiedades por defecto también).

export let config = { }; 
export function sayHi() { alert(`Ready to serve, ${config.user}!`); }

//Entonces en `init.js`, el primer script de nuestra app, importamos `config` de él y establecemos `config.user`:

// 📁 init.js 
import {config} from './admin.js'; 
config.user = "Pete";

//Ahora el modulo admin.js esta configurado. Importadores posteriores pueden llamarlo, y el muestra correctamente el usuario actual.

// 📁 another.js 
import {sayHi} from './admin.js';
sayHi(); // Ready to serve, _Pete_!
```

#### No se permiten modulos sueltos
En el navegador, import debe obtener una URL relativa o absoluta. Los modulos sin ninguna ruta se denominan modulos sueltos.

```js
import {sayHi} from 'sayHi'; // Error, módulo suelto // el módulo debe tener una ruta, por ejemplo './sayHi.js' o dondequiera que el módulo esté
```

Los navegadores antiguos no entienden `type = "module"`. Los scripts de un tipo desconocido simplemente se ignoran. Para ellos, esp osible proporcionar un respaldo utilizando el atributo **nomodule**.

```javascript
<script type="module">

  alert("Ejecuta en navegadores modernos");

<script>

  

<script nomodule>

  alert("Los navegadores modernos conocen tanto type=module como nomodule, así que omita esto")

  alert("Los navegadores antiguos ignoran la secuencia de comandos con type=module desconocido, pero ejecutan esto.");
<script>
```

### Diferencias entre los script normales y los modulos.

Los modulos estan siempre diferidos, es decir, tienen el mismo efecto que el atributo **defer**, para ambos scripts ya sean externos y en linea. Es decir, la descarga de los modulos externos no bloquea el procesamiento de HTML, se cargan en paralelo con otros recursos.
Los modulos esperan hasta que el documento HTML este completamente listo y luego lo ejecuta. Se mantiene el orden relativo de los script: los scripts que van primero en el documento, se ejecutan primero.
Como efecto secundario los modulos siempre ven la pagina HTML completamente cargada incluidos los elementos HTML debajo de ellos.

El script normal se ejecuta inmediatamente, por lo que vemos siempre su salida primero.

Al usar módulos, debemos tener en cuenta que la página HTML se muestra a medida que se carga, y los módulos JavaScript se ejecutan después de eso, por lo que el usuario puede ver la página antes de que la aplicación JavaScript esté lista. Es posible que algunas funciones aún no funcionen. Deberíamos poner “indicadores de carga”, o asegurarnos de que el visitante no se confunda con eso.

Para los scripts de modulo podemos utilizar async para que no espere nada.

Los scripts externos que tengan type module son diferentes a los normales en dos aspectos:

- los scripts externos con el mismo src solo se ejecutan una vez.

- Los scripts externos que se buscan desde otro origen (p.ej otra sitio web) requiere encabezados [CORS](https://developer.mozilla.org/es/docs/Web/HTTP/CORS) para permitir la busqueda. Esto asegura mejor seguridad de forma predeterminada.

## Reexportacion

La sintaxis “Reexportar” `export ... from ...` permite importar cosas e inmediatamente exportarlas (posiblemente bajo otro nombre), de esta manera:

```js
export {sayHi} from './say.js'; // reexportar sayHi 
export {default as User} from './user.js'; // reexportar default
```

**¿Por qué se necesitaría eso?**

Imagine que estamos escribiendo un “paquete”: una carpeta con muchos módulos, con algunas de las funciones exportadas al exterior (herramientas como NPM nos permiten publicar y distribuir dichos paquetes pero no estamos obligados a usarlas), y muchos módulos son solo “ayudantes”, para uso interno en otros módulos de paquete.

![[Pasted image 20230414172951.png]]

Nos gustaría exponer la funcionalidad del paquete a través de un único punto de entrada.

En otras palabras, una persona que quiera usar nuestro paquete, debería importar solamente el archivo principal `auth/index.js`.

```javascript
import {login, logout} from 'auth/index.js'
```

El “archivo principal”, `auth/index.js`, exporta toda la funcionalidad que queremos brindar en nuestro paquete.

La idea es que los extraños, los desarrolladores que usan nuestro paquete, no deben entrometerse con su estructura interna, buscar archivos dentro de nuestra carpeta de paquetes. Exportamos solo lo que es necesario en `auth/index.js` y mantenemos el resto oculto a miradas indiscretas.

Como la funcionalidad real exportada se encuentra dispersa entre el paquete, podemos importarla en `auth/index.js` y exportar desde ella:

```js
// 📁 auth/index.js 
// importar login/logout e inmediatamente exportarlas 
import {login, logout} from './helpers.js'; 
export {login, logout}; // importar default como User y exportarlo

import User from './user.js'; 
export {User};
```

Ahora los usuarios de nuestro paquete pueden hacer esto `import {login} from "auth/index.js"`

La sintaxis `export ... from ...` es solo una notación más corta para tal importación-exportación:

```js
// 📁 auth/index.js 
// re-exportar login/logout 
export {login, logout} from './helpers.js'; 
// re-exportar export default como User 
export {default as User} from './user.js';
```

La diferencia notable de `export ... from` comparado a `import/export` es que los módulos re-exportados no están disponibles en el archivo actual. Entonces en el ejemplo anterior de `auth/index.js` no podemos usar las funciones re-exportadas `login/logout`.

### Reexportando la exportación predeterminada

Digamos que tenemos `user.js` con `export default class User`, y nos gustaría volver a exportar la clase `User` de él:

```javascript
// 📁 user.js 
export default class User { 
// ... 
}

//Para reexportar la exportación predeterminada, tenemos que escribir 
export {default as User}

//Para reexporta únicamente las exportaciones con nombre e ignorar la exportacion predeterminada

export * from './user.js'

// Si queremos reexportar tanto la exportacion con nombre como la predeterminada, se necesitan:

export * from './user.js'; // para reexportar exportaciones con nombre 
export {default} from './user.js'; // para reexportar la exportación predeterminada

```

[[Importaciones dinamicas]]
[[Herramientas de ensamblaje]]