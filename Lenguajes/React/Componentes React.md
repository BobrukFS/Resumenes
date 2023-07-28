# Componentes React

Un componente es una parte de la IU (interfaz de usuario) que tiene su propia logica y apariencia. Los componentes nos permiten dividir la interfaz de usuario en piezas independientes y reutilizables y pensar en cada parte de la interfaz de forma aislada. Los componentes tienen su propia logica y apariencia. Estos pueden ser tan pequeños como un boton o tan grande como una pagina entera.

**Dato**: Los nombres de los componentes de React siempre deben comenzar con una letra mayuscula, miuentras que las etiquetas HTML deben estar en minusculas. Tambien es recomendable nombrar con mayuscula las carpetas de los componentes

## Componentes de clase

Estos componentes son clases simples (compuestas por múltiples funciones que agregan funcionalidad a la aplicación). Todos los componentes basados ​​en clases son clases secundarias para la clase Component de ReactJS.

Aunque los componentes de clase son compatibles con React, se recomienda escribir componentes funcionales y hacer uso de ganchos en las aplicaciones modernas de React.

## Componente funcionales

Los componentes funcionales de React son el equivalente de los componentes de clase de React, pero se expresan como funciones en lugar de clases. En el pasado, no era posible usar el estado o los efectos secundarios en los componentes de función, por eso se llamaban **componentes sin estado funcionales** , pero ese ya no es el caso con al agregarse los Hooks en React , que los renombró como **componentes de función**. Es decir, ahora los componentes de React son funciones de JavaScript que devuelven HTML.

```jsx
import React from 'react';
function App() {
  const greeting = 'Hello Function Component!';
  return <h1>{greeting}</h1>;
}
export default App;
```

Un **componente React** es literalmente la declaración de un componente tal como lo vemos en el fragmento de código anterior.

La representación de un componente ocurre cada vez que usamos este componente como un **elemento React** con paréntesis angulares (por ejemplo, `<App />`) en otro componente. También podemos renderizar un componente como elemento React varias veces. Cada vez que un componente se representa como elemento, creamos una **instancia de este componente**. Si bien un componente React se declara una vez, se puede usar varias veces como elemento React en JSX. Cuando se usa, se convierte en una instancia del componente y vive en el árbol de componentes de React.

**¿Diferencia entre componente y elemento react?**

En resumen, los elementos de React son representaciones ligeras de lo que desea representar, mientras que los componentes son reutilizables y definen cómo se deben representar los elementos. Los componentes pueden verse como fábricas para crear elementos de React, y los elementos representan los elementos visuales reales en la interfaz de usuario.

### Como funcionan internamente

Cada vez que se llama a un componente de React (rendering), React llama internamente a su  método `React.createElement()` , lo que devuelve el siguiente objeto:

```jsx
console.log(App());

// {
//   $$typeof: Symbol(react.element)
//   "type": "p",  //Representa el elemento HTML real
//   "key": null,
//   "ref": null,
//   "props": {    //Representa todos los atributos HTML + El contenido interno en children debido a que  React trata `children`como un pseudo atributo HTML.
//     "children": "Hello React"
//   },
//   "_owner": null,
//   "_store": {}
// }
```

Nosotros podemos utilizar el metodo React.createElement() como remplazo del JSX devuelto para crear el mismo componente.

```jsx
const App = ()=> {
	const greeting = 'Hello Function Component!';
	return React.createElement(
	'h1',
		{
			className: 'header__title',
			children: greeting
		}
	);
}
```
[[Hooks]]