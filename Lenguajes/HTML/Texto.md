# Texto

## Elementos de texto

### Encabezados
Los elementos **`<h1></h6>`** definen un encabezado, siendo h1 el de mayor jerarquia, y h6 el de menor jerarquia.
Los motores de búsqueda que indizan tu página consideran el contenido de los títulos como palabras clave importantes e influyen en la puntuación de búsqueda de la página. Sin encabezados, tu página tendrá un rendimiento bajo en términos de optimización de motores de búsqueda [SEO](https://developer.mozilla.org/es/docs/Glossary/SEO). No hay que omitir los niveles de encabezados, no puedo poner h1 y luego h3.

### Parrafos
El elemento **`<p></p>`** definen texto en parrafos.

**Dato**: Si pongo **lorem20** por ejemplo se pondrán 20 palabras aleatorias para poder después remplazarlo por un texto.

### Bold
El elemento **`<b></b>`** indica que el texto debe ser representado en negrita, sin darle al texto importancia adicional.

### Strong
El elemento **`<strong></strong>`** le da al texto mas enfasis que el elemento bold, con una importancia mas alta semanticamente. Esta pensada para indicar importancia o urgencia de su contenido. Va a darle mas importancia cuando lo lean los buscadores

### Italic
El elemento **`<i></i>`** muestra el texto marcado con un estilo en cursiva o italica.

### Emphasis
El elemento **`<em></em>`** es apropiado para marcar con énfasis en el texto. El elemento **`<em>`** puede ser anidado, con cada nivel de anidamiento indicando un mayor grado de énfasis. El texto se ve en italica. Le agrega un peso semantico cuando lo lean los buscadores.

### Break
El elemento **`<br>`** produce un salto de línea en el texto (retorno de carro). Es útil para escribir un poema o una dirección, donde la división de las líneas es significante.

### Word break opportunity
El elemento **`<wbr>`** sugiere la posibilidad de un salto de linea para ayudar al navegador a decidir donde cortar el texto cuando no hay suficiente espacio para mostrarlo entero.

### Underlined
El elemento **`<u></u>`** agrega un subrayado.

### Strike
El elemento **`<strike></strike>`** agrega un tachado.

### Span
El elemento **`<span></span>`** se utiliza para delimitar contenido cuando se le quiere aplicar CSS (o tratarlo con Javascript) sin proporcionarle ningun significado.

### Horizontal rule
El elemento **`<hr>`** pone lineas horizontales.

### Blockquote
El elemento **`<blockquote></blockquote>`** se utiliza si una seccion de contenido a nivel de bloque se cita en otro lugar, e incluye una URL que apunte a la fuente de la cita dentro de un **atributo cite**. 

### Quote
El elemento **`<q></q>`** se utiliza para citas in line.

### abbr
El elemento **`<abbr></abbr>`** se utiliza para envolver una abreviatura o acronimo y proporciona una expansion completa del termino (incluido dentro de un atributo title).

### Address
El elemento **`<address></address>`** se utiliza para marcar la informacion de contacto. Se le puede añadir un recurso externo si este contiene informacion de contacto. Se implementa con frecuencia dentro de los pies de paginas para definir la direccion de la empresa o el sitio web.

### Sup
El elemento **`<sup></sup>`** sirve para convertir texto en superindice.

### Sub
El elemento **`<sub></sub>`** sirve para convertir texto en subindice.

### Code
El elemento **`<code></code>`** sirve para marcar fragmentos de codigo. Se puede utilizar con el elemento pre.

### Pre
El elemento **`<pre></pre>`** sirve para respetar los espacios en blanco.

### Time
El elemento **`<time></time>`** sirve para marcar horas y fechas en un formato legible por la maquina. Se utiliza acompañado del atributo **datetime="..."** donde se indica el formato del tiempo.

## ¿Como poner caracteres especiales?
Para que un signo no se interprete como código se utilizan las referencias de caracteres. Estos son códigos especiales que representan caracteres, para ser usados.
Para usar alguna de estas referencias en un documento HTML o XML, ingresa un **ampersand (&)** seguido por el **nombre de la entidad** y un **punto y coma (;)**, por ejemplo, &amp; para el ampersand ("&").