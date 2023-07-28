# Modelo de cajas

El modelo de cajas es el comportamiento de CSS que hace que todos los elementos de las páginas sean representados mediante cajas rectangulares.
Cada vez que se inserta un elemento HTML, se crea una nueva caja rectangular que encierra los contenidos de ese elemento. Poniendo a un selector general un borde podemos observar esta representacion.

![[Pasted image 20221204210546.png]]
Los navegadores web crean y colocan las cajas de forma automática, pero CSS permite modificar todas sus características. Cada una de las cajas está formada por seis partes que se describen a continuación:

**1. Content (contenido):** se trata del contenido HTML del elemento (las palabras de un párrafo, una imagen, el texto de una lista de elementos, etc.). El área donde se muestra su contenido, que se puede dimensionar usando propiedades como width y height.

**2. Padding (relleno):** espacio libre opcional existente entre el contenido y el borde.

**3. Border (borde):** línea que encierra completamente el contenido y su relleno.

**4. Background-imagen (Imagen de fondo):** imagen que se muestra por detrás del contenido y el espacio de relleno.

**5. Background-color (color de fondo):** color que se muestra por detrás del contenido y el espacio de relleno.

**6. Margin (margen):** separación opcional existente entre la caja y el resto de cajas adyacentes.

## Box-sizing

* **box-sizing**: Esta propiedad nos permite decidir cómo se calculará el tamaño de un elemento y forzar a los navegadores a incluir el relleno y el borde en el tamaño declarado por la propiedad width. **Por defecto**, el valor de la propiedad box-sizing se declara como **content-box**, lo cual significa que el navegador agregará los valores de las propiedades padding y border al tamaño especificado por la propiedad width. Si en cambio asignamos a esta propiedad el valor **border-box**, el navegador incluye el relleno y el borde como parte del ancho.

![[Pasted image 20221204210750.png]]
Si desea activar el modelo alternativo para un elemento, lo hace configurándolo box-sizing: border-box.  Al hacer esto, le está diciendo al navegador que use el cuadro de borde, como se muestra arriba, como su área definida.

En este el espacio real que ocupara la caja será de 350px de ancho (25px + 25px + 5 + 5 + 290 de width).

![[Pasted image 20221204210837.png]]
## Dimensiones de las cajas

### Width y Height
Por defecto, el tamaño de la mayoría de los elementos se determina según el espacio disponible en el contenedor. El ancho de un elemento se define como 100%, lo cual significa que será tan ancho como su contenedor, y tendrá una altura determinada por su contenido.

#### Width
La propiedad **width** declara el ancho de un elemento. El valor se puede especificar en píxeles, porcentaje, o con la palabra clave auto (por defecto). Cuando el valor se especifica en porcentaje, el ancho se calcula según el navegador a partir del ancho del contenedor, y cuando se declara con el valor auto, el elemento se expande hasta ocupar todo el espacio horizontal disponible dentro del contenedor.

* **width** 

* **max-width** : Esta propiedad especifica el ancho máximo permitido para el elemento. Acepta valores en cualquiera de las unidades disponibles en CSS, como píxeles o porcentajes.

* **min-width** : Esta propiedad especifica el ancho mínimo permitido para el elemento. Acepta valores en cualquiera de las unidades disponibles en CSS, como píxeles o porcentajes.

#### Height
Para los elementos de bloque y las imágenes, la propiedad **height (altura)** permite establecer la altura directamente mediante una medida. Esta propiedad declara la altura de un elemento. El valor se puede especificar en píxeles, porcentaje, o con la palabra clave auto (por defecto). Cuando el valor se especifica en porcentaje, el navegador calcula la altura a partir de la altura del contenedor, y cuando se declara con el valor auto, el elemento adopta la altura de su contenedor.

* **height**

* **max-height** : Esta propiedad especifica la altura máxima permitida para el elemento. Acepta valores en cualquiera de las unidades disponibles en CSS, como píxeles o porcentajes.

* **min-height** : Esta propiedad especifica la altura mínima permitida para el elemento. Acepta valores en cualquiera de las unidades disponibles en CSS, como píxeles o porcentajes.

### Margin
CSS define cuatro propiedades para controlar cada uno de los márgenes horizontales y verticales de un elemento.

1. **margin-top** : Margen superior .

2. **margin-right** : Margen derecho.

3. **margin-bottom** : Margen inferior .

4. **margin-left** : Margen izquierdo.

5. **margin :** Simplificacion para asignar los 4 margenes. Se ponen los valos siguiendo el orden del reloj, empieza por el margen superior.

Cada una de las propiedades establece la separación entre el borde lateral de la caja y el resto de las cajas adyacentes:

![[Pasted image 20221204211659.png]]
Los márgenes verticales (margin-top y margin-bottom) sólo se pueden aplicar a los elementos de bloque y las imágenes, mientras que los márgenes laterales (margin-left y margin-right) se pueden aplicar a cualquier elemento.

Los márgenes top y bottom de los bloques a veces están combinados (colapsados) en un solo margen cuyo tamaño es el tamaño mayor de los márgenes combinados, un comportamiento conocido como **colapso de margen**. Ten en cuenta que los márgenes de elementos flotantes y elementos con posicion absoluta nunca colapsan.

**Tambien se puede alinear elementos con margin**: Con el **margin : auto auto** para centrar. **margin-right: auto** para ponerlo a la izquierda. **margin-left: auto** para ponerlo a la derecha.

**Dato**: Algunos elementos tienen un margen predeterminado.
**Dato**: Se permite valores negativos que desplazaran en sentido contrario
### Relleno o padding
CSS define cuatro propiedades para controlar cada uno de los espacios de relleno horizontales y verticales de un elemento:

1. **Padding-top** : Relleno superior
2. **Padding-right** : Relleno derecho
3. **Padding-bottom** : Relleno inferior
4. **Padding-left** : Relleno izquierdo
5. **Padding** : Simplificacion para asignar los 4 paddings.

![[Pasted image 20221204212011.png]]
![[Pasted image 20221204212019.png]]

**Dato:** Algunos elementos tienen un padding predeterminado.

### Border

Permite implementar bordes a un elemento.

##### Para configurar las propiedades de cada lado individualmente, puede usar:

* **border-top**

* **border-right**

* **border-bottom**

* **border-left**

Para configurar las propiedades de cada lado de manera simplificada se puede hacer de la siguiente manera por ejemplo:

* **border-width = 10px(top) 10px(right) 10px(bottom) 10px(left) ;**

##### Para establecer el ancho, el estilo o el color de todos los lados, use lo siguiente:

* **border-width**

* **border-style**

* **border-color**

Shorthand para aplicar un ancho, estilo y color al borde

* **border : 10px solid black;**

Para establecer el ancho, el estilo o el color de un solo lado, se puede utilizar por ejemplo esto:

* **border-top-width.**

##### Para asignarle el radio al borde:

* **border-radius**

Se pueden utilizar dos longitudes o porcentajes como valor, definiendo el primer valor el radio horizontal y el segundo el radio vertical. Es decir, superior izquierda superior derecha inferior derecha inferior izquierda. En muchos casos, solo pasará un valor, que se utilizará para ambos. O para hacer que la esquina superior derecha tenga un radio horizontal de 1em y un radio vertical del 10%.

![[Pasted image 20221204212427.png]]

Tambien puedo asignar un radio con eje X/Y. Donde "X" representa el radio horizontal y "Y" representa el radio vertical de las esquinas. Puedes usar valores absolutos como píxeles (px) o unidades relativas como porcentaje (%) para definir los radios.

```CSS
border-radius: 10px 10px 20px 20px/20px; /* Radio horizontal de 10px para la esquina superior izquierda y derecha, y 20px para la esquina superior izquierda y derecha y radio vertical de 20px */
border-radius: 50%/50%; /* Radio circular con un radio del 50% */
border-radius: 0/50%; /* Esquinas horizontales rectas y esquinas verticales redondeadas */
```


Para sacarle el borde utiliza **border: none**.

##### Bordes personalizados con imágenes

* **border-image-source** : Esta propiedad determina la imagen que se usará para crear elborde. La URL del archivo se declara con la función url() (por ejemplo, url("ladrillos.jpg")).

* **border-image-width** : Esta propiedad define el ancho del borde. Acepta valores en cualquiera de las unidades disponibles en CSS (px, %, em, etc.).

* **border-image-repeat** : Esta propiedad define cómo se usa la imagen para generar el borde. Los valores disponibles son repeat, round, stretch, y space.

* **border-image-slice** : Esta propiedad define cómo se va a cortar la imagen para representar las esquinas del borde. Debemos asignar cuatro valores para especificar los cuatro trozos de la imagen que se utilizarán (si solo se declara un valor, se usa para todos los lados). El valor se puede especificar como un entero o en porcentaje.

* **border-image-outset** : Esta propiedad define el desplazamiento del borde (la distancia a la que se encuentra de la caja del elemento). Acepta valores en cualquiera de las unidades disponibles en CSS (px, %, em, etc.).

* **border-image** : Esta propiedad nos permite especificar todos los atributos del borde al mismo tiempo.

### Outline(Contorno)

Un outline es una línea que se dibuja alrededor de los elementos (fuera de las fronteras) para hacer que el elemento "stand out" .

Sin embargo, el outline propiedad es diferente de la propiedad border. El outline no es una parte de las dimensiones de un elemento; total de anchura y la altura del elemento no se ve afectada por el ancho del contorno.

* **outline-width** : Esta propiedad define el ancho del borde. Acepta valores en cualquiera de las unidades disponibles en CSS (px, %, em, etc.) y también las palabras clave thin, medium, y thick.

* **outline-style** : Esta propiedad define el estilo del borde. Los valores disponibles son none, auto, dotted, dashed, solid, double, groove, ridge, inset, y outset.

* **outline-color** : Esta propiedad define el color del borde.

* **outline-offset** : Esta propiedad define el desplazamiento (a qué distancia de los límites de la caja se dibujará el segundo borde). Acepta valores en cualquiera de las unidades disponibles en CSS (px, %, em, etc.).

* **outline** : Esta propiedad nos permite especificar el ancho, estilo y color del borde al mismo tiempo (el desplazamiento aún se debe definir con la propiedad outline-offset).

![[Pasted image 20221204212948.png]]
## Desbordamiento
Todo en CSS es una caja. Puede restringir el tamaño de estos cuadros asignando valores de width y height (o **inline-size** y **block-size**). El desbordamiento ocurre cuando hay demasiado contenido para caber en una caja. CSS proporciona varias herramientas para administrar el desbordamiento.

![[Pasted image 20221208112216.png]]
Siempre que sea posible, CSS no oculta el contenido. Esto provocaría la pérdida de datos. El problema con la pérdida de datos es que es posible que no lo notes. CSS se desborda de manera visible. Es más probable que vea que hay un problema. En el peor de los casos, un visitante del sitio le informará que el contenido se superpone.

Si restringe un cuadro con a width o a height, CSS confía en que sabrá lo que está haciendo. CSS asume que está administrando el potencial de desbordamiento. En general, restringir la dimensión del bloque es problemático cuando el cuadro contiene texto. Puede haber más texto del que esperaba al diseñar el sitio, o el texto puede ser más grande.

### Overflow
La propiedad **overflow** es cómo tomas el control del desbordamiento de un elemento. Es la forma en que le indica al navegador cómo debe comportarse. Los valores que puede tomar dicha propiedad son:

* **visible** : Es el valor predeterminado de desbordamiento. Con este valor predeterminado, podemos ver el contenido cuando se desborda.

![[Pasted image 20221208112348.png]]

* **hidden** : Sirve para recortar el contenido cuando se desborda, lo que hace es ocultar el desbordamiento.

* **auto**: El contenedor toma el tamaño del elemento mas grande.

* **scroll** : Mostraran el contenido con barras de desplazamiento visibles, incluso si no hay suficiente contenido para desbordar. Podemos usar **overflow-y: scroll** para desplazarnos en el eje y solamente o **overflow-x: scroll** para desplazarnos en el eje x solamente (Si tiene una palabra larga en un cuadro pequeño, podría considerar usar las propiedades **word-break** o **overflow-wrap** antes que el desplazamiento en el eje x). Si solo desea que aparezcan las barras de desplazamiento cuando hay más contenido del que cabe en el cuadro, utilice **overflow: auto**. Esto permite que el navegador determine si debe mostrar barras de desplazamiento.

	**Dato** : Cuando usa un valor de desbordamiento como scroll o auto, crea un contexto de formato de bloque (BFC). El contenido del cuadro cuyo valor ha cambiado overflow adquiere un diseño independiente. El contenido fuera del contenedor no puede asomarse al contenedor, y nada puede asomarse de ese contenedor al diseño circundante.

La propiedad **overflow-wrap**  indica si un palabra debería ser dividida en un punto arbitrario cuando no hay suficiente espacio para mostrarla en la línea. Los valores disponibles son normal (la línea será dividida naturalmente) y break-word (las palabras se dividirán en puntos arbitrarios para acomodar la línea de texto en el espacio disponible).

**Dato:** Los navegadores en los dispositivos móviles ignoran el overflow-x: hidden interior de la etiqueta body por lo que es mejor aplicar el overflow-x: hidden en la etiqueta html y body.

#### Resize

La propiedad **resize** modifica como se ven elementos con contenido mayor a su contenedor. Los valores posibles de resize son horizontal, vertical, both y none.