# Estado y Props

## Estado

Se define como estado al conjunto de variables reactivas encapsuladas dentro del componente. En otras palabras: el estado son variables que controlan el cambio de la interfaz pero solo en el componente en el que se encuentran (y sus componentes hijos) permitiendo asi la reactividad **focalizada**. A diferencia de las PROPS, son mutables.

Ejemplo: Si quiero mostrar un submenú al hacer clic en un ítem, eso debería controlarse mediante el estado porque es un cambio focalizado. Si, en cambio, quiero cambiar todo el tema del sitio a modo oscuro, eso debería gestionarlo mediante props ya que es un cambio compartido por muchos componentes.

Los componentes funcionales no tienen acceso al estado directamente, para acceder al estado desde un componente funcional debo usar el hook **useState**.

El estado a menudo se llama local o encapsulado. No es accesible desde ningún componente que no sea el que posee y lo establece. Un componente puede elegir pasar su estado como props a sus componentes secundarios. Esto se conoce comúnmente como flujo de datos "descendente" o "unidireccional"
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