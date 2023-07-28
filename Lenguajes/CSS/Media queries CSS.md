# Media queries CSS

Las consultas de medios son una parte clave del diseño web receptivo, ya que permite crear diferentes diseños según el tamaño de la ventana gráfica, pero también se pueden usar para detectar otras cosas sobre el entorno en el que se ejecuta su sitio, por ejemplo, si el el usuario está usando una pantalla táctil en lugar de un mouse. Un sitio optimo tiene 5 media queries o mas.

El uso de mediaqueria sirve para crear macro-layouts como tambien micro-layouts.

En el media query solo ira lo que se quiere modificar del estilo del elemento al modificar el tamaño del dispositivo, ya que las otras propiedades se heredan.

La sintaxis de consulta de medios más simple se ve así:

![[Pasted image 20221214120124.png]]

Donde **media-type** es el tipo de medias, o mismo se puede omitir para que se aplique en todos los medios, y **media-feature-rule** es la condicion multimedia que se debe pasar para que se apliquen las reglas sccs

## Media types

Los posibles tipos de medios que puede especificar son:

* **All :** Las propiedades se aplican en todos los medios.

* **Print :** Las propiedades se aplican cuando la pagina web se envia a una impresora.

* **Screen :** Las propiedades se aplican cuando la pagina web se muestra en una pantalla color.

* **Speech :** Las propiedades se aplican cuando la pagina web se procesa por un sintetizador de voz.

**Nota:** los tipos de medios son opcionales; si no indica un tipo de medio en su consulta de medios, la consulta de medios será predeterminada para todos los tipos de medios.

## Media features

Puede agregar condiciones a los tipos de medios. Estas se llaman consultas de medios. El CSS se aplica solo si el tipo de medio coincide y la condición también es verdadera. Estas condiciones se denominan media features.

#### Ancho de la ventana grafica

La característica que tendemos a detectar con más frecuencia para crear diseños receptivos (y que tiene un amplio soporte de navegador) es el **ancho de la ventana gráfica**, y podemos aplicar CSS si la ventana gráfica está por encima o por debajo de un cierto ancho, o un ancho exacto, usando el **min-width, max-width y width** como funciones multimedia. Las funciones de medios width(y height) se pueden usar como rangos y, por lo tanto, pueden tener el prefijo min-o max-para indicar que el valor dado es un mínimo o un máximo. En la práctica, usar valores mínimos o máximos es mucho más útil para el diseño receptivo, por lo que rara vez verá width o height se usará solo.

Ejemplo : 

![[Pasted image 20221214121847.png]]

#### Orientacion

Una función de medios bien admitida es **orientation**, que nos permite probar el modo vertical u horizontal. Para cambiar el color del texto del cuerpo si el dispositivo está en orientación horizontal, use la siguiente consulta de medios. Una vista de escritorio estándar tiene una orientación horizontal y un diseño que funciona bien en esta orientación puede no funcionar tan bien cuando se ve en un teléfono o tableta en modo vertical. La prueba de orientación puede ayudarlo a crear un diseño optimizado para dispositivos en modo vertical.

Ejemplo : 

![[Pasted image 20221214121933.png]]

#### Use of pointing devices

La función multimedia **hover**  significa que puede probar si el usuario tiene la capacidad de pasar el mouse sobre un elemento, lo que esencialmente significa que está usando algún tipo de dispositivo señalador; la pantalla táctil y la navegación con teclado no se desplazan. Si sabemos que el usuario no puede desplazarse, podríamos mostrar algunas funciones interactivas de forma predeterminada. Para los usuarios que pueden pasar el mouse, podemos elegir que estén disponibles cuando se pasa el mouse sobre un enlace.

Ejemplo : 

![[Pasted image 20221214122035.png]]

### Consultas de medios mas complejas

**Lógica "y" en consultas de medios**

Para combinar funciones de medios, puede usar **and**.Por ejemplo, podríamos querer probar para a min-width y orientation. El cuerpo del texto solo será azul si la ventana gráfica tiene al menos 600 píxeles de ancho y el dispositivo está en modo horizontal.

**Lógica "o" en consultas de medios**

Si tiene un conjunto de consultas, cualquiera de las cuales podría coincidir, entonces puede separarlas con **comas**. En el siguiente ejemplo, el texto será azul si la ventana gráfica tiene al menos 600 píxeles de ancho O si el dispositivo está en orientación horizontal. Si alguna de estas cosas es verdadera, la consulta coincide.

![[Pasted image 20221214122233.png]]
**Lógica "no" en consultas de medios**

Puede negar una consulta de medios completa utilizando el operador not. Esto invierte el significado de toda la consulta de medios. Por lo tanto, en el siguiente ejemplo, el texto solo será azul si la orientación es vertical.

![[Pasted image 20221214122302.png]]
## Como elegir puntos de interrupcion

![[Pasted image 20230705161916.png]]

## ¿Como trabajar con Media queries?
Podemos poner muchos selectores en un mismo media querie o poner un media querie para cada selector. La primer practica es la recomendada.

![[Pasted image 20221214122821.png]]

https://developer.mozilla.org/es/docs/Web/CSS/CSS_media_queries/Using_media_queries