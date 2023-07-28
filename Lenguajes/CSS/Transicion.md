# Transicion
Una animación real requiere una transición entre los dos pasos del proceso. Se suele utilizar con :focus y :hover entre otros, pero tambien podemos trabajar en conjunto con la propiedad transform. Para este propósito, CSS ofrece las siguientes propiedades.

* **transition-property** : Esta propiedad especifica las propiedades que participan en la transición. Además de los nombres de las propiedades, podemos asignar el valor all para indicar que todas las propiedades participarán de la transición. Si la transicion tiene que considerar los valores de mas de una propiedad, tenemos que declarar los nombres de las propiedades separadas por coma.

* **transition-duration :** Esta propiedad especifica la duracion de la transicion en segundos (S).

* **transition-timing-function** : Esta propiedad determina la funcion que se usa para calcular los valores para la transicion. Los valores disponibles son **ease**, **ease-in**, **ease-out**, **ease-in**, **linear**, **step-start**, y **step-end.**

	![[Pasted image 20230717141912.png]]

Podemos usar para facilitar https://cubic-bezier.com/#.17,.67,.83,.67

* **transition-delay** : Esta propiedad especifica el tiempo que el navegador esperara antes de iniciar la animacion.

* **transition :** Esta propiedad nos permite declarar todos los valores de la transicion al mismo tiempo.

## Multiples animaciones

```css
div {
	width: 200px;
	background : black;
	transition: background 2s ease-in, width 2s, ease-in;
}

div:hover{
	width : 400px;
	background-color : white;
}
```

