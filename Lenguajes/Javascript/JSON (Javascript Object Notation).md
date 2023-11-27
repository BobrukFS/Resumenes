# Json

JSON es un formato estandar basado en texto para representar datos estructurados basados en la sintaxis de objetos de Javascript. Se utiliza usualmente para trasmitir datos en aplicaciones web (por ejemplo, enviar algunos datos desde el servidor al cliente o visceversa).

Para poder transferir datos hay que **serializarlos a formato JSON**. Para poder acceder a dichos datos tenemos que **convertir el JSON a objetos**, es decir, **deserializarlos**. JS proporciona un objeto JSON global que tiene metodos disponibles para convertir entre los dos.

Los archivos JSON tienen como extension **.json**
## ¿Para que se usa el JSON?

-Compartir y transferir informacion entre distintos sistemas de software.

-Almacenar informacion en sistemas de persistencia.

**Dato:** En programación, la **persistencia** es la acción de preservar la información de un objeto de forma permanente (guardado), pero a su vez también se refiere a poder recuperar la información del mismo (leerlo) para que pueda ser nuevamente utilizado.
### Compartir informacion entre sistemas

El hecho de que JSON se representa en archivos de texto plano hace muy fácil su transferencia entre sistemas informáticos, usando protocolos ampliamente extendidos como HTTP.

En Internet el uso más importante es el de generar datos en el backend y enviarlos a las aplicaciones frontend. El flujo sería el siguiente:

1. Las aplicaciones frontend requieren datos para representar al usuario.

2. Mediante Javascript realizan solicitudes HTTP a un endpoint (URL) en el backend. Estas solicitudes se realizan de manera asíncrona mediante **[[Objeto XMLHttpRequest]]** o puedo utilizar axios o fetch.

3. El backend recibe la solicitud sobre el dato que se requiere desde el frontend, o la operación que se desea realizar (ediciones, inserciones, etc.)

4. El backend realiza la operación, enviando el resultado al frontend en formato JSON.

5. El frontend recibe el JSON y generalmente construye mediante Javascript el HTML necesario para representar esa información convenientemente al usuario.

Otro ejemplo:

![[Pasted image 20230122181945.png]]
## Sintaxis de codigo JSON

JSON es capaz de representar números, valores lógicos, cadenas, valores nulos, arrays  y matrices (secuencias ordenadas de valores) y objetos (mapas de cadena de valores) compuestos de estos valores (o de otras matrices y objetos). JSON no representa de manera nativa tipos de datos más complejos como funciones, expresiones regulares, fechas, symbol, propiedades que almacenan undefined y así sucesivamente.

### Reglas de sintaxis JSON:

- Los datos están en pares de nombre / valor. Un par de nombre / valor consta de un nombre de campo (entre comillas dobles), seguido de dos puntos, seguido de un valor:

![[Pasted image 20230122182058.png]]

- Los datos están separados por comas

- Las llaves sostienen objetos. Los objetos JSON se escriben entre llaves. Al igual que en JavaScript, los objetos pueden contener varios pares de nombre / valor:

Aquí, las claves deben estar entre comillas dobles y no se permite el uso de comillas simples.

![[Pasted image 20230122182120.png]]
- Los corchetes sostienen matrices. Las matrices JSON se escriben entre corchetes. Al igual que en JavaScript, una matriz puede contener objetos.

![[Pasted image 20230122182137.png]]
- A diferencia de javascript, Se deben usar siempre comillas dobles a la hora de encerrar cadenas y nombres de los atributos del objeto. Estamos obligador a colocar en comillas el nombre de la propiedad.

- UTF-8 obligatorio

**Dato:** Los comentarios no estan permitidos en JSON

Un ejemplo de codigo JSON:

![[Pasted image 20230122182150.png]]
**Dato:** Los archivos JSON pueden tener cualquier nivel de anidación que sea necesario, ya que podemos colocar unos objetos dentro de otros, creando un árbol de datos de cualquier profundidad. Si lo asignamos a una variable podríamos acceder a los datos dentro de ella usando la misma notación de punto/corchete.
### Limitaciones de JSON

- En JSON no podemos indicar los tipos de los datos de los elementos.

- No es posible insertar comentarios.

- No deben existir referencias circulares.

![[Pasted image 20230122182206.png]]
## Validar formato JSON

Para validar el formato JSON tenemos esta pagina https://jsonlint.com/

## Funciones para JSON en JS

El trabajo en Javascript con JSON incluye un par de métodos de utilidad, que dependen del objeto global "JSON". Mediante éstos es posible convertir un objeto Javascript a una cadena JSON y viceversa.

* **JSON.stringfy(objeto) :** Esta funcion Javascript convierte un objeto, un array u otro valor en su representacion como cadena en formato JSON, es decir estamos serializando. La cadena de caracteres json resultante se llama objeto JSON-codificado o **serializado** o convertido a String o reunido. Estamos listos para enviarlo por la red o colocarlo en el almacenamiento de información simple.

![[Pasted image 20230122182312.png]]

 La **sintaxis completa de JSON.stringify** es:
	
![[Pasted image 20230122182324.png]]
	
	Donde:

- **value:** Un valor para codificar

- **Replacer :** Array de propiedades para codificar o una funcion de mapeo function(propiedad,valor). Si pasamos un array de propiedades a él, solamente éstas propiedades serán codificadas, si no especificamos se serializan todas. Ejemplo:

![[Pasted image 20230122182353.png]]
Aquí probablemente seamos demasiado estrictos. La lista de propiedades se aplica a toda la estructura de objeto.

![[Pasted image 20230122182439.png]]
Podemos utilizar una función en lugar de un array como el sustituto. La función se llamará para cada par de (propiedad, valor) y debe devolver el valor “sustituido”, el cual será utilizado en lugar del original. O undefined si el valor va a ser omitido.

![[Pasted image 20230122182452.png]]
Por favor tenga en cuenta que la función replacer recibe todos los pares de propiedad/valor incluyendo objetos anidados y elementos de array. Se aplica recursivamente. El valor de this dentro de replacer es el objeto que contiene la propiedad actual.

El primer llamado es especial. Se realiza utilizando un “Objeto contenedor” especial: {"": meetup}. En otras palabras, el primer par (propiedad, valor) tiene una propiedad vacía, y el valor es el objeto objetivo como un todo. Es por esto que la primer línea es ":[object Object]" en el ejemplo de arriba.

* **splace :** Cantidad de espacio para usar para el formateo. Ejemplo:

![[Pasted image 20230122182530.png]]
**Dato:** Se puede tener un  **“toJSON” Personalizado**

* **JSON.Parse(cadena) :** Esta funcion permite convertir una cadena en formato JSON en un objeto Javascript que contiene la representacion del valor de esa cadena, es decir estamos **deserializando.** La sintaxis:

![[Pasted image 20230122182608.png]]
Donde:
 -**str :** string JSON para analizar.

Ejemplo:

![[Pasted image 20230122182624.png]]
 **-reviver :** function(key, value) opcional que sera llamado para cada par (propiedad, valor) y puede transformar el valor.

Ejemplo: Imagina esto, obtenemos un objeto meetup convertido en String desde el servidor.

![[Pasted image 20230122182720.png]]
Entonces al dar error, le pasemos a JSON.parse la función reactivadora como el segundo argumento, esto devuelve todos los valores “tal cual” pero date se convertirá en una Date:

![[Pasted image 20230122182737.png]]

![[Pasted image 20230122182752.png]]

Entonces para enviarlo o recibirlo lo hacemos en formato JSON, para utilizarlo lo hacemos en formato texto.

## Ventajas y desventajas de JSON
### Ventajas de JSON

-Más fácil de estructurar y trabajar con datos estructurados.

-El tamaño de los archivos que se transfieren es ligero.

-El codigo esta basado en el lenguaje Javascript.

-No requiere configurar encabezados especiales para el tipo de contenido.

-Se puede enviar en el cuerpo de la solicitud usando el encabezado `'Content-Type': 'application/json'`.

-Amplio soporte para ajax en la mayoria de frameworks

-Todos los lenguajes disponen de funciones para interpretar cadenas JSON y convertir datos en cadenas JSON validas.

-Se escribe en archivos de texto plano (Un **Texto plano** (plain text), son aquellos archivos formados exclusivamente por texto (sólo caracteres), sin ningún formato; es decir, no requieren ser interpretados para leerse (aunque pueden ser procesados en algunos casos).con codificación UTF8, que es compatible con todos los sistemas.

### Desventajas de JSON

-No es tan conveniente para el envío de archivos binarios (como imágenes).

[[FormData]]
[[JSONP]]
[[JSON Server]]