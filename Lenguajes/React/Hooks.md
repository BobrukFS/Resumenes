# Hooks

Los **Hooks** son una forma de desacoplar características en React. Los Hooks son funciones integradas que realizan tareas preestablecidas, como darle a su componente la capacidad de almacenar estado (gancho useState) o permitirle realizar efectos secundarios (gancho useEffect) al cargar sus componentes, similar a eventos de ciclo de vida como componenteDidMount en componentes de clase.

Las funciones que comienzan con **use** se llaman  **Hooks** . React viene ya con varios ganchos integrados [referencia de la API.](https://react.dev/reference/react) Sin embargo, también se puede escribir nuestros propios Hooks personalizados combinando los existentes.

Los ganchos son más restrictivos que otras funciones. Solo puede llamar Hooks en la parte superior de sus componentes (u otros Hooks). Si por ejemplo, deseamos utilizar useState en una condicion o en un bucle, debemos extraer un nuevo componente y colocarlo alli.


```jsx
//Ejemplo usando useEffect

const App = () => {

  const [value, setValue] = React.useState(
    localStorage.getItem('myValueInLocalStorage') || '',
  );

  React.useEffect(() => {

    localStorage.setItem('myValueInLocalStorage', value);

  }, [value]);

  const onChange = event => setValue(event.target.value);

  return (

    <div>

      <h1>Hello React Function Component!</h1>

      <input value={value} type="text" onChange={onChange} />

      <p>{value}</p>

    </div>

  );

};

//El código que has compartido es un componente de función de React que crea un formulario simple con un campo de entrada de texto. Aquí está lo que hace cada parte del código: - El estado `value` se inicializa utilizando el valor almacenado en `localStorage` con la clave "myValueInLocalStorage". Si no hay ningún valor en `localStorage` , se inicializa como una cadena vacía. - Se utiliza el hook `useEffect` para guardar el valor actual de `value` en `localStorage` cada vez que cambia. - La función `onChange` se ejecuta cuando se produce un cambio en el campo de entrada de texto y actualiza el estado `value` con el nuevo valor. - El componente renderiza un título `<h1>` que dice "¡Hola, React Function Component!". - Renderiza un campo de entrada de texto `<input>` que muestra el valor actual almacenado en el estado `value` y llama a la función `onChange` cuando cambia. - Renderiza un párrafo `<p>` que muestra el valor actual del estado `value` . En resumen, este componente de función de React muestra un formulario simple que guarda y muestra el valor ingresado en un campo de entrada de texto utilizando el almacenamiento local del navegador.
```

## UseState

El Hook useState permite acceder al estado de React. Se utiliza para crear variables de estado, es decir, variables que, al cambiar, ocasionan una actualización de los componentes relacionados. 

useState es un hook de React que permite gestionar el estado de un componente de forma declarativa. Para ello, crea una variable de estado que recibe el valor por defecto que queremos que tenga. A continuación, devuelve un array con dos valores:

- **En la posición 0, se encuentra una variable JS para leer el valor de la variable de estado.** Esta variable se puede utilizar en el componente para acceder al valor del estado.
- **En la posición 1, se encuentra una función JS para escribir el valor de la variable de estado.** Esta función se puede utilizar para actualizar el valor del estado.

```jsx
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
## UseEffect

Con este hook, le estamos indicando a React que el componente tiene que hacer algo después de renderizarse por primera vez o cuando se produce un cambio en uno de los valores de estado o dependencias del componente. React recordará la función que le hemos pasado (nos vamos a referir a ella como nuestro “efecto”) y la llamará más tarde después de actualizar el DOM.

useEffect tiene dos argumentos, el primero es la funcion que el codigo ejecutara. Este codigo puede acceder a los valores de estado y dependencias del componente. 

El segundo argumento es un array de valores de dependencia. Cuando alguno de estos valores que se pasen en el array cambie, el codigo de useEffect se volvera a ejecutar. Por ejemplo si ponemos data, el useEffect se ejecutara cuando la variable data haya sido cuando cambie.

```jsx
// Ejemplo de uso de useEffect para llamar a una API
function Example() {
  const [data, setData] = useState([]);

  useEffect(() => {
    // Llamamos a la API
    fetch("/api/data")
      .then((response) => response.json())
      .then((data) => setData(data));
  }, [data]); //Entonces al iniciarse capaz data sea undefined pero cuando lleguen los datos se vuelve a ejecutar. Es una forma de manejar ese error.

  return (
    <div>
      <p>Los datos son: {data}</p>
    </div>
  );
}
```
## UseContext

El Hook `useContext()` sirve para consumir valores de contexto de un Provider. Para utilizar el Hook `useContext()`, debemos pasar como argumento el contexto que queremos consumir. El Hook devuelve el valor del contexto actual.

```jsx
const ThemeContext = React.createContext();
const theme = useContext(ThemeContext);
```
## Hooks en React Router

### UseRoutes

Este hook es un reemplazo al **Routes** y **Route**. Sirve para implementar la misma logica que esos dos componentes pero de forma programatica en JavaScript.

Este hook recibe como argumento una array de objetos. Cada objeto puede tener las mismas propiedades que un Route, incluyendo la propiedad Children.

El hook useRoute retorna un elemento de React listo para ser renderizado en JSX o retornado directamente por un componente.

![[Pasted image 20231028214959.png]]
### UseNavigate

El hook useNavigate retorna una función que hace exactamente lo mismo que el componente Navigate. Nos puede ser muy útil cuando necesitamos realizar una redirección de forma programática en lugar de JSX (como por ejemplo en el handler de un evento).

![[Pasted image 20231028215112.png]]

**Dato**: Forma programatica significa en JS en vez de JSX, es decir, que no es codigo de marcado.
### UseParams

El hook **useParams permite acceder a los parámetros pasados por la URL**.

El hook retorna un objeto JavaScript plano donde las claves son los nombres definidos en la ruta (los segmentos que empiecen con dos puntos) y los valores son los caracteres ubicados en esa posición de la ruta.

Ejemplo:

![[Pasted image 20231028215359.png]]

El símbolo `:` se utiliza para definir parámetros de ruta obligatorios. Los parámetros de ruta obligatorios deben especificarse en la URL. Si no se especifican, el navegador devolverá un error.

El símbolo `@` se utiliza para definir parámetros de ruta opcionales. Los parámetros de ruta opcionales pueden o no especificarse en la URL. Si no se especifican, el valor del parámetro de ruta será `undefined`.
### UseSearchParams

**UseSearchParams** nos permite leer los parametros query string, es decir los parametros de busqueda de la URL del navegador. `seSearchParams` proporciona un objeto `SearchParams` que se puede usar para acceder a los parámetros de búsqueda de la URL. El objeto `SearchParams` tiene métodos para obtener, establecer y eliminar parámetros de búsqueda.

## Reglas de hooks

* 🔴 No puede poner un hook dentro de otro hook.
* 🔴 No llames Hooks dentro de condiciones o bucles.
- 🔴 No llames a Hooks después de una `return`declaración condicional.
- 🔴 No llame a Hooks en controladores de eventos.
- 🔴 No llames a Hooks en componentes de clase.
- 🔴 No llame a Hooks dentro de funciones pasadas a `useMemo`, `useReducer`o `useEffect`.

[[Custom Hook]]