# Atributos globales

## Clases  e id

Las **clases e id** son atributos globales que identifican elementos. Estos atributos permiten a CSS y JavaScript seleccionar y acceder a elementos específicos a través de los selectores de clase e id.

* **Class=”…”** :  Este atributo permiten identificar a varios elementos. Es decir varios elementos pueden tener la misma clase y un elemento puede tener varias clases.

* **Id=”…”** : Este atributo permite identificar a un unico elemento y no se comparte al menos que sea en diferentes paginas.

	Sirve para muchos propósitos, incluyendo:

	-   El destino del identificador de fragmento de un enlace.
	-   Identificación de un elemento para scripting.
	-   Asociar un elemento de formulario con su etiqueta.
	-   Proporcionar una etiqueta o descripción para las tecnologías de asistencia.
	-   Estilos de orientación con (especificidad alta o como selectores de atributos) en CSS.

Un elemento puede tener varias clases y un solo id.

## Style

El atributo **style** permite aplicar estilos en linea, que son estilos aplicados al unico elemento en el que se establece el atributo.

Los estilos solo se aplican al elemento en el que se establece el atributo, y los descendientes heredan los valores de propiedad heredados si no se reemplazan por otras declaraciones de estilo en hojas de estilo.

**Sin embargo se recomienda hacerlo con CSS.**

## tabindex

El atributo "tabindex" se utiliza en HTML para especificar el orden en que los elementos de una página web reciben el foco cuando un usuario navega a través de ellos utilizando la tecla "Tab" en su teclado.

## Role

 El  atributo `role` se puede usar para proporcionar un significado semántico al contenido, lo que permite a los lectores de pantalla informar a los usuarios del sitio sobre la interacción esperada del usuario con un objeto. Hay algunos elementos que ya tienen un rol aria implicito.

## contenteditable

Un elemento con el atributo contenteditable establecido en true es editable, se puede enfocar y se agrega al orden de tabulacion como si tabindex="0" estuviera establecido.