# BEM
BEM (Bloque, Elemento, Modificador) es un enfoque basado en componentes para el desarrollo web. La idea detrás de esto es dividir la interfaz de usuario en bloques independientes. Esto hace que el desarrollo de la interfaz sea fácil y rápido, incluso con una interfaz de usuario compleja, y permite la reutilización del código existente sin copiar y pegar.

## Entidades BEM

### Block

Los **bloques** es un componente de pagina funcionalmente independiente que se puede reutilizar. El nombre del bloque describe su proposito.  

Los bloques son elementos autónomos y no deben depender del entorno que los rodea. Esto significa que no debemos establecer la geometría externa (como márgenes) o la posición para el bloque. 

```html
<div class="bloque"></div>
```

Podemos anidar bloques dentro de otros bloques.

```HTML
<header class="header">
	<div class="logo"></div>
</header>
```

![[Pasted image 20230420183654.png]]

El objetivo es que el bloque sea independiente y reutilizable en diferentes contextos sin afectar su apariencia o funcionalidad. No debe afectar los elementos fuera de el. Por ejemplo, si tienes un bloque que representa un boton, no deberia definir un margen en el bloque que haga que los elementos a su alrededor se desplacen o se superpongan. En lugar de eso, deberia definir el margen dentro del bloque para separar los elementos internos del boton.

![[Pasted image 20230420183715.png]]
![[Pasted image 20230420183734.png]]

![[Pasted image 20230420183803.png]]

#### Element
Los **elementos en BEM** son parte de un bloque, depende del bloque y no es por si solo significativo. El nombre del elemento describe su proposito, no su estado.

```HTML
<div class="header">
	<div class="header__item"></div>
</div>
```

Los elementos se pueden anidar unos dentro de otros. Un elemento es siempre parte de un bloque, no de otro elemento.

```HTML
<div class="header">
	<div class="header__item">
		<div class="header__logo"></div>
	</div>
</div>
```

Un elemento siempre es parte de un bloque y no se debe usar por separado del bloque. Ademas un elemento es un componente de bloque opcional, no todos los bloques tienen elementos.

```HTML
<!-- `search-form` block -->
<div class="search-form">
    <!-- `input` block -->
    <input class="input">

    <!-- `button` block -->
    <button class="button">Search</button>
</div>
```

![[Pasted image 20230420183819.png]]

### Modificadores
Los **modificadores** es una entidad que define la apariencia, el estado o el comportamiento de un bloque o elemento. El nombre del modificador describe su apariencia, su estado y su comportamiento.

```HTML
<div class="bloque">
	<h2 class="bloque__elemento"></h2>
	<h2 class="bloque__elemento_modificado"></h2>
</div>
```

Hay dos tipos de modificadores:

* booleano: Se utiliza cuando solo es importante la presencia o ausencia del modificador y su valor es irrelevante. Si esta presente un modificador booleano, se asume que su valor es true.

```HTML
<!-- The `search-form` block has the `focused` Boolean modifier -->
<form class="search-form search-form_focused">
    <input class="search-form__input">

    <!-- The `button` element has the `disabled` Boolean modifier -->
    <button class="search-form__button search-form__button_disabled">Search</button>
</form>
```

* key-value: Se utiliza cuando el valor del modificador es importante.

```html

<!-- El bloque `search-form` tiene el modificador `theme` con el valor `islands` --> 
< form  class = "search-form search-form_theme_islands" > 
    < input  class = "search-form__input" > 

    < !-- El elemento `button` tiene el modificador `size` con el valor `m` --> 
    < button  class = "search-form__button search-form__button_size_m" > Buscar </ button > 
</ form > 

<!-- Usted no se pueden usar dos modificadores idénticos con diferentes valores simultáneamente --> 
<clase de formulario  = "formulario de búsqueda
             search-form_theme_islands 
             search-form_theme_lite" > 

    < input  class = "search-form__input" > 

    < button  class = "search-form__button search-form__button_size_s 
                   search-form__button_size_m" > 
        Buscar </ button > </ form >
```

Un modificador no se puede usar de forma aislada del bloque o elemento modificado. Un modificador debe cambiar la apariencia, el comportamiento o el estado de la entidad, no reemplazarlo.

Los modificadores se pueden cambiar en tiempo de ejecución (por ejemplo, como reacción a un evento DOM del bloque) o a través de otros bloques.

### ¿Debo crear un bloque o un elemento?

Si una seccion de codigo se puede reutilizar y no depende de la implementacion de otros componentes de la pagina, podemos crear un bloque. En cambio, si una seccion de codigo no se puede usar por separado sin la entidad principal deberiamos crear un elemento.

## Mix

Las mezclas permiten combinar el comportamiento y los estilos de varias entidades sin duplicar el codigo. Crear componentes de interfaz de usuario semanticamente nuevos basados en los existentes.

```html
<!-- `header` block -->
<div class="header">
    <!--
        The `search-form` block is mixed with the `search-form` element
        from the `header` block
    -->
    <div class="search-form header__search-form"></div>
</div>
```

En este ejemplo, combinamos el comportamiento y los estilos del bloque `search-form` y el elemento `search-form`del bloque `header`. Este enfoque nos permite establecer la geometría externa y el posicionamiento en el elemento`header__search-form`, mientras que el bloque`search-form` en sí sigue siendo universal. Como resultado, podemos usar el bloque en cualquier otro entorno, porque no especifica ningún relleno. Por eso podemos llamarlo independiente.

## Estructura de archivos

## Nivel de redefinicion

La implementación final de un bloque se puede dividir en diferentes niveles de redefinición. Cada nuevo nivel amplía o anula la implementación original del bloque. [El resultado final se ensambla a partir de tecnologías de implementación](https://en.bem.info/methodology/key-concepts/#implementation-technology) individuales del bloque de todos los niveles de redefinición en un orden consecutivo predeterminado.

![[Pasted image 20230420190118.png]]

Por ejemplo, hay una biblioteca de terceros vinculada a un proyecto en un nivel separado. La biblioteca contiene implementaciones de bloques listas para usar. Los bloques específicos del proyecto se almacenan en un nivel de redefinición diferente.

Digamos que necesitamos modificar la apariencia de uno de los bloques de la biblioteca. Eso no requiere cambiar las reglas CSS del bloque en el código fuente de la biblioteca o copiar el código a nivel de proyecto. Solo necesitamos crear reglas CSS adicionales para ese bloque a nivel de proyecto. Durante el proceso de compilación, la implementación resultante incorporará tanto las reglas originales del nivel de biblioteca como los nuevos estilos del nivel de proyecto.


## Reglas de nomenclatura

`block-name__elem-name_mod-name_mod-val`

-   Los nombres están escritos en letras latinas minúsculas.
    
-   Las palabras están separadas por un guión ( `-`).
    
-   El nombre del bloque define el [espacio de nombres](https://en.wikipedia.org/wiki/Namespace) para sus elementos y modificadores.
    
-   El nombre del elemento está separado del nombre del bloque por un doble guión bajo ( `__`).
    
-   El nombre del modificador está separado del nombre del bloque o elemento por un solo guión bajo ( `_`).
    
-   El valor del modificador está separado del nombre del modificador por un solo guión bajo (`_`).
    
-   Para los modificadores booleanos, el valor no se incluye en el nombre.

### Nomenclatura alternativa

`block-name__elem-name--mod-name--mod-val`

-   Los nombres están escritos en letras latinas minúsculas.
    
-   Las palabras dentro de los nombres de las entidades BEM están separadas por un guión ( `-`).
    
-   El nombre del elemento está separado del nombre del bloque por un doble guión bajo ( `__`).
    
-   Los modificadores booleanos están separados del nombre del bloque o elemento por un guión doble ( `--`).
    
-   El valor de un modificador está separado de su nombre por un guión doble ( `--`).

Mas info en  https://en.bem.info/

