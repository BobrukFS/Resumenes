# Transform
Una vez que se crean los elementos HTML, estos permanecen inmóviles, pero podemos modificar su posición, tamaño y apariencia por medio de la propiedad **transform.** Esta propiedad realiza cuatro transformaciones básicas a un elemento:

* **scale(x, y)** : Esta función modifica la escala del elemento. Existen otras dos funciones relacionadas llamadas scaleX() y scaleY() pare especificar los valores horizontales y verticales independientemente. Los valores entre 0 y 1 reducen el tamaño del elemento, el valor 1 preserva las proporciones originales, mientras que los valores sobre 1 incrementan las dimensiones del elemento de forma lineal.

* **rotate(ángulo)** : Esta función rota el elemento. El atributo angulo representa los grados de rotación y se puede declarar en deg (grados), grad (gradianes), rad (radianes) o turn (espiras).

* **skew(ángulo)** : Esta función inclina el elemento. El atributo representa los grados de desplazamiento. La función puede incluir dos valores para representar el ángulo horizontal y vertical. Los valores se pueden declarar en deg (grados), grad (gradianes), rad (radianes) o turn (espiras).

* **translate(x, y)** : Esta función desplaza al elemento a la posición determinada por los atributos x e y. Podemos tambien utilizar translateX o translateY.


Con la propiedad **transform-origin**  podemos establecer el origen de las transformaciones de un elemento. El origen de la transformación es el punto alrededor del cual se aplica una transformación. Por defecto es 0,0 o cente center.

**Dato:** cuando combinamos múltiples funciones, debemos considerar que el orden de combinación es importante. Esto se debe a que algunas funciones modifican el punto de origen y el centro del elemento y, por lo tanto, cambian los parámetros sobre los que el resto de las funciones trabajan.

De la misma manera que podemos generar transformaciones en dos dimensiones sobre elementos HTML, también podemos hacerlo en tres dimensiones. Estos tipos de transformaciones se realizan considerando un tercer eje que representa profundidad y se identifica con la letra z.

![[Pasted image 20221213151734.png]]
CSS tambien incluye algunas propiedades que podemos usar para lograr un efecto mas realista:

![[Pasted image 20221213151745.png]]
