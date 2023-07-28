# Display flex
Flex es un método de diseño unidimensional para organizar elementos en filas o columnas. Los elementos se flexionan (expanden) para llenar espacio adicional o se encogen para caber en espacios más pequeños.

Cuando los elementos se disponen como elementos flexibles, se disponen a lo largo de dos ejes:

![[Pasted image 20221213154040.png]]
### Flex-direction

Flexbox proporciona una propiedad denominada **flex-direction** que especifica en qué dirección corre el eje principal (en qué dirección se disponen los hijos de flexbox). De forma predeterminada, está configurado en **row (como se ve en la imagen de arriba)**, lo que hace que se coloquen en una fila en la dirección en la que funciona el idioma predeterminado de su navegador (de izquierda a derecha). Se puede diseñar elementos flexibles con dirección **column** (arriba hacia abajo). También puede diseñar elementos flexibles en una dirección inversa utilizando los valores **row-reverse y  column-reverse**.

### Envase(wrap)

De forma predeterminada, todos los elementos flexibles intentarán encajar en una línea.

Un problema que surge cuando tiene un ancho o una altura fijos en su diseño es que, eventualmente, sus elementos secundarios flexbox desbordarán su contenedor, rompiendo el diseño.

La propiedad **flex-wrap** establece si los elementos flexibles se fuerzan en una línea o se pueden ajustar en varias líneas. Si se permite el ajuste, establece la dirección en que se apilan las líneas.

![[Pasted image 20221213204925.png]]
![[Pasted image 20221213204929.png]]
Se puede abreviar la sintaxis de flow-direction y flex-wrap con **flex-flow**:

![[Pasted image 20221213205003.png]]

### Tamaño flexible de elementos flexibles

**Flex** es una propiedad abreviada que puede especificar hasta tres valores diferentes:

* **Flex-grow**:  Esta propiedad declara la proporcion en la que se va a distribuir el espacio restante luego de haber asignado el tamaño predeterminado mediante flex-basis. La proporción se determina considerando los valores asignados al resto de los elementos de la caja. Por ejemplo si a un elemento le asignamos un valor de 2, y al otro un valor de 1, el que tiene un valor 2 ocuparia el doble de espacio que el que tiene el valor de 1. El flex-grow de cada elemento es como default 0. Si nosotros tenemos un elemento con flex-grow 0 y otro con flex-grow 1, el elemento con flex-grow 1 va ocupar todo el espacio.

*  **Flex-shrink**: Este valor especifica cuánto se reducirá un elemento para evitar el desbordamiento. Si el tamaño de todos los elementos flexibles es mayor que el contenedor flexible, los elementos se contraen para ajustarse. El flex-shrink de cada elemento es como default 1. Si ponemos flex-shrink 0 el elemento ocupara todo el contenedor.

* **Flex-basis**: Define el tamaño predeterminado de un elemento antes de que se distribuya el espacio restante, es decir, antes que se aplique flex-grow y flex-shrink. Si se establece en 0, el espacio adicional alrededor del contenido no se tiene en cuenta. Si se establece en auto, el espacio adicional se distribuye en funcion del valor flex-grow. Flex-basis se suele utilizar para evitar utilizar width y establecer un tamaño predeterminado de un elemento o varios elementos.

Ejemplo:

![[Pasted image 20221213205803.png]]

Donde 1 rem es la separación. También para separar se puede utilizar la propiedad **gap**.

### Alineación horizontal y vertical

#### Alineacion horizontal

* **justify-content** : Controla dónde se ubican los elementos flexibles en el eje principal. Los valores disponibles son flex-start, flex-end, center, space-around, y space-between.

* **margin** : Puedo utilizar margin para alinear por ejemplo, margin-left: auto y margin-right: 0, alinea hacia la derecha. 

#### Alineacion vertical

* **align-items** : Esta propiedad alinea las cajas en el eje transversal en la linea actual. Los valores disponibles son flex-start, flex-end, center, baseline, y stretch (default, se estira el eje secundario ocupando todo el contenedor).

* **align-self :** Esta propiedad alinea una caja en el eje transversal. Trabaja como align items pero afecta cajas de forma individual. Los valores disponibles son auto, flexstart, flex-end, center, baseline, y stretch. Esto permite anular la alineacion predeterminada (o la especificada por align-items) para elementos flexibles individuales.

* **align-content :** Esta propiedad alinea las líneas de cajas en el eje vertical.  No tiene efecto cuando los elementos estan en una sola linea. Los valores disponibles son flex-start, flex-end, center, space-between, space-around, y stretch.

### Ordering flex items

Flexbox también tiene una función para cambiar el orden de diseño de los elementos flexibles sin afectar el orden de origen.

![[Pasted image 20221213210109.png]]
Puede establecer valores de orden negativos para que los elementos aparezcan antes que los elementos cuyo valor es 0.

### Gap

La propiedad **gap** controla explicitamente el espacio entre elementos flexibles.

### Cajas flexibles anidadas

Es posible crear algunos diseños bastante complejos con flexbox. Está perfectamente bien configurar un elemento flexible para que también sea un contenedor flexible, de modo que sus elementos secundarios también se presenten como cajas flexibles.

Ejemplo:

![[Pasted image 20221213210210.png]]