# Eventos en React

React nos ofrece la posibilidad de utilizar los mismos eventos que usamos en HTML y, además, crear nuestros propios eventos

En React, toda la gestión de eventos se hace a través de JSX mediante atributos específicos. Estos atributos reciben como valor funciones que serán ejecutadas cuando el evento se dispare.

Por convención, es común nombrar los controladores de eventos `handle` seguidos del nombre del evento.

```jsx
//Ejemplo 1:
<button onClick={handleClick}>
//Ejemplo 2
<button onClick={() => {  
alert('You clicked me!');  
}}>
```

**Dato**: Las funciones pasadas a los controladores de eventos deben pasarse, no llamarse.

Debido a que los controladores de eventos se declaran dentro de un componente, tienen acceso a los accesorios del componente.

Los componentes integrados como `<button>`y `<div>`solo admiten [nombres de eventos del navegador](https://react.dev/reference/react-dom/components/common#common-props) como `onClick`. Sin embargo, cuando construyes tus propios componentes, puedes nombrar los accesorios del controlador de eventos como quieras.

```jsx
export default function App() {
  return (
    <Toolbar
      onPlayMovie={() => alert('Playing!')}
      onUploadImage={() => alert('Uploading!')}
    />
  );
}

function Toolbar({ onPlayMovie, onUploadImage }) {
  return (
    <div>
      <Button onClick={onPlayMovie}>
        Play Movie
      </Button>
      <Button onClick={onUploadImage}>
        Upload Image
      </Button>
    </div>
  );
}

function Button({ onClick, children }) {
  return (
    <button onClick={onClick}>
      {children}
    </button>
  );
}
```

Los controladores de eventos no son puros, por lo que se puede cambiar cierta informacion.
## Propagacion de eventos
Los controladores de eventos también detectarán eventos de cualquier elemento secundario que pueda tener su componente. Decimos que un evento “burbujea” o “se propaga” hacia arriba en el árbol: comienza donde ocurrió el evento y luego sube por el árbol.

```jsx
//Si hace clic en cualquiera de los botones, se ejecutará `onClick` primero, seguido del `onClick` del `<div>` padre . Entonces aparecerán dos mensajes. Si hace clic en la barra de herramientas, solo se ejecutará `onClick` del `<div>`de los padres.

export default function Toolbar() {
  return (
    <div className="Toolbar" onClick={() => {
      alert('You clicked on the toolbar!');
    }}>
      <button onClick={() => alert('Playing!')}>
        Play Movie
      </button>
      <button onClick={() => alert('Uploading!')}>
        Upload Image
      </button>
    </div>
  );
}
```
### Detener la propagacion
Los controladores de eventos reciben un **objeto de evento** como único argumento. Por convención, suele denominarse `e`, que significa "evento". Puede utilizar este objeto para leer información sobre el evento.

Ese objeto de evento también te permite detener la propagación. Si desea evitar que un evento llegue a los componentes principales, debe llamar `e.stopPropagation()`
### Prevenir el comportamiento predeterminado.
Algunos eventos del navegador tienen un comportamiento predeterminado asociado. Por ejemplo, un `<form>`evento de envío, que ocurre cuando se hace clic en un botón dentro de él, recargará toda la página de forma predeterminada. Puedes llamar `e.preventDefault()`al objeto de evento para evitar que esto suceda.