# Indice

[[Caracteristicas basicas de React]]
[[Componentes React]]
[[Eventos en React]]
[[Renderizado condicional y de listas]]
[[Uplifting]]
[[React Router]]
[[Suspense]]
[[Context]]


Puedo poner comentarios // o /**/ pero tambien puedo poner comentarios en return utilizando `{/**/}`

Hay un div con id="root"

react es la libreria que nos permite trabajar en jsx. react-dom es puntualmente la libreria que nos va a permitir hacerlo web.

jsx mezcla html con javascript

el main.jsx va a ser el punto inicial de la aplicacion, en el que tiene

```jsx
//main.jsx o como quiera llamarlo
import React from 'react'
import ReactDOM from 'react-dom/client'
import Header from './Components/Header/header.jsx'
import './styles/main.scss'

ReactDOM.createRoot(document.getElementById('root')).render( //selecciona al elemento con el id root y lo pinta (render)
  <React.StrictMode>
    <Header/>
  </React.StrictMode>,
)
```

JSX es más estricto que HTML. Tienes que cerrar etiquetas como `<br />`. Su componente tampoco puede devolver varias etiquetas JSX. Tienes que envolverlos en un padre compartido, como un envoltorio `<div>...</div>`vacío o :`<>...</>`

En react, se especifica una clase CSS con className. Es el equivalente al atributo class en HTML.

JSX le permite poner marcas en JavaScript. Las llaves le permiten "escapar hacia atrás" en JavaScript para que pueda incrustar alguna variable de su código y mostrársela al usuario

También puede "escapar a JavaScript" desde los atributos JSX, pero debe usar llaves _en lugar de_ comillas. Por ejemplo, `className="avatar"`pasa la `"avatar"`cadena como la clase CSS, pero `src={user.imageUrl}`lee el `user.imageUrl`valor de la variable de JavaScript y luego pasa ese valor como el `src`atributo:

También puede poner expresiones más complejas dentro de las llaves JSX, por ejemplo, [concatenación de cadenas](https://javascript.info/operators#string-concatenation-with-binary) :


En el ejemplo anterior, `style={{}}`no es una sintaxis especial, sino un `{}`objeto normal dentro de las `style={ }`llaves JSX. Puede usar el `style`atributo cuando sus estilos dependen de variables de JavaScript.

En React, no existe una sintaxis especial para las condiciones de escritura. En su lugar, utilizará las mismas técnicas que utiliza al escribir código JavaScript normal.


Para cada elemento de una lista debemos pasar una cadena o un numero que identifique de forma unica ese elemento entre sus hermanos. Esto se realiza con el atributo key

## Respondiendo a eventos

Puede responder a eventos declarando funciones de controlador de eventos dentro de sus componentes.

```jsx
function MyButton() {  

	function handleClick() {  

		alert('You clicked me!');  
	}  

	return (  

		<button onClick={handleClick}>  

			Click me  

		</button>  
	);  
}
```

## Actualizando la pantalla

A menudo, deseará que su componente "recuerde" cierta información y la muestre. Por ejemplo, tal vez desee contar la cantidad de veces que se hace clic en un botón. Para hacer esto, agregue _el estado_ a su componente.

Primero, importa [`useState`](https://react.dev/reference/react/useState)desde React:

function MyButton() {  

const [count, setCount] = useState(0);  

// ...

Obtendrá dos cosas de `useState`: el estado actual ( `count`) y la función que le permite actualizarlo ( `setCount`). Puede darles cualquier nombre, pero la convención es escribir `[something, setSomething]`.

La primera vez que se muestre el botón, `count`será `0`porque pasaste `0`a `useState()`. Cuando desee cambiar de estado, llame `setCount()`y pásele el nuevo valor. Al hacer clic en este botón se incrementará el contador:

```jsx
function MyButton() {  

const [count, setCount] = useState(0);  

  

function handleClick() {  

setCount(count + 1);  

}  

  

return (  

<button onClick={handleClick}>  

Clicked {count} times  

</button>  

);  

}
```

Si renderiza el mismo componente varias veces, cada uno obtendrá su propio estado. Haga clic en cada botón por separado:

```jsx
import { useState } from 'react';

export default function MyApp() {
  return (
    <div>
      <h1>Counters that update separately</h1>
      <MyButton />
      <MyButton />
    </div>
  );
}

function MyButton() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return (
    <button onClick={handleClick}>
      Clicked {count} times
    </button>
  );
}
//Observe cómo cada botón "recuerda" su propio `count`estado y no afecta a otros botones.
```



## Compartir datos entre componentes

Sin embargo, a menudo necesitará componentes para _compartir datos y actualizarlos siempre juntos_ .

Ejemplo cuando haga click en un boton lo que va a suceder es que se actualizan ambos

```jsx
import { useState } from 'react';

export default function Header() {
  const [count, setCount] = useState(0);
  function handleClick() {
    setCount(count + 1);
  }

  return (

    <div>

      <h1>Counters that update together</h1>

      <MyButton count={count} onClick={handleClick} />

      <MyButton count={count} onClick={handleClick} />

    </div>

  );

}

  

function MyButton({count, onClick}) {

  return (

    <button onClick ={onClick}>

      Clicked {count} times

    </button>

  );

}
```

