# Imagenes receptivas

Para ello podemos utilizar media queries pero tambien existen los atributos **srcset** y **sizes** para proporcionar varias imágenes de origen adicionales junto con sugerencias para ayudar al navegador a elegir la correcta. El navegador solo descargara la imagen que sea acorde al dispositivo.

* **Srcset :** Este atributo define el conjunto de imágenes entre las que permitiremos que el navegador elija y el tamaño de cada imagen. Cada conjunto de informacion de la imagen esta separada del anterior por una coma. Para cada srcset escribimos : Un nombre de archivo de imagen, dejamos un espacio y escribimos el **ancho intrinseco** (ancho real de la imagen en si) de la imagen en **w** o la densidad de pixeles (1x, 2x, etc. Para ello dividimos la resolucion de la imagen por el ancho del dispositivo, ejemplo 1920/360, da 5.3333 por lo que se va ajustar a aquella imagen que se acerque a 5x). Por ejemplo, en instagram cuando subimos una img, se procesa y la va optimizando por un algoritmo programado por los desarrolladores, que lo que hace es guardar diferentes resoluciones en la base de datos con su URL, asi cuando una persona entra desde X dispositivo, se le enviaran las URL para que cargue la imagen acorde.

* **Sizes:** Este atributo define un conjunto de condiciones de medios e indica que tamaño de imagen seria mejor elegir, cuando ciertas condiciones de medios son verdaderas. En cada sizes escribimos: Una condicion de medios entre parentesis, dejamos un espacio y escribimos el ancho de la ranura que llenara la imagen cuando la condicion sea verdadera, en px.

```html

<!--Utilizando srcset para asignar 3 imagenes dependiendo del ancho intrinseco del dispositivo. -->

   <img src="img/img-original.jpg" alt="Imagen de persona caminando en la ciudad" srcset="img/img-pequeña.jpg 640w,
    img/img-mediana.jpg 1920w,
    img/img-grande.jpg 2400w">
    
<!-- La asignación de 640w, 1920w y 2400w en el atributo "srcset" indica las diferentes opciones de tamaño para la imagen en función del ancho de pantalla del dispositivo. La letra "w" indica el ancho de la imagen en píxeles. - Si el ancho de pantalla es menor o igual a 640 píxeles, se seleccionará la imagen con un ancho de 640 píxeles. - Si el ancho de pantalla está entre 641 y 1920 píxeles, se seleccionará la imagen con un ancho de 1920 píxeles. - Si el ancho de pantalla es mayor que 1920 píxeles, se seleccionará la imagen con un ancho de 2400 píxeles. De esta manera, se asegura que se muestre la imagen con el tamaño adecuado para la pantalla, lo que ayuda a mejorar la velocidad de carga y la calidad de la imagen. -->

<!-- Ejemplo 2 -->

<img src="http://placehold.jp/3840x3840.png" srcset="http://placehold.jp/3840x3840.png 3840w, http://placehold.jp/2048x2048.png 2048w, http://placehold.jp/1920x1920.png 1920w, http://placehold.jp/1200x1200.png 1200w, http://placehold.jp/1080x1080.png 1080w, http://placehold.jp/828x828.png 828w, http://placehold.jp/750x750.png 750w, http://placehold.jp/640x640.png 640w" sizes="(max-width: 480px) 100vw, (max-width: 1024px) 50vw, 33.33vw">
```

**Dato:** Los navegadores más antiguos que no admiten estas funciones simplemente las ignorarán. En su lugar, esos navegadores seguirán adelante y cargarán la imagen a la que se hace referencia en el src atributo de forma normal.

**Dato:** En el `<head>` del documento usted hallará la línea `<meta name="viewport" content="width=device-width">`: esto fuerza a los dispositivos móviles a adoptar su ancho real de ventana para cargar las páginas web (algunos navegadores móviles mienten sobre el ancho de su ventana gráfica y, en su lugar, cargan páginas con un ancho de ventana más grande y luego reducen la página cargada, lo que no es muy útil para imágenes o diseño receptivos).

**Dato:** Las consultas de medios tienen soporte limitado para la densidad de píxeles. Debido a esto, las imágenes no se seleccionarán correctamente en todos los dispositivos y se verán borrosas. Además, a menos que "lazy" cargue las imágenes, el navegador cargará todos los tamaños. (Incluso si están configurados para mostrar: ninguno). Utilizando srcset  no sucede esto.

**Dato**:  La resolucion se refiere a la cantidad de detalle y calidad que tiene la imagen, medida en pixeles. Determina cuantos pixeles se utilizan para representar una imagen en pantalla. Una resolucion mas alta implica una mayor cantidad de pixeles.

**Dato**: En chrome por ejemplo, se utilizan pixeles virtuales, entonces nosotros por consola le podemos el devicePixelRatio mediante window.devicePixelRatio, y el numero que nos de lo multiplicamos por los pixeles virtuales, y eso nos daran los pixeles reales. Ejemplo, tengo un ancho de dispositivo virtual de 390px, y un devicePixelRatio de 3, por lo que el ancho real es 1170px.