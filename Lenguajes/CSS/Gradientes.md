# Gradientes
Un gradiente se forma mediante una serie de colores que varían continuamente con una transición suave de un color a otro. Los gradientes se crean como imágenes y se agregan al fondo del elemento con las propiedades **background-image** o **background**. Para crear la imagen con el gradiente, CSS ofrece las siguientes funciones:

+ **linear-gradient(posición, ángulo, colores)** : Esta función crea un gradiente lineal. El atributo posición determina el lado o la esquina desde la cual comienza el gradiente y se declara con los valores top, bottom, left y right(se pueden declarar 2 posiciones si queremos para que comience en la esquina); el atributo ángulo define la dirección del gradiente y se puede declarar en las unidades deg (grados), grad (gradianes), rad (radianes), o turn (espiras), y el atributo colores es la lista de colores que participan en el gradiente separados por coma. Los valores para el atributo colores pueden incluir un segundo valor en porcentaje separado por un espacio para indicar la posición donde finaliza el color. Si usamos el valor **transparent** en lugar de un color, podemos hacer que el gradiente sea traslúcido y de esta manera se mezcle con el fondo (este efecto también se puede lograr con la función rgba()).

![[Pasted image 20230703152155.png]]

+ **radial-gradient(posición, forma, colores, extensión)** :  Esta función crea un gradiente radial. El atributo posición indica el origen del gradiente y se puede declarar en píxeles, en porcentaje, o por medio de la combinación de los valores center, top, bottom, left y right(se pueden declarar 2 posiciones si queremos para que comience en la esquina), el atributo forma determina la forma del gradiente y se declara con los valores circle y ellipse, el atributo colores es la lista de los colores que participan en el gradiente separados por coma, y el atributo extensión determina la forma que el gradiente va a adquirir con los valores closest-side, closest-corner, farthest-side, y farthest-corner. Los valores para el atributo colores pueden incluir un segundo valor en porcentaje separado por un espacio para indicar la posición donde finaliza el color.

## Gradientes repetitivos

También existen gradientes repetitivos que pueden ser tanto radiales como lineales. Funcionan de la misma forma que los gradientes regulares, pero repiten el patrón. Para ello se utiliza la **repeating-linear-gradient** o **repeating-radial-gradient**.

Se puede utilizar tambien esta pagina para hacerlo [https://cssgradient.io/](https://cssgradient.io/).

