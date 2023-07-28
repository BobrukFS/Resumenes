# Objetos nativos
Los valores de tipo string, número, y Booleano no son objetos, y aunque el lenguaje no se queja si intentas establecer nuevas propiedades en ellos, en realidad no almacena esas propiedades.

Los numeros y las cadenas de caracteres que asignamos a las variables se convierten automaticamente en objetos por el interprete javascript. Cada vez que asignamos un nuevo valor a una variable, en realidad estamos asignando un objeto que contiene ese valor. Debido a que los valores que almacenamos en variables son de tipos diferentes, existen diferentes tipos de objetos para representarlos.

La  mayor ventaja **pueden almacenar propiedades**.

Si queremos podemos crear estos objetos directamente usando sus constructores. Existen diferentes constructores disponibles dependiendo del tipo de valor que queremos almacenar:

* **String(valor)**: Este constructor crea objetos para almacenar cadenas de caracteres. Acepta una cadena de caracteres o cualquier valor que pueda convertirse en una cadena de caracteres.

* **Boolean(valor)**: Este constructor crea objetos para almacenar valores booleanos. Acepta los valores true y false. Si el valor se omite o es igual a 0, NaN, null, undefined, o una cadena de caracteres vacia, el valor almacenado en el objeto es false, en caso contrario es true.

* **Array(valores)**: Este constructor crea objetos para almacenar arrays. Si se proveen multiples valores, el constructor crea un array con esos valores, pero si solo se prove un valor, y ese valor es un numero entero, el constructor crea un array con la cantidad de elementos que indica el valor del atributo y almacena el valor undefined en cada indice.

Estos constructores trabajan con el operador **new** para poder crear nuevos objetos.

![[Pasted image 20230110203411.png]]
Convertir valores en objetos permite al lenguaje ofrecer la funcionalidad necesaria para manipular esos valores. Nosotros vamos a tener el **valor primitivo** y tambien le podemos agregar propiedades. Por ejemplo nuestro objeto valor, tiene como valor primitivo 5 y le podemos agregar propiedades al objeto (Por ejemplo valor.nombre = “Numero entero”).
