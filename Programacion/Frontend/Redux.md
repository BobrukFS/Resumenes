# Redux

Redux es un contenedor predecible del estado de aplicaciones JS. Redux proporciona un conjunto de herramientas y convenciones para gestionar el estado de una manera eficiente y escalable. 
Permite diseñar herramientas de desarrollo muy poderosas, ya que es posible registrar cada modificación que causan las acciones: podrías registrar la sesión de un usuario y reproducirlas ejecutando las mismas acciones.

Redux tambien se puede usar vanilla con los hooks de react.

**Dato**: Se puede usar Redux junto con React o cualquier otra librería de vistas.

```npm
npm install redux 
```

Para instalar Redux, vamos a necesitar una librería de base para su propio código y una librería extra en caso que queramos los bindings con una aplicación React:

```npm
npm install react-redux
```

Todo el **state** de tu aplicación está almacenado en un solo árbol dentro de un **store**. La única forma para cambiar el árbol de estado es emitiendo una **acción**. Para especificar cómo las acciones transforman el árbol de estado, se utilizan **reducers puros** que son funciones.

Redux funciona de la siguiente manera con un flujo de datos estrictamente unidireccional:

1. Los componentes de una aplicación generan acciones. (Realizando llamada a store.dispatch(action)).
2. El store recibe las acciones y las pasa a los reducers. El store pasara dos argumentos al reductor: el arbol de estado actual y la accion.
3. Los reducers actualizan el estado en función de las acciones.
4. El store guarda por completo el arbol de estado devuelto por el reductor raiz, es decir guarda el nuevo estado.
5. Los componentes de la aplicación se suscriben al store para recibir notificaciones sobre los cambios de estado.

![[Pasted image 20231102140916.png]]

Redux puede ser descrito en tres principios fundamentales:

1. **Centralización del estado:** El estado de toda tu aplicación está almacenado en un árbol guardado en un único store. Esto simplifica la tarea de crear aplicaciones universales, ya que el estado en tu servidor puede ser serializado y enviado al cliente sin ningún esfuerzo extra. Además, contar con un único árbol de estado hace más fácil depurar una aplicación y facilita el mantenimiento del estado de la aplicación en desarrollo, para un ciclo de desarrollo más veloz.
 
2. **Estado de solo lectura:** La única forma de modificar el estado es emitiendo una acción, un objeto que describa qué ocurrió. Esto te asegura que ni tu vista ni callbacks de red vayan a modificar el estado directamente. En vez de eso, expresarán un intento de modificar el estado. Ya que todas las modificaciones están centralizadas y suceden en un orden estricto, no hay que preocuparse por una carrera entre las acciones, y como las acciones son objetos planos, pueden ser registrados, serializados y almacenados para volver a ejecutarlos por cuestiones de depuración y pruebas.
4. **Funciones puras para modificar el estado**:  Para especificar cómo el árbol de estado es transformado por las acciones, se utilizan **reducers puros**. Los reducers son funciones puras que toman el estado anterior y una acción y devuelven un nuevo estado. Recuerda devolver un nuevo objeto de estado en vez de modificar el anterior. Puedes comenzar con un único reducer y, mientras tu aplicación crece, dividirlo en varios reducers más pequeños que manejan partes específicas del árbol de estado. Ya que los reducers son funciones puras, puedes controlar el orden en que se ejecutan, pasarle datos adicionales o incluso hacer reducers reusables para tareas comunes como, por ejemplo, paginación.

## State

 El estado es la información que representa el estado actual de una aplicación. Redux almacena el estado en un objeto JavaScript. Podemos tener una carpeta con el estado inicial.
## Acciones

Para cambiar algo en el estado, es necesario enviar una accion. Las **acciones** son un bloque de información que describe lo que sucedio. Son la única fuente de información para el store y las envías usando el comando **store.dispatch()**.

Las acciones son objetos planos de JavaScript. Una acción debe tener una propiedad **type** que **indique el tipo de acción a realizar**. Además del type, el resto de la estructura de los objetos de acciones dependen de ti.

```jsx
const ADD_ITEM = "ADD_ITEM"
const ADD_ITEM = {
	type : ADD_ITEM,
	payload : "Terminar modulo Cobros"
}
```

**Dato**: Para proyectos pequeños, probablemente sea más fácil usar strings directamente para los tipos de acciones. De todas formas, hay algunos beneficios explícitos en declarar constantes en grandes bloques de código.

Segun **flux standar action** una accion puede tener:

* Una propiedad **error**: Se establece en true si la accion representa un error. Una accion que contiene la propiedad error que es true es analoga a una promesa rechazada. Por convencion, la propiedad payload debe ser un objeto de error. En cambio, si es false, null o undefined, la accion no debe interpretarse como un error.
* Una propiedad **payload**: Puede ser cualquier tipo de valor. Representa la carga util de la accion. 
* Una propiedad **meta**: Esta destinado a cualquier informacion adicional que no forme parte de la carga util.

El modulo flux-standar-action esta disponible en npm mediante npm i flux-standard-action. 

```jsx
import {isFSA, isError} from 'flux-standard-action';
```

* **isFSA(action)** devuelve verdadero si action cumple con la FSA.
* **isError(action)** devuelve verdadero si action representa un error.
### Creadores de acciones
Los **creadores de acciones** son exactamente eso: funciones que crean acciones. En Redux, los creadores de acciones son funciones que simplemente regresan una acción.

```jsx
function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```
### Despachar una accion
Para efectivamente iniciar un despacho, pasa la acción a la función dispatch():

```jsx
dispatch(addTodo(text))
dispatch(completeTodo(index))
```

Tambien podemos crear un **creador de acciones conectados** que despache automaticamente.

```jsx
const boundAddTodo = (text) => dispatch(addTodo(text))
const boundCompleteTodo = (index) => dispatch(completeTodo(index))

boundAddTodo(text)
boundCompleteTodo(index)
```

Puedes acceder a la función dispatch() en el store como store.dispatch(), pero tambien se pueden utilizar utilidades como **connect()** de React-Redux. También se puede usar **bindActionCreators()** para conectar automáticamente muchos creadores de acciones a dispatch().

**Dato**: Los creadores de acciones pueden además ser asíncronos y tener efectos secundarios.

Ejemplo:

```jsx
//actions.js
/*
 * tipos de acciones
 */

export const ADD_TODO = 'ADD_TODO'
export const COMPLETE_TODO = 'COMPLETE_TODO'
export const SET_VISIBILITY_FILTER = 'SET_VISIBILITY_FILTER'

/*
 * otras constantes
 */

export const VisibilityFilters = {
  SHOW_ALL: 'SHOW_ALL',
  SHOW_COMPLETED: 'SHOW_COMPLETED',
  SHOW_ACTIVE: 'SHOW_ACTIVE'
}

/*
 * creadores de acciones
 */

export function addTodo(text) {
  return { type: ADD_TODO, text }
}

export function completeTodo(index) {
  return { type: COMPLETE_TODO, index }
}

export function setVisibilityFilter(filter) {
  return { type: SET_VISIBILITY_FILTER, filter }
}
```
## Reducers
El **reducer** es una función pura que toma el estado anterior junto a una acción y devuelve en nuevo estado.

```jsx
(prevState, action) => newState
```

Estas son algunas cosas que nunca deberías hacer dentro de un reducer:

* Modificar sus argumentos. 
* Realizar tareas con efectos secundarios, como llamar a un API o transiciones de rutas. 
* Llamar una función no pura, por ejemplo Date.now() o Math.random().

Entonces, dados los mismos argumentos, debería calcular y devolver el siguiente estado. Sin sorpresas, efectos secundarios, llamadas a APIs ni mutaciones, solo cálculos.

Redux va a llamar a nuestros reducers con undefined como valor del estado la primera vez por lo que debemos configurar el estado inicial.

```jsx
import { VisibilityFilters } from './actions' //Importa el objeto llamado VisibilityFilters. Este objeto contiene los diferentes tipos de filtros de visibilidad que se pueden utilizar, como SHOW_ALL, SHOW_COMPLETED y SHOW_ACTIVE.

// Esta línea define el estado inicial de la aplicación. El estado inicial es un objeto con dos propiedades: visibilityFilter y todos. La propiedad visibilityFilter especifica qué filtro de visibilidad está seleccionado actualmente. La propiedad todos es una matriz de objetos de tareas pendientes.

const initialState = {
  visibilityFilter: VisibilityFilters.SHOW_ALL,
  todos: []
}

//Reductor
function todoApp(state = initialState, action) {
  switch (action.type) {
  // Este manejador de casos maneja acciones de tipo SET_VISIBILITY_FILTER. Estas acciones se envían cuando el usuario cambia el filtro de visibilidad seleccionado. El manejador de casos actualiza la propiedad visibilityFilter del estado al valor especificado en la acción.
    case SET_VISIBILITY_FILTER:
      return Object.assign({}, state, {
        visibilityFilter: action.filter
      })
	 // Este manejador de casos maneja acciones de tipo ADD_TODO. Estas acciones se envían cuando el usuario agrega un nuevo elemento de tarea pendiente. El manejador de casos agrega un nuevo objeto de tarea pendiente a la matriz todos en el estado. El nuevo objeto de tarea pendiente tiene el texto especificado y está marcado como incompleto.
    case ADD_TODO:
      return Object.assign({}, state, {
        todos: [
          ...state.todos,
          { //El nuevo
            text: action.text,
            completed: false
          }
        ]
      })

    case COMPLETE_TODO:
      return Object.assign({}, state, {
        todos: state.todos.map((todo, index) => {
          if(index === action.index) {
            return Object.assign({}, todo, {
              completed: true
            })
          }
          return todo
        })
      })
    default:
      return state
  }
}
```

Cuando tu aplicación crezca, en vez de agregar más stores, divides tu reducer principal en varios reducers pequeños que operan de forma independiente en distintas partes del árbol de estado. Esto es como si sólo hubiese un componente principal en una aplicación de React pero esta estuviese compuesta de muchos componentes pequeños. Este patron se llama **composicion de reducers**.

```jsx
//Ya que todos y visibilityFilter se actualizan de forma completamente separada. Podemos actualizar todos en una funcion separada.
//reducer
function todos(state = [], action) {
  switch (action.type) {
    case ADD_TODO:
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case COMPLETE_TODO:
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: true
          })
        }
        return todo
      })
    default:
      return state
  }
}
//reducer
function todoApp(state = initialState, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return Object.assign({}, state, {
        visibilityFilter: action.filter
      })
    case ADD_TODO:
    case COMPLETE_TODO:
      return Object.assign({}, state, {
        todos: todos(state.todos, action)
      })
    default:
      return state
  }
}

//Podemos tambien seguir extrayendo otro reducer

function visibilityFilter(state = SHOW_ALL, action) {
  switch (action.type) {
  case SET_VISIBILITY_FILTER:
    return action.filter
  default:
    return state
  }
}

//Ahora podemos reescribir el reducer principal como una función que llama a los reducers que controlan distintas partes del estado, y los combina en un solo objeto. Ni siquiera necesita saber el estado inicial. Es suficiente con que los reducers hijos devuelvan su estado inicial cuando reciben `undefined` la primera vez.
```

Ejemplo utilizando la composicion de reducers completa:

```jsx
//reducer
function todos(state = [], action) {
  switch (action.type) {
    case ADD_TODO:
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case COMPLETE_TODO:
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: true
          })
        }
        return todo
      })
    default:
      return state
  }
}
//reducer
function visibilityFilter(state = SHOW_ALL, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return action.filter
    default:
      return state
  }
}
//reducer PRINCIPAL
function todoApp(state = {}, action) {
  return {
    visibilityFilter: visibilityFilter(state.visibilityFilter, action),
    todos: todos(state.todos, action)
  }
}

//Nota que cada uno de estos reducers esta manejando su propia parte del estado global. El parámetro `state` es diferente por cada reducer, y corresponde con la parte del estado que controla.
```

Redux viene con una utilidad llamada **combineReducers()** que realiza la misma logica que crear un reducer principal y tener dentro los reducers hijos.

```jsx
import { combineReducers } from 'redux'

const todoApp = combineReducers({
  visibilityFilter,
  todos
})

export default todoApp

//Es equivalente a

function todoApp(state = {}, action) {
  return {
    visibilityFilter: visibilityFilter(state.visibilityFilter, action),
    todos: todos(state.todos, action)
  }
}

//Además puedes darles diferentes nombres, o llamar funciones diferentes. Estas dos formas de combinar reducers son exactamente lo mismo:

const reducer = combineReducers({
  a: doSomethingWithA,
  b: processB,
  c: c
})

//Es equivalente a

function reducer(state = {}, action) {
  return {
    a: doSomethingWithA(state.a, action),
    b: processB(state.b, action),
    c: c(state.c, action)
  }
}

```

Ya que `combineReducers` espera un objeto, podemos poner todos nuestros reducers en un archivo separado, `export` cada función reductora, y usar `import * as reducers` para obtenerlos todos juntos como objetos con sus nombres como propiedades.

```jsx
import { combineReducers } from 'redux'
import * as reducers from './reducers'

const todoApp = combineReducers(reducers)
```
## Store

El store es el objeto que reune las acciones y los reductores.

* Contiene el estado de la aplicación. 
* Permite el acceso al estado vía **getState()**. 
* Permite que el estado sea actualizado a través de dispatch(action).
* Registra los listeners vía subscribe(listener). 
* Maneja la anulación del registro de los listeners mediante el retorno de la función de subscribe(listener).

Es importante destacar que **sólo se puede tener un store en una aplicación Redux**. Cuando desees dividir la lógica para el manejo de datos, usarás composición de reductores en lugar de muchos stores.

Es fácil crear un store si tienes un reductor. En los ejemplos anteriores, use combineReducers() para combinar varios reductores en uno solo. Ahora lo voy a importar y pasarlo a **createStore()**:

```jsx
import { createStore } from 'redux'
import todoApp from './reducers'
let store = createStore(todoApp)
```

Opcionalmente puedes especificar el estado inicial a través del segundo argumento para createStore(). Esto es útil para hidratar el estado del cliente para que coincida con el estado de una aplicación Redux que se ejecuta en el servidor.

```jsx
let store = createStore(todoApp, window.STATE_FROM_SERVER)
```

Ejemplo:

```jsx
import { addTodo, toggleTodo, setVisibilityFilter, VisibilityFilters } from './actions'

// Mostramos el estado inicial
console.log(store.getState())

// Cada vez que el estado cambie, lo mostramos
// Tenga en cuenta que subscribe() devuelve una función para anular el registro del listener
let unsubscribe = store.subscribe(() =>
  console.log(store.getState())
)

// Enviamos algunas acciones
store.dispatch(addTodo('Aprender sobre acciones'))
store.dispatch(addTodo('Aprender sobre reductores'))
store.dispatch(addTodo('Aprender sobre stores'))
store.dispatch(toggleTodo(0))
store.dispatch(toggleTodo(1))
store.dispatch(setVisibilityFilter(VisibilityFilters.SHOW_COMPLETED))

// Anulamos el monitoreo de las actualizaciones al estado
unsubscribe()
```

![[Pasted image 20231102162834.png]]
## Implementando react redux

La mayoría de los componentes que escribiremos serán de presentación, pero necesitaremos generar algunos componentes contenedores para conectarlos al Store que maneja Redux.

![[Pasted image 20231102122903.png]]

Es el momento de conectar los componentes de presentación a Redux mediante la creación de algunos contenedores. Técnicamente, un componente contenedor es un componente de React que utiliza el llamado store.subscribe () para leer una parte del árbol de estado en Redux y suministrar los props a un componente de presentación que renderiza.

Puedes escribir un componente contenedor de forma manual, pero mi sugerencia es generar los componentes contenedores con la función connect() de la librería React Redux, ya que ofrece muchas optimizaciones útiles para evitar re-renders innecesarios. Un beneficio de utilizar esta librería es que no tienes que preocuparte por la implementación del método shouldComponentUpdate, recomendado por React para mejor rendimiento.

Para usar connect(), es necesario definir una función llamada mapStateToProps que indica cómo transformar el estado actual del store Redux en los props que desea pasar a un componente de presentación.

Por ejemplo 

Nuestro componente necesita calcular propiedades para pasar al componente. Por lo que definimos una función que filtra el que se denomina state.propiedades de acuerdo con state.visibilityFilter y lo usamos en su mapStateToProp

![[Pasted image 20231102123017.png]]

Además de leer el estado, los componentes contenedores pueden enviar acciones. De manera similar, puede definir una función llamada mapDispatchToProps() que recibe el método dispatch() y devuelve los callback props que deseas inyectar en el componente de presentación. Por ejemplo Queremos que el componente inyecte un prop llamado onTodoClick en el componente, y queremos que onTodoClick envíe una acción toggleTodo:

![[Pasted image 20231102123042.png]]

Finalmente, creamos un componente llamando connect() y le pasamos estas dos funciones:

![[Pasted image 20231102123101.png]]

Todos los componentes contenedores necesitan acceso al store Redux para que puedan suscribirse a ella. Una opción sería pasarlo como un prop a cada componente contenedor. Sin embargo, se vuelve tedioso, pues hay que enlazar store incluso a través del componentes de presentación, ya que puede suceder que tenga que renderizar un contenedor allá en lo profundo del árbol de componentes.

La opción recomendada es usar un componente React Redux especial llamado para hacer que el store esté disponible para todos los componentes del contenedor en la aplicación sin pasarlo explícitamente. Solo es necesario utilizarlo una vez al renderizar el componente raíz. 

![[Pasted image 20231102123759.png]]
```jsx
// State
const state = {
  counter: 0,
};

// Reducer
function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return {
        ...state,
        counter: state.counter + 1,
      };
    case "decrement":
      return {
        ...state,
        counter: state.counter - 1,
      };
    default:
      return state;
  }
}

// Store
const store = createStore(reducer);

// Componente
function Counter() {
  const [counter, dispatch] = useSelector((state) => state.counter);

  const increment = () => dispatch({ type: "increment" });
  const decrement = () => dispatch({ type: "decrement" });

  return (
    <div>
      <h1>Counter</h1>
      <p>Counter: {counter}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}

// App
function App() {
  return (
    <div>
      <Counter />
    </div>
  );
}

const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);

```