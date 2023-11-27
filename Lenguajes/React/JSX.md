# JSX

**JSX** es un lenguaje de desarrollo propio. Este lenguaje es usado únicamente en tiempo de desarrollo ya que, al construir la aplicación, todo código JSX es traducido en código JS procesable por el navegador mediante Babel y Webpack. La posibilidad de escribir componentes React dentro de JavaScript como etiquetas HTML. Esto lo que hace es permitir que la logica de renderizado y el marcado convivan en el mismo lugar, es decir, en los componentes.

La mayoria de los proyectos de React usan JSX. JSX es mas estricto que HTML. 

**Reglas de JSX**

* Su componente no puede devolver varias etiquetas JSX. Tienes que envolverlos en un padre compartido, como un envoltorio div o vacio ` <></>` a la que se le denomina **fragmento** (permite agrupar cosas sin dejar ningun rastro en el arbol HTML del navegador). Tambien se puede utilizar la sintaxis larga `<Fragment></Fragment>`
* Hay que cerrar siempre las etiquetas HTML.
* Para especificar una clase CSS utilizamos **className**. Funciona de la misma manera que el atributo class. Hay que usar camelCase en los nombres de la clase.

[Convertidor de HTML a JSX](https://transform.tools/html-to-jsx)

## JS en JSX con llaves

JSX permite poner marcado en JavaScript. Las llaves permiten escapar hacia atras en JS para que pueda incrustar alguna variable de su codigo y mostrarsela al usuario. 

```jsx
//Dentro de una etiqueta
return (
	<h1>
		{user.name}
	</h1>
)

//Como atributos inmediatamente despues del signo del =
<h1 className={avatar}></h1>

//Otra forma

src={ baseUrl + person.imageId + person.imageSize + ".jpg"}
src={`${baseUrl}.jpg`}//baseUrl.jpg
```

Tambien puede escapar a Javascript desde los atributos JSX, pero debe usar llaves en lugar de comillas. 

```jsx
style= {{
          width: user.imageSize,
          height: user.imageSize
}}
```

 En el ejemplo anterior, `style={{}}`no es una sintaxis especial, sino un `{}`objeto normal dentro de las `style={ }`llaves JSX. Puede usar el `style`atributo cuando sus estilos dependen de variables de JavaScript.