# Posicionamiento

La propiedad **position** nos va a permitir seleccionar el tipo de posicion del elemento, esta puede tener varios valores : 

* **static**

* **relative**

* **absolute**

* **fixed**

* **sticky**

Las propiedades **top, bottom, left y right** se utilizan junto position para especificar exactamente a dónde mover el elemento posicionado.

* **top** : Esta propiedad especifica la distancia entre el margen superior del elemento y el margen superior de su contenedor.

* **bottom** : Esta propiedad especifica la distancia entre el margen inferior del elemento y el margen inferior de su contenedor.

* **Left** : Esta propiedad especifica la distancia entre el margen izquierdo del elemento y el margen izquierdo de su contenedor.

* **right** : Esta propiedad especifica la distancia entre el margen derecho del elemento y el margen derecho de su contenedor.

## Posicionamiento static

El **posicionamiento estático** es el valor predeterminado que obtiene cada elemento. Simplemente significa "colocar el elemento en su posición normal en el flujo del documento”.

La única razón por la que alguna vez configuraría un elemento `position: static;`es para eliminar a la fuerza algún posicionamiento que se aplicó a un elemento fuera de su control. Esto es bastante raro, ya que el posicionamiento no se produce en cascada. No funcionan las propiedades de posicionamiento cuando el elemento tiene este tipo de posicionamiento.

## Posicionamiento relative

Esto es muy similar al posicionamiento estático, excepto que una vez que el elemento posicionado ha ocupado su lugar en el flujo normal, puede modificar su posición final, incluso hacer que se superponga a otros elementos en la página. Para ello utilizamos las propiedades Top, bottom, left y right que actúan colocando el elemento en función de su posición relativa dentro del flujo de documentos normal (es decir, las coordenadas se fijan en referencia a si mismo). Los elementos relativos se utilizan como padres para los absolutos hijos.

Ademas introduce la capacidad de usar z-index.

La otra cosa que sucede es que **limita el alcance de los elementos secundarios absolutamente posicionados** . Cualquier elemento que sea hijo del elemento relativamente posicionado puede estar absolutamente posicionado dentro de ese bloque.

### z-index

**¿Puedes cambiar el orden de apilamiento?** Sí, puedes, usando la propiedad **z-index**. "z-index" es una referencia al eje z.

Las páginas web también tienen un **eje z**: una línea imaginaria que va desde la superficie de tu pantalla hacia tu cara (o cualquier otra cosa que quieras tener frente a la pantalla). Los valores  z-index afectan dónde se ubican los elementos posicionados en ese eje; los valores positivos los mueven más arriba en la pila, los valores negativos los mueven más abajo en la pila. De forma predeterminada, todos los elementos posicionados tienen un valor z-index de auto, que es efectivamente 0. Tenga en cuenta que z-index solo acepta valores de índice sin unidades.

## Posicionamiento absolute

Un elemento absolutamente posicionado ya no existe en el flujo normal. Un elemento con este tipo de posicionamiento no se ve afectado por otros elementos y no afecta a otros elementos. Esto es muy útil: significa que podemos crear funciones de interfaz de usuario aisladas que no interfieren con el diseño de otros elementos de la página. Por ejemplo, cuadros de información emergentes, menús de control, paneles dinámicos, características de la interfaz de usuario que se pueden arrastrar y soltar en cualquier parte de la página, etc.

En lugar de colocar el elemento en función de su posición relativa dentro del flujo de documentos normal, especifican la distancia que debe estar el elemento desde cada uno de los lados del elemento relativo mas cercano que lo contiene.

Si ningún elemento ancestro tiene su propiedad de posición definida explícitamente, entonces todos los elementos ancestro tendrán una posición estática por defecto. El resultado de esto es que el elemento absolutamente posicionado estará contenido en el bloque contenedor inicial . El bloque contenedor inicial tiene las dimensiones de la ventana gráfica y también es el bloque que contiene el elemento `<html>`. En otras palabras, el elemento absolutamente posicionado se mostrará fuera del elemento `<html>` y se ubicará en relación con la ventana gráfica inicial. **Se cumple que el elemento absoluto se posiciona con respecto al elemento relativo más cercano.**

Su uso excesivo o inadecuado puede limitar la flexibilidad de su sitio.

Ademas introduce la capacidad de usar z-index.

## Posicionamiento fixed

Esto funciona exactamente de la misma manera que el posicionamiento absoluto, con una diferencia clave: mientras que el posicionamiento absoluto fija un elemento en un lugar en relación con su ancestro relativo posicionado más cercano (el bloque contenedor inicial si no lo hay), el **posicionamiento fijo** generalmente fija un elemento en un  lugar en relación con la parte visible de la ventana gráfica. (Se produce una excepción a esto si uno de los ancestros del elemento es un bloque contenedor fijo porque su propiedad transform tiene un valor distinto de none ) siempre visible sin importar cuánto se desplace la página. (Es decir puede ser un menú que al desplazar la pagina hacia abajo lo podemos seguir viendo).

## Posicionamiento sticky

Esto es básicamente un híbrido entre posición relativa y fija. Permite que un elemento posicionado actúe como si estuviera relativamente posicionado hasta que se desplace a un cierto umbral.

Los elementos pegajosos son "pegajosos" en relación con el antepasado más cercano con un "mecanismo de desplazamiento", que está determinado por la propiedad de posición de sus antepasados .