# Animaciones
La propiedad transition lo que va hacer es crear una animacion basica donde solo se involucran dos estados en el proceso, el estado inicial y el estado final. Para crear una animacion real, necesitamos declarar mas de dos estados, como los fotogramas de una pelicula.

![[Pasted image 20221213152209.png]]

* **animation-play-state** : La propiedad CSS establece si una animacion se esta ejecutando o esta en pausa. Los valores son **paused** y **running**.

Un valor de animation-timing-function es el uso de **steps**. Este nos permite hacer cortes o temporizar la animacion. La sintaxis es **steps(n , direccion)** donde n indica cuantos cortes tendra la animacion, mientras que la direccion puede ser **start**(completa el tiempo de un paso antes de que la animacion comience) o **end** (empieza la animacion inmediatamente). 

Estas propiedades configuran la animación, pero los pasos se declaran por medio de la regla **@keyframes**. Esta regla se debe identificar con el nombre usado para configurar la animación, y debe incluir la lista de propiedades que queremos modificar en cada paso. La posición de cada paso de la animación se determina con un valor en porcentaje, donde 0 % corresponde al primer fotograma o al comienzo de la animación, y 100 % corresponde al final.

Ejemplo:

```CSS
div {
    width: 200px;
    background-image: url(https://media.revistagq.com/photos/5ca5f6a77a3aec0df5496c59/4:3/w_1960,h_1470,c_limit/bob_esponja_9564.png);
    transition: background 2s ease-in, width 2s ease;
    height: 200px;
    clip-path: circle(50% at center center);
    animation-name: hola;
    animation-duration: 2s;
    animation-timing-function: ease;
    animation-fill-mode: forwards;
}

@keyframes hola {
    20%, 70% {  /*Indica que en 20% y 70% de la animacion hara lo mismo*/
        width: 300px;
        height: 300px;
    }

  

    50% {
        width: 400px;
        height: 400px;
    }

  

    100% {
        width: 100px;
        height: 100px;
    }
}
```

[[Transform]]
[[Transicion]]