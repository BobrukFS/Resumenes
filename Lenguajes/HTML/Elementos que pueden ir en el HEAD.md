# Elementos que pueden ir en el HEAD
La función de la cabecera es **contener los metadatos** (informacion que describe otro datos) del documento.
## Meta
El elemento **`<meta>`** representa metadatos asociados con el documento, como la descripción del documento, palabras claves, el tipo de codificación de caracteres, etc.

### Atributos que puede contener META

* **name=”…”** : Este atributo especifica el tipo de metadato del que se trata; es decir, qué tipo de información contiene. Pueden tener valores description, keywords,etc.

* **content=”…”** : Este atributo especifica el contenido del metadato en sí.

* **charset=”…”** : Este atributo especifica el tipo de caracteres que vamos a utilizar en nuestra pagina web

Ejemplo:

```HTML
<meta name="description" content="The MDN web Docs site provides...">
```

![[Pasted image 20221124231141.png]]
Otro tipo de metadatos que se pueden utilizar es [**Open Graph Data**](https://ogp.me/) que nos da como resultado por ejemplo esto al pasar un link por Facebook:

![[Pasted image 20221124231210.png]]
![[Pasted image 20221124231217.png]]
## Title
El elemento **`<title></title>`** establece el titulo de la totalidad del documento HTML, es el titulo que aparece en la pagina. Tanto **meta** como **tittle** son **importantes ya que se utilizan en el motor de busqueda**.
Establece el título de la página, que es el título que aparece en la pestaña del navegador en la que se carga la página. El título de la página también se utiliza para describir la página cuando se marca como favorita.
## Link
El elemento **`<link>`** especifica la relación entre el documento actual y un recurso externo. Por ejemplo sirve para instalar CSS y Bootstrap. 

### Atributos que puede contener link

* **href = “…”**: Este atributo contiene la ruta al recurso externo que se quiere vincular.`

* **rel = “…”**: Este atributo especifica el tipo de relación que tiene el documento vinculado con el documento presente. Puede tomar diferentes valores: **stylesheet** (indica que es la hoja de estilo del documento) y **preload** (indica que dicho recursos la pagina los necesitara muy pronto)`

* **as=”…”**: Este atributo solo se utiliza cuando se ha establecido un rel=”preload” o rel=”prefetch” en el elemento y se le asigna un valor “style”.`

* **type=”…”**: Este atributo especifica el tipo de medio/recurso vinculado (anteriormente conocido como Multipurpose Internet Mail Extensions MIME). Ejemplo image/png.`
**Dato:** Es importante tener en cuenta que el html lee de arriba hacia abajo por lo que es importante el orden de los **link**.

Otro caso es el de agregar un icono personalizado al lado del titulo de la pagina, este se denomina **favicon**. 

Ejemplo:

![[Pasted image 20221124232705.png]]
## Script
El elemento **`<script></script>`** también debería ir en el head, y debería incluir un atributo src con la ruta al JavaScript que quieres cargar. Tambien puede ir antes del cierre del elemento **body**. Esto depende de que si queremos asegurarnos de que los elementos existan antes de que se lea el script o que se lea el script despues de que cargue el archivo html.

![[Pasted image 20221124232455.png]]
## Style
El elemento **`<style></style>`** se usa para declarar estilos CSS dentro del documento.