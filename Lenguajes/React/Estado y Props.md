# Estado y Props

## Estado

Se define como estado al conjunto de variables reactivas encapsuladas dentro del componente. En otras palabras: el estado son variables que controlan el cambio de la interfaz pero solo en el componente en el que se encuentran (y sus componentes hijos) permitiendo asi la reactividad **focalizada**. A diferencia de las PROPS, son mutables.

Ejemplo: Si quiero mostrar un submenú al hacer clic en un ítem, eso debería controlarse mediante el estado porque es un cambio focalizado. Si, en cambio, quiero cambiar todo el tema del sitio a modo oscuro, eso debería gestionarlo mediante props ya que es un cambio compartido por muchos componentes.

Hay que tener en cuenta que:

1. **Las variables locales no persisten entre renderizaciones.** Cuando React renderiza este componente por segunda vez, lo renderiza desde cero; no considera ningún cambio en las variables locales.
2. **Los cambios en las variables locales no activarán las representaciones.** React no se da cuenta de que necesita renderizar el componente nuevamente con los nuevos datos.

Para actualizar un componente con nuevos datos, deben suceder dos cosas:

1. **Conservar** los datos entre renderizados.
2. **Active** React para renderizar el componente con nuevos datos (volver a renderizar).

Para ello utilizamos el hook **useState** que proporciona ambas cosas. Una variable de estado para tener los datos entre renderizaciones y una funcion de establecimiento de estado para actualizar la variable y activar React para renderizar el componente nuevamente,

El estado a menudo se llama local o encapsulado. No es accesible desde ningún componente que no sea el que posee o sus hijos y lo establece. Un componente puede elegir pasar su estado como props a sus componentes secundarios. Esto se conoce comúnmente como flujo de datos "descendente" o "unidireccional". El estado es local para una instancia de componente en la pantalla. En otras palabras, **si renderizas el mismo componente dos veces, ¡cada copia tendrá un estado completamente aislado!** Cambiar uno de ellos no afectará al otro. Y si en algun caso lo que quiero es que ambos componentes tengan el estado compartido lo que tendria que hacer es eliminar el estado de los componentes y agregarlo a su padre compartido mas cercano.

```jsx
//Ejemplo
import {useState} from 'React';

function Counter(props){
	const [count, setCount] = useState(0);
	return(
		<div onClick={()=> setCount(count + 1)}>
		Has hecho click {count} veces
		</div>
	);
}
```

**Dato**: Puede tener tantas variables de estado de tantos tipos como desee en un componente.

React espera hasta que se haya ejeutado todo el codigo de los controladores de eventos antes de proesar las actualizaciones de estado. Es por eso que:

```jsx
//Va a dar number siempre 1.
export default function Counter() {
  const [number, setNumber] = useState(0);

  return (
    <>
      <h1>{number}</h1>
      <button onClick={() => {
        setNumber(number + 1);
        setNumber(number + 1);
        setNumber(number + 1);
      }}>+3</button>
    </>
  )
}
```

Por lo que podemos utilizar funciones de actualizacion, por ejemplo

```jsx
import { useState } from 'react';

export default function Counter() {
  const [number, setNumber] = useState(0);

  return (
    <>
      <h1>{number}</h1>
      <button onClick={() => {
        setNumber(n => n + 1);
        setNumber(n => n + 1);
        setNumber(n => n + 1);
      }}>+3</button>
    </>
  )
}
```

Hay que tratar cualquier objeto de JS que pongamos en estado como solo lectura. Es decir no debemos modificar las propiedades si no crear una copia del objeto con las propiedades modificadas. Para eso utilizamos el operador spread.

```jsx
//Ejemplo 1

setPerson({  
...person, // Copy the old fields  
firstName: e.target.value // But override this one  
});

//Ejemplo 2

const [person, setPerson] = useState({  
name: 'Niki de Saint Phalle',  
artwork: {  
title: 'Blue Nana',  
city: 'Hamburg',  
image: 'https://i.imgur.com/Sd1AgUOm.jpg',  
}  
});

const nextArtwork = { ...person.artwork, city: 'New Delhi' };  
const nextPerson = { ...person, artwork: nextArtwork };  
setPerson(nextPerson);
```

Lo mismo ocurre con los arrays. No hay que utilizar los metodos push, pop, etc y si utilizar metodos como filter, y map para crear un nuevo array para ponerlo en el setArray y asi modificar el estado.
## Props

Las **propiedades o accesorios (o simplemente “props”)** son un objeto que se pasa como argumento al momento de renderizar un nuevo componente React. Este objeto permite al componente recibir información externa e interactuar/comunicarse con otros componentes. Permiten el desacoplamiento de caracteristicas y la reutilizacion de codigo. Los accesorios pueden recordarle los atributos HTML, pero puede pasar cualquier valor de JavaScript a través de ellos, incluidos objetos, matrices y funciones.

```jsx
//Pasar props al componente secundario
export default function Profile() {  
	return (  
		<Avatar  person={{ name: 'Lin Lanying', imageId: '1bX5QH6' }} //Le paso un objeto 
		size={100}  />  //Le paso un numero
	);  
}

//Leer los accesorios dentro del componente secundario
//Puede leer estos accesorios enumerando sus nombres `person, size`separados por comas dentro `({`y `})`directamente después `function Avatar`. Esto le permite usarlos dentro del `Avatar`código, como lo haría con una variable.

function Avatar({ person, size }) {   

}

//Tambien se puede hacer esto
function Avatar(props) {  
	let person = props.person;  
	let size = props.size;  
// ...  

}
```

Podemos darle a un accesorio un valor predeterminado al que recurrir cuando no se especifica ningún valor, puede hacerlo con la desestructuración colocando = y el valor predeterminado justo después del parámetro.

```jsx
//Ejemplo: Si no se le pasa valor a size, este tendra un valor 100.
function Avatar({ person, size = 100 }) {   

}
```

Hay veces que pasar props se vuelven muy repetitivo y dificultan la legibilidad del codigo. Por lo que es conveniente utilizar el "spread".

```jsx
//Ejemplo sin spread

function Profile({ person, size, isSepia, thickBorder }) {  
	return (  
		<div className="card">  
		<Avatar  
		person={person}  
		size={size}  
		isSepia={isSepia}  
		thickBorder={thickBorder}  
		/>  
		</div>  
	);  
}

//Ejemplo con spread

function Profile(props) {  
	return (  
		<div className="card">  
			<Avatar {...props} />  
		</div>  
	);  
}
```

**Datos**: Los props no siempre son estaticos, pueden cambiar durante el tiempo por ejemplo usando useState. Los accesorios son inmutables.

### Children

Cuando anida contenido dentro de una etiqueta JSX, el componente principal recibirá ese contenido en un accesorio llamado `children`. Por ejemplo, el siguiente componente `Card`  recibirá un conjunto de props `children` y lo representará en un div contenedor:

```jsx
import Avatar from './Avatar.js';

function Card({ children }) {
  return (
    <div className="card">
      {children} //Mostrara lo que se le pase a children, en este caso seria Avatar
    </div>
  );
}

export default function Profile() {
  return (
    <Card>
      <Avatar/>
    </Card>
  );
}

```

Puede pensar que un componente con un `children`accesorio tiene un "agujero" que sus componentes principales pueden "rellenar" con JSX arbitrario. A menudo utilizarás el `children`accesorio para envoltorios visuales: paneles, cuadrículas, etc.


![[Pasted image 20230924230508.png]]

[[Estados en profundidad]]