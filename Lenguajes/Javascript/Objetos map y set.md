Es una alternativa de los objetos literales.
# Objeto map

Un **objeto Map** es un grupo de pares clave-valor en el que se puede usar cualquier tipo de datos como clave(a diferencia de un objeto que solo permitia strings, aca podemos utilizar numeros, booleanos, objetos como clave) y que puede mantener el orden de sus entradas. Los mapas se pueden inicializar con la sintaxis **new Map().** Como en el caso de un Array, tenemos un grupo con índice cero y también podemos ver la cantidad de elementos disponibles por defecto en el Map. Un map no contiene ninguna key por defecto. 

**Dato** Es mejor utilizar la clase llamada Map que viene implementada en JS que utilizar objetos simples como mapas.

```js
//Forma simplificada

let mapa = new Map([["name", "Exequiel"], ["lastname", "Bobruk"]]);

//Otra forma

let mapa = new Map()
.set("name", "Exequiel")
.set("lastname", "Bobruk");
```

Los metodos y propiedades son:

* **set(clave, valor) :** Almacena el valor asociado a la clave.

* **get(clave) :** Devuelve el valor de la clave. Sera undefined si la clave no existe en map.

* **has(clave) :** Devuelve true si la clave existe en map, false si no existe.

* **delete(clave) :** Elimina el valor de la clave. En el método, se muestra un booleano ( truesi existió un elemento y se eliminó, y falsesi no coincidió con ningún elemento).

* **clear() :** Elimina todo de map.

* **size  :** Esta propiedad devuelve la cantidad actual de elementos.

* **keys() :** Devuelve un iterable para las claves.

* **values() :** Devuelve un iterable para los valores.

* **entries() :** Devuelve un iterable para las entradas[clave,valor]. Es el que se usa por edefecto en for…of.

* **forEach(funcion) :** El método forEach() ejecuta la función indicada una vez por cada elemento del map. El atributo funcion es una referencia a una funcion o una funcion anonima a cargo de procesar los valores. La funcion recibe tres valores: el valor procesar, su clave y una referencia al map.

Una caracteristica importante de Map es que podemos utilizar objetos como claves. Un ejemplo:

![[Pasted image 20230112142609.png]]

**Dato:**  La iteración va en el mismo orden en que se insertaron los valores. Map conserva este orden, a diferencia de un Objeto normal.

Si tenemos un objeto plano y queremos crear un Map a partir de el, podemos usar el metodo Object.entries(obj) que devuelve un array de pares clave/valor para un objecto exactamente en ese formato, por lo que podemos inicializar un map desde un objeto.

![[Pasted image 20230112142644.png]]
Tambien existe un metodo llamado Object.fromEntries que hace lo contrario: dado un array de pares [clave, valor], crea un objeto a partir de ellos. Esto nos sirve por ejemplo si almacenamos los datos en un Map, pero necesitamos pasarlos a un codigo de terceros que espera un objeto simple.

![[Pasted image 20230112142654.png]]
# Objeto set

El **objeto Set** es una colección de conjunto de valores (sin claves), donde cada valor puede aparecer solo una vez, es decir colleciona valores unicos. Podemos inicializar Set con la sintaxis new Set().

```js
//Forma simplificada

let mapa = new Set(["Exequiel", "Sofia"]);

//Otra forma

let mapa = new Set()
.add("Exequiel")
.add("Sofia");
```
Los principales metodos y propiedades del objeto Set:

* **add(valor) :** Agrega un valor, y devuelve el set en si.

* **Delete(valor) :** Elimina el valor, y devuelve true si el valor existia al momento de la llamada, si no, devuelve false.

* **has(valor) :** Devuelve true si el valor existe en el set, si no, devuelve false.

* **clear() :** Elimina todo el contenido del set.

* **size :** Es la cantidad de elementos que tiene el set

* **forEach(funcion) :** La función callback pasada en forEach tiene 3 argumentos: un valor, luego el mismo valor “valueAgain” y luego el objeto de destino que es set. El mismo valor aparece en los argumentos dos veces. For..of tambien se puede utilizar para iterar en set.

* **values() :** Devuelve un iterable para los valores.

* **entries() :** Devuelve un iterable para las entradas [clave,valor].

El Set es una matriz unidimensional con claves únicas, mientras que el Map es una matriz bidimensional con pares clave-valor, donde cada clave será única. Un  Set consiste en una colección de valores únicos, mientras que un map es un par de datos asociados cuando asignamos las claves a los valores.