# Fondos sombreados
CSS incluye las siguientes propiedades para generar sombras para la caja de un elemento y también para formas irregulares como texto.

* **box-shadow** : Esta propiedad genera una sombra desde la caja del elemento. La propiedad acepta hasta seis valores: Podemos declarar el **desplazamiento horizontal**, **desplazamiento vertical de la sombra**, el **radio de difuminado**, el **valor de propagación**, el **color de la sombra**, y también podemos incluir el valor **inset** para indicar que la sombra deberá proyectarse dentro de la caja u **outset** que indica que la sombra debera proyectarse fuera de la caja. 
	
	El desplazamiento puede ser positivo o negativo. Los valores negativos posicionan la sombra a la izquierda y encima del elemento, mientras que los positivos crean una sombra a la derecha y debajo del elemento. El valor 0 ubica a la sombra detrás del elemento y ofrece la posibilidad de generar un efecto de difuminado a su alrededor. 

	Podemos declarar varias sombras simultaneas separando con coma.

* **text-shadow** : Esta propiedad genera una sombra desde un texto. Acepta hasta cuatro valores. Podemos declarar el desplazamiento horizontal y vertical, el radio de difuminado y el color de la sombra.

Se puede hacer tambien con [https://www.cssmatic.com/box-shadow](https://www.cssmatic.com/box-shadow).

**Dato**: Las sombras suelen ser transparentes por lo que es conveniente pasarle el color en rgba o hsla. Ademas hay que respetar de donde viene la luz que hace que se proyecte la sombra.
