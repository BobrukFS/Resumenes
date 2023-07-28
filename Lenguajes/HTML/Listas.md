# Listas
Las listas en HTML son muy importantes, no solo se utilizan para listar si no tambien para diseñar un menu, etc.

* **Listas ordenadas**: Las listas ordenadas son listas en las que el **orden** de los elementos **SI importa** y se indican con la etiqueta **`<ol> </ol>`**, dentro se le anida otra etiqueta **`<li> </li>`** (declara cada uno de los elementos de una lista.) quedando de la siguiente manera:

![[Pasted image 20221126221609.png]]

* **Listas desordenadas**: Las listas desordenadas son listas en las que el **orden** de los elementos **NO importa** y se indican con la etiqueta **`<ul> </ul>`**, dentro se le anida otra etiqueta **`<li> </li>`** quedando de la siguiente manera:

![[Pasted image 20221126221743.png]]

* **Listas de definicion**: Son listas en las que se ponen los ítems con su definición. Se indican con la etiqueta **`<dl> </dl>`**, dentro se le anida otra etiqueta **`<dt> </dt>`** (termino a describir) y se le anida otra etiqueta  **`<dd></dd>`** (**definición de descripción**).

**Dato:**  Podemos anidar listas dentro de nuestras listas.

### Atributos que pueden ir en listas

*  **type=”…”**: Este atributo sirve para determinar el tipo de indicador que queremos usar. Se le puede asignar como valor a(Para que tenga orden alfabetico), 1 (Para que tenga orden numerico) o I(Para que tenga orden en numero romanos).

*  **start=”…”**: Este atributo sirve para determinar el valor desde el cual los indicadores tienen que comenzar a contar

*  **reversed**: Este atributo booleano sirve para invertir el orden de los indicadores.

Tambien podemos utilizar el elemento **`<details></details>`**: Este elemento crea una herramienta que se expande cuando se hace clic en ella para mostrar información adicional. La parte visible se define con el elemento **`<summary>`**, y se pueden usar elementos comunes como parrafos para definir el contenido.


**Se puede anidar listas dentro de listas**: 

```html
<ul role="list">  
	<li>  
		<a href="#e">Elements</a>  
		<ul>  
			<li>  
				<a href="#nr">Non-replaced elements</a>  
			</li>  
			<li>  
				<a href="#rave">Replaced and void elements</a>  
			</li>  
		</ul>  
	</li>  
	<li>  
		<a href="#a">Attributes</a>  
	</li>  
	<li>  
		<a href="#aoe">Appearance of elements</a>  
	</li>  
	<li>  
	<a href="#e2">Element, attributes, and JavaScript</a>  
	</li>  
</ul>
```