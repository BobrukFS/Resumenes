# Cosas que no tienen que faltar al iniciar CSS
Tenemos que vincular el archivo normalize.css al html(se copia de la pagina y se pega en una hoja de estilos normalize.css). Esto va hacer que los navegadores representen todos los elementos de manera mas consistente ya que estamos reseteando CSS.

También pongo esto:

![[Pasted image 20221214120734.png]]

La propiedad `box-sizing: border-box` establece el modelo de caja a utilizar en todos los elementos de la página, lo que significa que el ancho y alto de un elemento incluirá su relleno y borde, en lugar de sumarse a él.

La regla `*, *:before, *:after {box-sizing: inherit}` establece que todos los elementos, incluyendo los pseudo-elementos `before` y `after`, hereden el valor `box-sizing` del elemento padre. En este caso, todos los elementos heredarán el valor `border-box` establecido en la regla `html {box-sizing: border-box}`, lo que significa que el ancho y alto de los elementos incluirá su borde y relleno.

En resumen, la combinación de estas dos reglas garantiza que el modelo de caja `border-box` se utilizará en toda la página, incluyendo en elementos que se agreguen posteriormente, como nuevos componentes o widgets.
Donde:


-font-size: 62,5% : Hace que 1rem sea 10px

También podemos agregar en el body un Font-size : 16px; para que se tome como referencia.

**Para buscar mas estilos, etc podemos buscar en la documentación oficial especialmente en la pagina de referencias.**