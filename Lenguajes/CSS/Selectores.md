# Selectores
Los selectores nos indican en cual elemento HTML hay que aplicar el estilo. Una misma regla puede aplicar a varios selectores y, a un mismo selector se le pueden aplicar varias reglas. Se puede dirigirse a varios selectores al mismo tiempo separándolos con una coma.

## Selectores basicos

### Selector universal

El **selector universal** se utiliza para seleccionar todos los elementos de la pagina.

```CSS
/*Se aplica a todos los elementos del documento*/
* {
	margin: 0;
	padding: 0;
}

/*Se le aplica estilo a todos los parrafos del documento*/
* p {
		color: blue;
}
```

### Selector de etiqueta
El **selector de etiqueta** selecciona todos los elementos de la pagina cuya etiqueta HTML coincide con el valor del selector.

```CSS
h1 {
	color: red;
}

h2 {
	color: blue;
}

p {
	color: orange;
}
```

### Selectores descendentes

Los **selectores descendentes** seleccionan los elementos que se encuentran dentro de otros elementos. Un elemento es descendente de otro cuando se encuentra entre las etiquetas de apertura y de cierre de otro elemento.

```CSS
p span {
	color: red;
}
```

### Selectores descendentes directos

Se utiliza para seleccionar un elemento que es hijo directo de otro elemento y se indica mediante el "signo de mayor que".

```CSS
p > span {
	color : blue;
}
```

### Selectores de hermano adyacente directo

Sólo seleccionará un elemento especificado que esté inmediatamente después de otro elemento especificado.

```CSS
/* En este caso se seleccionara al elemento p que este inmediatamente despues de h2 siempre y cuando sea hermano de h2 */

h2 + p {
color:black;
}
```

### Selectores de hermano general

El selector general de hermanos da estilos a los elementos hermanos del primer selector definido, incluso si no es su hermano inmediato, solo si estos son hijos del mismo elemento padre.

```CSS
/* En este caso se seleccionara a todos los elementos p siempre y cuando sean hermanos de h2 */

h2 ~ p {
	color:black;
}
```


## Selectores de clase

Los **selectores de clase** seleccionan aquellos elementos que tengan dicha clase.

```CSS
/*Selecciona a los elementos con clase "titulo" */
.titulo {
	color: red;
}

/*Selecciona a los elementos con clase "titulo" que sean parrafos*/
p.titulo {
	color: red;
}
```

![[Pasted image 20221201183132.png]]

Es posible aplicar los estilos de varias clases CSS sobre un mismo elemento:

```HTML
<p class="especial destacado error">Parrafo de texto...</p>
```

```CSS
.error {
	color : red;
}

.error.destacado {
	color : blue;
}

.destacado {
	font-size : 15px;
}

.especial {
	font-weight : bold;
}
```

Tambien podemos aplicar la misma regla a diferentes selectores

```css
.error,
.peligro,
.danger {
	color: red;
}
```

## Selectores de ID

El **selector de ID** permite seleccionar un elemento de la página a través del valor de su atributo id. Este tipo de selectores sólo selecciona un elemento de la página porque el valor del atributo id no se puede repetir en dos elementos diferentes de una misma página.

La sintaxis de los selectores de ID es muy parecida a la de los selectores de clase, salvo que se utiliza el símbolo de la almohadilla (#) en vez del punto (.)

```CSS
#destacado {
	color: red;
}
```

## Selectores de atributos
Los **selectores de atributos** brinda diferentes formas de seleccionar elementos en funcion de la presencia de un determinado atributo en un elemento.

```CSS
input[type="text"] {
		color : blue;
}
```

### Expresiones regulares en selectores

* **`^="..."`** : Selecciona al elemento que empiece con el valor que se le asigne.
* **`$="..."`** : Selecciona al elemento que termine con el valor que se le asigne.
* **`*="..."`** : Selecciona al elemento que contenga el valor que se le asigne.

```css
/*En este ejemplo, se seleccionaran los inputs que contengan el atributo type que finalizen con xt*/
	input[type$="xt"]{
		color: blue;
	}
```


[[Pseudo clases y pseudo elementos]]
[[Especificidad]]