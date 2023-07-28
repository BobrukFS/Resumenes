# Mutabilidad

La **mutabilidad** es la **capacidad de un elemento de cambiar su estado**. Cambiando el valor de la propiedad de un objeto, o la referencia que tiene una variable, estas haciendo uso de la mutabilidad de estos elementos.
Los objetos, arreglos y otras estructuras no primitivas son mutables. 

## Mutabilidad en objetos

Los objetos son de tipo de referencia, lo que significa que a una variable a la que se le asigna un objeto, se le esta definiendo una referencia a ese objeto. Si a otra variable se le asigna una referencia al mismo objeto y lo modifica, afectara a todas las variables vinculadas, cuando es asi se dice que tienen la misma identidad.

```javascript
const persona = {
	nombre : "Exe",
};

const otraPersona = persona;
otraPersona.nombre = "Sofia";

console.log(persona.nombre); //Sofia
```

Al momento de crear un nuevo objeto, se crea el espacio en memoria suficiente para alojarlo y administrarlo. Si a una variable se le asigna a ese objeto, se crea una referencia al espacio de memoria donde ese objeto esta alojado. No importan las propiedades o valores del objeto, siempre que se cree uno nuevo ocupara otro espacio de memoria y se tratara de un nuevo objeto.

## ¿Por que importa la inmutabilidad?
La mutabilidad es una de las principales causas de que el codigo de las aplicaciones genere efectos secundarios. Lo que se busca al almacenar los datos de manera inmutable es tener persistencia en ellos.
Para evitar crear variables que referencien a un objeto podemos utilizar el metodo Object.assign que nos permite crear un nuevo objeto copiando los valores de otro, tambien podemos utilizar Object.freeze que impide que un objeto sea cambiado.