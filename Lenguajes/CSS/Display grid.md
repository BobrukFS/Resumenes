# Display grid

CSS Grid es un sistema de diseño bidimensional basado en cuadriculas.

Una cuadrícula es una colección de líneas horizontales y verticales que crean un patrón contra el cual podemos alinear nuestros elementos de diseño.

Una cuadrícula normalmente tendrá **columnas , filas** y luego espacios entre cada fila y columna. Los huecos se conocen comúnmente como **gutters** .

Para definir una grilla usamos **display:grid**; esto habilita el diseño de cuadrícula; todos los elementos secundarios directos del contenedor se convierten en elementos de cuadrícula.

* **grid container**: El elemento sobre el que  `display: grid` se aplica. Es el padre directo de todos los elementos de la cuadrícula. 

* **grid line**: Las líneas divisorias que componen la estructura de la cuadrícula. Pueden ser verticales ("líneas de cuadrícula de columna") u horizontales ("líneas de cuadrícula de fila") y residir en cualquier lado de una fila o columna. Aquí, la línea amarilla es un ejemplo de una línea de rejilla de columna.

![[Pasted image 20230426221814.png]]

* **grid item**: Los hijos (es decir,  descendientes _directos_  ) del contenedor de cuadrícula. 

* **grid cell**: El espacio entre dos filas adyacentes y dos líneas de cuadrícula de columnas adyacentes. Es una sola "unidad" de la red.

* **grid track**: El espacio entre dos líneas de cuadrícula adyacentes. Puede pensar en ellos como las columnas o filas de la cuadrícula. Aquí está la pista de cuadrícula entre las líneas de cuadrícula de la segunda y la tercera fila.

![[Pasted image 20230426221925.png]]
* **grid area**: El espacio total rodeado por cuatro líneas de cuadrícula. Un área de cuadrícula puede estar compuesta por cualquier número de celdas de cuadrícula.

![[Pasted image 20230426221956.png]]

## Definir las medidas de las columnas y filas

Para definir las medidas de las columnas podemos utilizar las propiedades **grid-template-columns**  y **grid-template-row**. Si los elementos abarcan mas que las columnas, se crea una nueva row.

Como valor podemos utilizar cualquier unidad de medida, o podemos usar la unidad **fr**  para cambiar el tamaño de las filas y columnas de la cuadrícula de manera flexible. La unidad fr distribuye el espacio disponible , no todo el espacio. Por lo tanto, si una de tus cuadriculas tiene algo grande dentro, habrá menos espacio libre para compartir.

![[Pasted image 20221213225613.png]]

![[Pasted image 20221213225618.png]]

Podemos utilizar la funcion **repeat()** para crear nuestra cuadricula si tenemos valores repetitivos. El primer valor pasado a la función repeat() especifica la cantidad de veces que desea que se repita, mientras que el segundo valor es la fraccion en la que se divida.

![[Pasted image 20221213231430.png]]

El espacio libre se calcula  después  de cualquier elemento no flexible. En este ejemplo, la cantidad total de espacio libre disponible para las  `fr` unidades no incluye los 50 px:

```css
.container { grid-template-columns: 1fr 50px 1fr 1fr; }
```

Podemos utilizar en repeat el valor auto-fill para que llene todo el espacio con cuadriculas del tamaño que le asignemos. Ejemplo repeat(auto-fill, 100px). La palabra clave`auto-fill` crea tantas pistas como quepan en el contenedor de cuadrícula sin que la cuadrícula se desborde. La palabra clave`auto-fit` se comporta de la misma manera que `auto-fill`, excepto que después de la colocación del elemento de cuadrícula, solo creará tantas pistas como sea necesario y cualquier pista repetida vacía colapsará.

### Espacio entre columnas y filas

Para crear espacios entre grillas, usamos las propiedades **row-gap** espacios entre , **column-gap** para espacios entre columnas y **gap** como abreviatura de ambos.

## Definir un area

Una forma alternativa de organizar los elementos en su cuadrícula es usar la propiedad **grid-template-areas** y dar un nombre a los diversos elementos de su diseño. Para ubicar dicho elemento en el area utilizamos **grid-area**.

![[Pasted image 20221213232101.png]]
![[Pasted image 20221213232106.png]]
![[Pasted image 20221213232112.png]]

## Grid-template

Es una abreviatura para establecer grid-template-rows, grid-template-columns y grid-template-areas en una sola declaracion.

```css

.container { 
grid-template: 
[row1-start] "header header header" 25px 
[row1-end] [row2-start] "footer footer footer" 25px 
[row2-end] / auto 50px auto; 
}

/*Esto es equivalente a*/

.container { 
grid-template-rows: [row1-start] 25px [row1-end row2-start] 25px [row2-end]; 

grid-template-columns: auto 50px auto; 

grid-template-areas: "header header header" "footer footer footer"; 

}

```

## Posicionar elementos en las columnas o filas

Podemos posicionar las cosas de acuerdo con estas líneas especificando la línea inicial y final. Hacemos esto usando las siguientes propiedades:

* **grid-column-start**

* **grid-column-end**

* **grid-row-start**

* **grid-row-end**

Todas estas propiedades pueden tener un número de línea como valor.  O podemos utilizar la unidad `span` se utiliza para definir la cantidad de columnas o filas que un elemento debe ocupar en el grid. Ejemplo:

```css
.item {
	grid-column-start: 2;
	grid-column-end: span 3;
}
```


También puede utilizar las propiedades abreviadas:

* **grid-column**

* **grid-row**

Estos le permiten especificar las líneas de inicio y finalización a la vez, separadas por una barra inclinada /.

Ejemplo: Va de la columna 1 a la 3 y se posiciona en la fila 3.

![[Pasted image 20221213231959.png]]

## Alinear elementos de la cuadricula verticalmente y horizontalmente

#### Alinear horizontalmente

Para ello utilizamos **justify-items**, que sirve para alinear elementos  de la cuadricula a lo largo del eje en linea (row) . Este valor se aplica a todos los elementos de la cuadricula dentro del contenedor.

Este comportamiento tambien se puede establecer en elementos de cuadricula individuales a traves de la propiedad **justify-self**.

#### Alinear verticalmente

Para ello utilizamos la propiedad **align-items**, que sirve para alinear los elementos de la cuadricula a lo largo del eje del bloque (columna). Este valor se aplica a todos los elementos de la cuadrícula dentro del contenedor.

Este comportamiento tambien se puede establecer en elementos de cuadricula individuales a traves de la propiedad **align-self**.

##### Place-items 

La propiedad **place-items** establece las propiedades align-items y justify-items en una sola declaracion.

### Justify content y align content

A veces, el tamaño total de nuestra cuadricula puede ser menor que el tamaño de su contenedor de cuadricula. Esto podria suceder si todos los elementos de la cuadricula tienen el tamaño de unidades no flexibles como px,etc. En este caso podemos establecer la alineacion de la cuadricula dentro del contenedor de la cuadricula.

La propiedad **justify-content** alinea la cuadricula a lo largo del eje en linea(fila). Mientras que **align-content** alinea la cuadricula a lo largo del eje en bloque (columna).

La propiedad **place-content** establece las propiedades **align-content** y **justify-content** en una sola declaracion.

## Grilla explicita e implícita.

La **grilla explícita** es la que creas usando grid-template-columns o grid-template-rows. Si hay más elementos de cuadrícula que celdas en la cuadrícula o cuando un elemento de cuadrícula se coloca fuera de la cuadrícula explícita, el contenedor de cuadrícula genera automáticamente pistas de cuadrícula agregando líneas de cuadrícula a la cuadrícula. La cuadrícula explícita junto con estas pistas y líneas implícitas adicionales forma la denominada **grilla implícita** .

De forma predeterminada, las grillas creadas en la cuadrícula implícita tienen un tamaño auto, lo que en general significa que son lo suficientemente grandes para acomodar su contenido

### Dimensionar tracks implicitas

Si desea dar un tamaño a las pistas de cuadrícula implícitas, puede usar las propiedades **grid-auto-rows y grid-auto-columns**. Si agrega grid-auto-rows un valor de 100px a su CSS, verá que esas filas creadas ahora tienen 100 píxeles de alto sin importar si el contenido de la cuadricula se ajusta o no.

Nuestras grillas de 100 píxeles de altura no serán muy útiles si agregamos contenido en esas pistas que es más alto que 100 píxeles, en cuyo caso se produciría un desbordamiento. Puede ser mejor tener grillas que tengan al menos 100 píxeles de alto y aún puedan expandirse si se agrega más contenido.

La función **min-max()** nos permite establecer un tamaño mínimo y máximo para una grilla, por ejemplo, min-max(100px, auto). El tamaño mínimo es de 100 píxeles, pero el máximo es auto, que se expandirá para acomodar más contenido.

Las pistas implícitas también se agregan si la cantidad de elementos excede la cantidad de celdas  o cuando un elemento de cuadrícula se coloca fuera de la cuadrícula explícita. De forma predeterminada, el algoritmo de colocación automática coloca los elementos llenando cada fila de forma consecutiva, agregando nuevas filas según sea necesario. Podemos especificar cómo los elementos colocados automáticamente fluyen hacia la cuadrícula usando la propiedad **grid-auto-flow**.  Grid-auto-flow tiene distintos valores: El valor row le dice al algoritmo de colocacion automatica que complete cada fila a su vez, agregando nuevas filas segun sea necesario (predeterminado), column le dice al algoritmo de colocacion automatica que complete cada columna a su vez, agregando nuevas columnas segun sea necesario. Por otra parte, dense le dice al algoritmo de colocacion automatica que intente llenar los agujeros antes en la cuadricula si aparecen elementos mas pequeños mas tarde.

![[Pasted image 20230426230247.png]]
![[Pasted image 20230426230258.png]]

Debido al hecho de que es posible cambiar el tamaño de las celdas automáticamente `grid-auto-rows` y `grid-auto-columns`, no es obligatorio definir una cuadrícula explícita.

## Grid

Esta propiedad es una abreviatura para configurar grid-template-rows, grid-template-columns, grid-templare-areas, grid-auto-rows, grid-auto-columns y grid-auto-flow.

**Nota:** solo puede especificar las propiedades de cuadrícula explícitas o implícitas en una sola declaración de cuadrícula).