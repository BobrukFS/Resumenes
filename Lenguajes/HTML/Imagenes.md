# Imagenes
En la Web, trabajará con dos tipos de imágenes: **imágenes rasterizadas** e **imágenes vectoriales**:

* Las **imágenes ráster** se definen mediante una cuadrícula de píxeles: un archivo de imagen ráster contiene información que muestra exactamente dónde debe colocarse cada píxel y exactamente de qué color debe ser. Los formatos ráster web populares incluyen mapa de bits ( .bmp), PNG ( .png), JPEG ( .jpg) y GIF ( .gif.). Las imagenes JGP no permiten transparencias (No tiene canal alpha). Las imagenes PNG si permiten transparencia (tiene canal alpha). Las imagenes !WEBP, permite animaciones y permite transparencia, y tambien comprime las imagenes para que pesen menos manteniendo la calidad.

* Las **imágenes vectoriales** se basan en fórmulas matemáticas, y no se dividen en unidades mínimas de información como los píxeles, sino en curvas, formas y líneas. Se construyen a partir de **vectores**, que son objetos definidos por una serie de puntos que pueden modificarse para dar una u otra forma a la imagen final. El formato SVG nos permite crear poderosos gráficos vectoriales para usar en la Web. Las imagenes vectoriales son mucho mas escalables y ligeras que las imagenes raster. No pierden calidad ni se pixelean.
	
## Insertar imagenes 

* **`<img>`**: Este elemento inserta una imagen en el documento. El elemento requiere del atributo **src** para especificar la URL del archivo con la imagen que queremos incorporar.

![[Pasted image 20230623142914.png]]

* **`<picture></picture>`**: Este elemento es un contenedor usado para especificar multiples elementos **`<source>`** y un elemento **`<img>`** contenido en el para proveer versiones de una imagen para diferentes escenarios de dispositivos. Si no hay coincidencias con los elementos **`<source>`** , el archivo especificado en los atributos src del elemento img es utilizado.
	
* **`<figure></figure>` y `<figcaption></figcaption`>**: El elemento  **`<figure>`** representa contenido independiente, a menudo con un título. Si bien se relaciona con el flujo principal, su posición es independiente de éste. Por lo general, se trata de una imagen, una ilustración, un diagrama, un fragmento de código, o un esquema al que se hace referencia en el texto principal, pero que se puede mover a otra página o a un apéndice sin que afecte al flujo principal. El **`<figcaption>`** elemento representa un título o leyenda que describe el resto del contenido de su elemento principal. El elemento  dice al navegador, o a alguna tecnologia de apoyo, que el texto que contiene describe la imagen que esta contenida en el elemento **`<figure>`**. Es recomendable utilizar el elemento figure junto con el elemento figcaption para agregar subtitulos a sus imagenes. Asi optimizamos motores de busqueda y sera mas facil para los visitantes web que utilizan lectores de pantalla comprender el contenido de su pagina web.

También puede abrir el archivo SVG en un editor de texto, copiar el código SVG de alguno pagina y pegarlo en su documento HTML; esto a veces se denomina poner su **SVG en línea o insertar SVG** .

**Dato**: Con figma puedo diseñar algo y exportarlo como png, svg, etc y modificarlo.

### Atributos que suelen ir en imagenes

* **src="..."**: El atributo **src** contiene una ruta que apunta a la imagen que se quiere poner en la pagina, que puede ser una URL relativa o absoluta.

* **alt="..."**: El atributo **alt** contiene informacion complementaria si la imagen no carga. Es un texto alternativo. Tambien le da informacion a los buscadores. Tengo que describir la imagen.

* **width="..."**: El atributo **width** determina el ancho de la imagen.

* **height="..."**: El atributo **height** determina la altura de la imagen.

* **title="..."**: El atributo **title** proporciona mas informacion de ayuda si es necesario. [Popper](https://popper.js.org/) le agrega un tooltip a la imagen al pasar con el mouse por encima.

* **srcset="..."**: El atributo **srcset="..."** nos permite especificar una lista de imagenes de diferentes resoluciones que el navegador puede cargar para el mismo elemento.

* **sizes="..."**: El atributo **sizes** especifica una lista de media queries junto con distintos tamaños de imagenes para que el navegador decida que mostrar segun la resolucion de la pantalla.

* **media="..."**: El atributo **media** permite especificar una media query que el agente de usuario evaluara para seleccionar un elemento source. Si la media query evalua false, el elemento source es omitido.

* **loading="..."**: El atributo **loading** especifica como se carga la imagen. Los valores pueden ser **"eager"** (carga inmediata) o **"lazy"** (carga diferida cuando la imagen se acerca al area visible de la pagina).

## Mapa de imagenes

Un mapa de imagen permite definir diferentes zonas "pinchables" dentro de una imagen. El usuario puede clickear sobre cada una de las zonas definidas y cada una de ellas puede apuntar a una URL diferente. Las zonas o regiones que se pueden definir en una imagen se crean mediante rectángulos, círculos y polígonos. Para crear un mapa de imagen, en primer lugar se inserta la imagen original mediante la etiqueta `<img>`. Luego, se utiliza la etiqueta `<map>` para definir las zonas o regiones de la imagen. Cada zona se define mediante la etiqueta `<area>`.

![[Pasted image 20230622222533.png]]

Para crear estos mapas, lo puedo hacer de forma manual o utilizando la siguiente pagina https://www.image-maps.com/.

[[SVG]]