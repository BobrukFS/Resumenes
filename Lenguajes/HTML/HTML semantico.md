# HTML semantico

Está bastante claro que el uso de elementos semánticos ayuda a la accesibilidad, y el uso de elementos no semánticos reduce la accesibilidad. HTML es generalmente, por defecto, accesible. Nuestro trabajo como desarrolladores es proteger la naturaleza accesible predeterminada de HTML y asegurarnos de maximizar la accesibilidad.
## Elementos semanticos para estructurar el body

![[Pasted image 20221126094403.png]]

### Header
El elemento **`<header></header>`** sirve para especificar contenido de tipo introductorio como el logo o titulo,  o un conjunto de enlaces de navegacion. Tiene una semantica diferente dependiendo de donde este anidado. Puede ser el banner de nuestro sitio o puede ser el encabezado de una seccion en especifico. Es decir puede haber mas de un header.

En el AOM header es un landmark con papel implicito de heading.
### Nav
El elemento **`<nav></nav>`** representa una sección de una página cuyo propósito es proporcionar enlaces de navegación, ya sea dentro del documento actual o en otros documentos. El elemento **`<nav>`** está destinado sólo para el bloque principal de enlaces de navegación. No hace falta que todos los enlaces esten en el elemento nav, los enlaces individuales pueden ir fuera del nav.

### Main
El elemento **`<main></main>`** define una división que contiene el contenido principal del documento (el contenido que representa el tema central de la página). No se debe incluir más de un elemento principal en un documento. Dentro de main podemos utilizar **`<section>`**, etc. No podemos anidar main dentro de otro elemento.

### Section
El  elemento **`<section></section>`** define una sección en un documento. Una sección es una agrupación temática de contenido. Se usa para abarcar secciones independientes genéricas de un documento cuando no hay un elemento semántico más específico para usar. Las secciones deben tener un encabezado si o si, con muy pocas excepciones.

### Article
El elemento **`<article></article>`** específica contenido autónomo e independiente. Un artículo debe tener sentido por sí solo y debe ser posible distribuirlo independientemente del resto del sitio web.

### Aside
El elemento HTML **`<aside></aside>`** representa una sección de una página que consiste en contenido que está indirectamente relacionado con el contenido principal del documento. Estas secciones son a menudo representadas como barras laterales o como inserciones y contienen una explicación al margen como una definición de glosario, elementos relacionados indirectamente, como publicidad, la biografía del autor, o en aplicaciones web, la información de perfil o enlaces a blogs relacionados.

El aside tambien es un landmark, con el papel implicito de complementary.

### Footer
El elemento **`<footer></footer>`** define un pie de página para un documento o sección. Un elemento **`<footer>`** normalmente contiene: 1. Información de autoría. 2. Información registrada. 3. Información de contacto. 4. Mapa del sitio. 5. Volver a los enlaces superiores. 6. Documentos relacionados. 7. declaracion de derechos de autor y enlaces a sus politicas de privacidad y cokies. Tiene una semantica diferente dependiendo de donde este anidado. Puede ser el pie de pagina de nuestro sitio o puede ser el pie de pagina de una seccion en especifico. Es decir puede haber mas de un footer. 

En el AOM el footer de nivel superior es un landmark con funcion implicita contentinfo. Mientras que cualquier otro footer de una seccion se muestra como FooterAsNonLandmark o section.

### Detalles y resumen

Las etiquetas `<details>`y `<summary>`se utilizan para marcar una sección plegable de contenido. La `<summary>`etiqueta se usa para marcar el título de la sección y la `<details>`etiqueta se usa para marcar el contenido en sí.

### Figura y pie de foto

Las etiquetas `<figure>`y `<figcaption>` se utilizan para marcar un contenido independiente al que se hace referencia desde el contenido principal de una página web. La `<figure>`etiqueta se usa para marcar el contenido en sí y la `<figcaption>`etiqueta se usa para marcar un título o una descripción del contenido.

### Mark

La `<mark>`etiqueta se utiliza para marcar texto que se ha resaltado por algún motivo. Esto puede incluir cosas como resultados de búsqueda o texto que un usuario ha resaltado.

### Tiempo

La `<time>`etiqueta se utiliza para marcar una fecha u hora. Al usar la `<time>`etiqueta, puede facilitar que los motores de búsqueda y otras tecnologías comprendan el significado del contenido de su página.

### Progress

La `<progress>`etiqueta se utiliza para marcar una barra de progreso. Al usar la `<progress>`etiqueta, puede facilitar que los usuarios comprendan el progreso de una tarea.

## Div

El elemento **`<div></div>`** define una división genérica. Se usa cuando no se puede aplicar ningún otro elemento semantico. Este no es un elemento semantico pero le podes agregar la funcion semantica mediante el atributo role.

