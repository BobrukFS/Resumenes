# Responsive web 

El maquetado web responsivo (en inglés, Responsive Web Design) es una técnica de diseño y desarrollo web que mediante el uso de estructuras, grillas e imágenes y videos fluidos, así como la utilización de Media Query desde CSS, para adaptar el sitio web al entorno del usuario. Es decir se utiliza el **diseño adaptable** y **diseño fluido**.

Las ventajas de trabajar con diseños responsivos, en sí es que cualquier usuario puede acceder desde cualquier dispositivo y entender el contenido, lo cual genera mayor conversión ya sea de servicios, o de productos.

Las ventajas son:
* Mejora la experiencia del usuario (usabilidad y conversión). 
* Mejora mantenimiento. 
* Evita contenido duplicado. 
* Mejora el posicionamiento web.

Para realizar un diseño responsive:

* diseño flex
* diseño grid
* fluid media
* media queries

## Diseño adaptable vs Sitios separados vs Diseño fluido

### Diseño adaptable

Existe la posibilidad de generar un solo diseño mediante el **diseño adaptable** y que éste sea tomado en múltiples pantallas trabajando en css. Esto se consigue mediante el uso de mediaqueries.

### Sitios separados

Se generan diferentes templates o diseños dependiendo la pantalla a través de un código de JavaScript que detecte el tamaño del dispositivo, por lo que se diseña una pagina para cada dispositivo. Esto tiene como consecuencia que debamos mantener diferentes bases de codigo y diseños por separado.

Si bien es una decisión posible, es importante mencionar que actualmente la tendencia es tener un solo diseño que sea responsivo para varios medios o tamaños de pantalla.

### Diseño fluido

Existen otros tipos de diseños, como por ejemplo el **diseño fluido o líquido.** En este tipo de diseño se usan porcentajes en vez de pixeles u otras medidas de longitud como em, rem, o ex, para que los elementos se adapten según el ancho de la pantalla. Si bien el resultado puede parecer atractivo en pantallas medianas, como computadores de escritorio y tablets, se producen muchos problemas en las pantallas grandes y pequeñas, es decir, en los extremos. Se suelen utilizar funciones como clamp y calc para ser mas especificos.

## Viewport

La **ventana grafica**(viewport) es el area visible del usuario de una pagina web. La ventana grafica varia segun el dispositivo. Esta se puede configurar a traves de la etiqueta `<meta>`.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!--Width=device-width establece el ancho de la pagina para que sea el mismo ancho que el de la pantalla del dispositivo(que variaria segun el dispositivo).

initial-scale=1.0 establece el nivel de zoom inicial cuando el navegador carga la pagina por primera vez. Es decir, escala, cuando hacemos responsive web deseamos que no se haga escala.

minimun-scale: Maximo zoom que se puede realizar a la pagina del 1 al 10.
maximum-scale: Minimo zoom que se puede realizar a la pagina del 1 al 10.
user-scalabe: Define si el usuario podra o no hacer zoom sobre la pagina

-->
```

![[Pasted image 20230427101117.png]]

## Breakpoints

Los breakpoints son bloques de diseño responsivo. Es importante su utilizacion para controlar o adaptar la interfaz a un tamaño de pantalla especifico.

![[Pasted image 20230715133221.png]]

## Media

Con el elemento `<link>` y el atributo media podemos cargar diferentes hojas de estilo para cada situacion, pero cuando solo se modifican unas pocas propiedades, podemos incluir todas en la misma hoja de estilo y definir las Media Queries con la regla @media.

![[Pasted image 20221214115629.png]]

**Dato:** El navegador bloquea la representación hasta que analiza todos estos estilos, pero no bloqueará la representación en estilos que sabe que no usará, como las hojas de estilo impresas. Al dividir el CSS en varios archivos en función de las consultas de medios, puede evitar el bloqueo de procesamiento durante la descarga de CSS no utilizado. Para crear un enlace CSS que no bloquee, mueva los estilos que no se usan inmediatamente, como los estilos de impresión, a un archivo separado, agregue un `<link>` al marcado HTML y agregue una consulta de medios, en este caso indicando que es una hoja de estilo de impresión.


## Mobile first vs desktop first

Siempre hay que empezar a diseñar dispositivos moviles primero antes de diseñar para computadoras de escritorio o cualquier otro dispositivo. Antes se utilizaba desktop first pero ahora se utilizan mas moviles por lo que quedo anticuado.

![[Pasted image 20230705141406.png]]

## Internalizacion

### Propiedades logicas

Las propiedades logicas se adaptan a cualquier modo de escritura y por lo tanto a cualquier idioma, a diferencia de las propiedades fisicas. Estas propiedades se enfocan en declarar una posicion segun la posicion del contenedor y no un lado arbitrario. Por ejemplo, en vez de hacer un margin-left (margen de izquierda) hacemos margin-inline-start, u otro ejemplo en vez de hacer padding-top hacemos padding-block-start. Entonces si esa página se traduce a un idioma de derecha a izquierda, no será necesario actualizar los estilos.

* property-inline-start: Lado fisico izquierdo de una caja
* property-inline-end:  Lado fisico derecho de una caja
* property-block-start: Lado fisico arriba de una caja
* property-block-end: Lado fisico abajo de una caja

Utilizar flexbox o grid facilita esto ya que utiliza propiedades logicas.

**Dato**: Utilizando el atributo dir en el elemento html y poniendole un valor ltr podemos ver el modo de escritura de izquierda a derecha. El predeterminado para los occidentales es rtl.

### Identificar el idioma de la pagina

Para identificar el idioma de una pagina podemos utilizar el atributo **lang** en el elemento html. Tambien podemos ser mas especifico y especificar que es por ejemplo un ingles estadounidense. Esto es util para los motores de busqueda como asi tambien las tecnologicas de asistencia como asistentes de voz y lectores de pantalla. El atributo lang puede ir en cualquier etiqueta html no solo en la etiqueta html.

Tambien podemos identifcar el idioma de enlace vinculado con el atributo **hreflang**.

### Consideraciones al internacionalizar una pagina

* No crear imagenes que contengan texto porque si no debo crear imagenes para todos los idiomas.

* Asegurarme que el diseño sea amplio y comodo para que se puedan adaptar a los diferentes idiomas y modo de escritura.
* Si estoy utilizando una fuente web debo asegurarme de que tenga un rango de caracteres lo suficientemente amplio para cubrir los idiomas a los que se traducira.


[[Unidades de medida]]
[[Display flex]]
[[Display grid]]
[[Media queries CSS]]
[[Container queries CSS]]
[[Imagenes receptivas]]
