# Estilo de texto
Las propiedades CSS que se utilizan para diseñar el texto generalmente se dividen en dos categorías:

* **Estilos de fuente:** propiedades que afectan la fuente de un texto, por ejemplo, qué fuente se aplica, su tamaño y si está en negrita, cursiva, etc.

* **Estilos de diseño de texto:** propiedades que afectan el espaciado y otras características de diseño del texto, lo que permite manipular, por ejemplo, el espacio entre líneas y letras, y cómo se alinea el texto dentro del cuadro de contenido.

**Dato**: Los párrafos se van a expandir al ancho de sus contenedores. Para que no haga eso, puedes intentar utilizar display inline-block o utilizar width: fit-content. 
## Estilos de fuente

* **font-family:** Esta propiedad sirve establecer una fuente diferente para su texto; esto le permite especificar una fuente (o una lista de fuentes) para que el navegador la aplique a los elementos seleccionados. El navegador solo aplicará una fuente si está disponible en la máquina desde la que se accede al sitio web; si no, solo usará una fuente predeterminada del navegador o la siguiente de la lista. Se pueden declarar múltiples valores separados por coma.

**Fuentes externas**

Para utilizar una familia de fuente externa se vincula con el `<link>` en el html con la pagina de la fuente en el HTML. O tambien las podemos importar. Al utilizar @import en nuestro proyecto al colocarse en un archivo CSS, en caso de cualquier cambio, no tenemos que cambiar todos nuestros archivos HTML como si sucederia en el caso de utilizar link, si no que tenemos que cambiar solamente el archivo CSS que esta vinculado a todos nuestros archivos HTML.


![[Pasted image 20221209214308.png]]
Tambien tenemos **@font-face** que permite al autor especificar fuentes online para visualizar en sus páginas web. Al permitir a los autores proporcionar sus propias fuentes, @font-face elimina la necesidad de depender del numero limitado de fuentes de usuarios instaladas en sus computadoras.

![[Pasted image 20221209214336.png]]

**Dato**: Tambien podemos tener fuentes locales.

* **font-size :** Este se utiliza para establecer el tamaño de un texto. El **font-size** de un elemento se hereda del elemento padre de ese elemento. Todo esto comienza con el elemento raíz de todo el documento (etiqueta html), cuyo estándar font-size se establece en 16 px en todos los navegadores. Cualquier párrafo (u otro elemento que no tenga un tamaño diferente establecido por el navegador) dentro del elemento raíz tendrá un tamaño final de 16 px.

* **font-Style :** La propiedad **font-Style** se utiliza para activar o desactivar el texto en cursiva. Los valores posibles son los siguientes: **normal:** Establece el texto en la fuente normal (desactiva la cursiva existente). **italic:** configura el texto para usar la versión en cursiva de la fuente, si está disponible; si no, simulará cursiva con oblicua en su lugar. **oblique:** configura el texto para usar una versión simulada de una fuente en cursiva, creada inclinando la versión normal.

* **font-Weight :** Esta propiedad determina si el texto se mostrará en negrita o no. Los valores disponibles son normal y bold, pero también podemos asignar los valores 100, 200, 300, 400, 500, 600, 700, 800, y 900 para determinar el grosor de la letra (solo disponibles para algunos tipos de letra).

* **font :** Esta propiedad nos permite declarar múltiples valores al mismo tiempo. Los valores deben declararse separados por un espacio y en un orden preciso. El estilo y el grosor se deben declarar antes que el tamaño, y el tipo de letra al final (por ejemplo, font: bold 24px Arial,sans-serif).
## Estilo de diseño de texto

* **text-transform :** Permite configurar su fuente para que se transforme. Los valores incluyen: **none:** Evita cualquier transformación. **uppercase:** Transforma todo el texto a mayúsculas. **lowercase:** Transforma todo el texto a minúsculas. **capitalize:** Transforma todas las palabras para tener la primera letra en mayúscula.

* **text-decoration :** Establece/desestablece las decoraciones de texto en las fuentes. Los valores disponibles son: **none:** anula cualquier decoración de texto que ya esté presente.**underline:** Subraya el texto. **overline:** Le da al texto una línea superior. **line-through:** Pone un tachado sobre el texto. Debe tener en cuenta que text-decoration puede aceptar varios valores a la vez si desea agregar varias decoraciones simultáneamente, por ejemplo, text-decoration: underline overline. También tenga en cuenta que text-decoration es una propiedad abreviada para **text-decoration-line**, **text-decoration-color**  y **text-decoration-style**. 

* **text-shadow:** Sirve para aplicar sombras paralelas a su texto usando la propiedad **text-shadow**. Esto toma hasta cuatro valores.

![[Pasted image 20221209214737.png]]
![[Pasted image 20221209214743.png]]
![[Pasted image 20221209214750.png]]
Puede aplicar varias sombras al mismo texto incluyendo varios valores de sombra separados por comas

![[Pasted image 20221209214802.png]]

* **text-Align:** La text-align propiedad se utiliza para controlar cómo se alinea el texto dentro del cuadro de contenido que lo contiene. Los valores disponibles se enumeran a continuación. **left:** Justifica el texto a la izquierda. **right:** Justifica el texto a la derecha. **center:** centra el texto. **justify:** hace que el texto se extienda, variando los espacios entre las palabras para que todas las líneas de texto tengan el mismo ancho. Debe usar esto con cuidado: puede verse terrible, especialmente cuando se aplica a un párrafo con muchas palabras largas. Si va a usar esto, también debe pensar en usar algo más junto con él, como **hyphens**, para dividir algunas de las palabras más largas en líneas.

* **vertical-align :** Esta propiedad alinea elementos verticalmente. Se usa frecuentemente para alinear texto con imágenes (la propiedad se aplica a la imagen). Los valores disponibles son baseline, sub, super, text-top, text-bottom, middle, top, y bottom.

* **line-height:** Esta propiedad define el espacio entre líneas. Se recomienda usar unidades sin medida.

* **letter-spacing :** Esta propiedad define el espacio entre letras.

* **word-spacing :** Esta propiedad define el ancho del espacio entre palabras.
## Modos de escritura
Un modo de escritura en CSS se refiere a si el texto se ejecuta horizontal o verticalmente. La propiedad **writing-mode** nos permite cambiar de un modo de escritura a otro.

![[Pasted image 20221209214954.png]]
La dimensión del bloque es siempre la dirección en que se muestran los bloques en la página en el modo de escritura en uso. La dimensión en línea es siempre la dirección en que fluye una oración.

![[Pasted image 20221209215008.png]]
![[Pasted image 20221209215023.png]]

Se llama a la propiedad asignada width cuando está en un modo de escritura horizontal **inline-size**: se refiere al tamaño en la dimensión en línea. La propiedad para height se nombra **block-size** y es el tamaño en la dimensión del bloque. Puede ver cómo funciona esto en el siguiente ejemplo donde hemos reemplazado width con inline-size.

**Dato:** Si no está utilizando múltiples modos de escritura, por ahora puede preferir usar las propiedades físicas. Sin embargo, si se utilizan muchos modos de escritura dependiendo el pais, conviene mejor utilizar las [propiedades logicas](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties). 

