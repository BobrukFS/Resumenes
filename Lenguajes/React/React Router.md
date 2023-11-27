# React Router

Es una libreria para implementar enrutamiento del lado del cliente y del lado del servidor para aplicaciones React.

El enrutamiento del lado del cliente (SPA) consiste en mostrar determinada interfaz en funcion de la URL sin que haya solicitudes a un servidor, sino de forma dinamica mediante JavaScript.

Esta librería nos servirá para implementar enrutamiento o, en otras palabras, renderizar ciertos componentes en función de eventos en la URL (como el cambio en la url o en alguno de sus parámetros).

Para instalarlo utilizamos:

```npm
npm install --save react-router react-router-dom
```

## Componentes React Router

### Router o BrowserRouter

React Router empieza con un componente `<Router>` o `<BrowserRouter>` (especifico para web).  El componente Router provee el contexto y las opciones globales necesarias para que la aplicación funcione.

El BrowserRouter es un Router específico que utiliza la API History de HTML5 para manipular la navegación entre páginas. Es un componente que debe ser el padre de todos los componentes que utilicen React Router. En general, se pone como componente Padre de la aplicación entera. El BrowserRouter almacena la información de la ruta actual en memoria, proporcionando una URL limpia.

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
ReactDOM.createRoot(document.getElementById('root')).render(

  <React.StrictMode>
    <Router> //Puede ser tambien <BrowserRouter>
    <Header></Header>
      <Routes>
		    <Route path="/" element={<Intro/>} />
            <Route path="/about" element={<About />} />
            <Route path="/Contact" element={<Contact />} />
            <Route path="/Tienda" element={<Tienda />} />
	   </Routes>
    </Router>
  </React.StrictMode>

)
```

### HashRouter

HashRouter nos va a permitir implementar un enrutamiento en el cual el estado de la página se almacena en la URL.

Si bien esto conlleva URLs menos limpias, también implica que nuestra aplicación React será más portable ya que no necesitará de un servidor que procese las rutas, como es el caso del BrowserRouter.

### Routes y Route

Los componentes Routes y Route son la principal fuente para renderizar en React-Router basado en el valor actual de la propiedad location. 

Un `<Route path="" element={}>` como una especie de condicional IF: si su propiedad path coincide con la URL actual, entonces renderiza en ese lugar el element asociado. Tiene una propiedad llamada **element** que contiene JSX con el componente a renderizar si la URL actual coincide con el valor de su path. Tiene otro atributo que es **path** que contiene la url que busca.

**Dato**: Tambien en vez de utilizar **element** podemos utilizar **component** cuando queremos renderizar un componente de React que esta definido en mi aplicacion.

Se pueden definir parametros por la URL con la sintaxis **:miParametro**. Estos parametros se pueden leer en el componente renderizado con el hook **useParams**.

Un Route puede tener a su vez componentes hijos y de esa forma definir rutas anidadas.

El componente `<Routes>` sirve para agrupar un conjunto de rutas. Define el espacio donde se renderizan las rutas de la aplicacion.

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
ReactDOM.createRoot(document.getElementById('root')).render(

  <React.StrictMode>
    <Router> //Puede ser tambien <BrowserRouter>
    <Header></Header>
      <Routes>
		    <Route path="/" element={<Intro/>} />
            <Route path="/about" element={<About />} />
            <Route path="/Contact" element={<Contact />} />
            <Route path="/Tienda/:id" element={<Tienda />} />
	   </Routes>
    </Router>
  </React.StrictMode>

)
```
### Link

**Link** es un componente que sirve para navegar a otra página. Este renderiza un elemento y lleva a que, al hacer clic izquierdo (o tap en pantallas chicas), navegue a la URL indicada. Para indicar la ruta, el elemento `<Link>` lleva la propiedad **to**.

```jsx
<Link to="/about">Ir a sobre mi</Link>
```

El atributo to soporta tambien un objeto donde podemos definir parámetros específicos y compartir información entre las distintas rutas.

![[Pasted image 20231028225239.png]]
#### NavLink
NavLink es una versión especial de , que agrega atributos de estilo al elemento renderizado cuando coincida con la URL actual.

* **activeClassName**: debe ser un string el cual será el nombre de la clase que se le agrega al elemento cuando la ruta de navegación coincida con su link.
* **activeStyle**: es un objeto que representa los estilos que se agregan cuando el link esté activo.
### Navigate

Cuando se renderiza un Navigate, éste cambia el location actual. En otras palabras: al renderizarse Navigate, provoca una redirección. Lo podemos utilizar para proteger el acceso a páginas renderizando un Navigate a una página de Login si, por ejemplo, el usuario no está autorizado para la página

![[Pasted image 20231028214659.png]]

### Switch

El componente Switch de Router React es un componente que se utiliza para renderizar solo una ruta de entre varias rutas que coincidan. Esto es útil para casos en los que solo quieres renderizar una ruta de entre varias rutas que coincidan, como en el caso de una página de inicio y una página de error 404.

El componente Switch funciona de la siguiente manera:

1. Comprueba si alguna de las rutas que contiene coincide con la URL actual del navegador.
2. Si coincide alguna ruta, renderiza el componente asociado a esa ruta.
3. Si no coincide ninguna ruta, renderiza el componente `NoMatch`.

El componente `NoMatch` es un componente que se renderiza cuando ninguna de las rutas que contiene el componente Switch coincide con la URL actual del navegador. Por defecto, el componente `NoMatch` renderiza un mensaje de error 404.

```jsx
//En este caso, la ruta `/` coincidirá con la URL actual del navegador cuando el usuario se encuentre en la página de inicio. La ruta `*` coincidirá con cualquier URL que no coincida con ninguna de las otras rutas.

import React from "react";
import { BrowserRouter as Router, Switch, Route } from "react-router-dom";

const App = () => {
  return (
    <Router>
      <Switch>
        <Route path="/" component={Home} />
        <Route path="*" component={Error404} />
      </Switch>
    </Router>
  );
};

export default App;

```

La principal diferencia entre usar el componente Switch y no usarlo es que, sin el componente Switch, todas las rutas que coincidan se renderizarán al mismo tiempo. Esto puede provocar problemas de rendimiento y confusión para los usuarios. Mientras que al usar Switch solo renderizara la primera ruta que coincida.
### Redirect

Renderizando un `<Redirect to=""/>` la aplicación navegará hacia la nueva ubicación. La nueva ubicación sobreescribirá la ubicación actual en el historial (En otras palabras, no se podrá volver atrás).

```jsx
	    <Route path="/admin">
		    {estaLogeado ? <Redirect to="/panel"/> : <HomePage/>}
		</Route>
```