# Context

**Context** nos proporciona una forma de compartir props entre componentes sin tener que pasar explicitamente una prop a traves de cada nivel del arbol. Es decir, es un mecanismo para compartir datos entre componentes que no están relacionados jerárquicamente. 

Context está diseñado para compartir datos que pueden considerarse “globales” para un árbol de componentes en React, como el usuario autenticado actual, el tema o el idioma preferido.

Context se usa principalmente cuando algunos datos tienen que ser accesibles por muchos componentes en diferentes niveles de anidamiento.

Context no es la única forma de gestionar el estado de las aplicaciones React. Redux también es una opción popular. La principal diferencia entre Redux y React Context es que Redux proporciona una forma centralizada de gestionar el estado, mientras que React Context permite que cada componente gestione su propio estado. En general, Redux es una buena opción para aplicaciones complejas que requieren un estado bien administrado. React Context es una buena opción para aplicaciones más simples que no requieren un estado tan complejo.

Para crear un objeto Context utilizamos

```jsx
const ThemeContext = React.createContext(/*defaultValue o puede ir undefined*/)

//El argumento defaultValue es usado únicamente cuando un componente no tiene un Provider superior a él en el árbol. Este valor por defecto puede ser útil para probar componentes de forma aislada sin contenerlos.
```

Este objeto Context tiene dos propiedades:

* **Provider**: En React, un Provider es un componente que proporciona valores de contexto a sus descendientes. Permite que los componentes que lo consumen se suscriban a los cambios del contexto. El componente Provider acepta una prop value que se pasara a los componentes consumidores que son descendientes de este Provider. Un provider puede estar conectado a muchos consumidores. Los Providers pueden estar anidados para sobreescribir los valores mas profundos dentro del arbol. Todos los consumidores que son descendientes de un Provider se vuelven a renderizar cada vez que cambia la prop value del Provider. La propagación del Provider a sus consumidores descendientes (incluyendo .contextType y useContext) no está sujeta al método shouldComponentUpdate, por lo que el consumidor se actualiza incluso cuando un componente padre evita la actualización.

* **Consumer**: Es un componente de React que se suscribe a cambios de contexto del Provider mas cercano. Al usar este componente puedes suscribirte a un contexto dentro de un componente de función. El componente Consumer requiere una función como hijo: la función recibe el valor de contexto actual y devuelve un nodo de React. El argumento value pasado a la función será igual a la prop value del Provider más cercano para este contexto en el árbol. Si no hay un proveedor superior para este contexto, el argumento value será igual al defaultValue que se pasó a createContext().

```jsx
const ThemeContext = React.createContext();

function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");

  return (
    <ThemeContext.Provider value={theme}>
      {children}
    </ThemeContext.Provider>
  );
}

function ThemeConsumer({ children }) {
  const theme = React.useContext(ThemeContext);

  return (
    <div className={`my-component ${theme}`}>
      {children}
    </div>
  );
}

function App() {
  return (
    <ThemeProvider>
      <ThemeConsumer>
        <h1>This is my component</h1>
      </ThemeConsumer>
    </ThemeProvider>
  );
}

```

Otro ejemplo:

```jsx
const ThemeContext = React.createContext();

function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");

  return (
    <ThemeContext.Provider value={theme}>
      {children}
    </ThemeContext.Provider>
  );
}

function MyComponent() {
  const theme = useContext(ThemeContext);

  return (
    <ThemeContext.Consumer>
      {(theme) => (
        <div className={`my-component ${theme}`}>
          This is my component in {theme} theme
        </div>
      )}
    </ThemeContext.Consumer>
  );
}

function App() {
  return (
    <ThemeProvider>
      <MyComponent />
    </ThemeContext.Provider>
  );
}

```

## Casos de uso para el contexto[](https://react.dev/learn/passing-data-deeply-with-context#use-cases-for-context "Enlace a casos de uso para contexto")

- **Tematización:** si su aplicación permite al usuario cambiar su apariencia (por ejemplo, modo oscuro), puede colocar un proveedor de contexto en la parte superior de su aplicación y usar ese contexto en los componentes que necesitan ajustar su apariencia visual.
- **Cuenta actual:** Es posible que muchos componentes necesiten conocer el usuario que ha iniciado sesión actualmente. Ponerlo en contexto hace que sea conveniente leerlo en cualquier parte del árbol. Algunas aplicaciones también te permiten operar varias cuentas al mismo tiempo (por ejemplo, dejar un comentario como usuario diferente). En esos casos, puede resultar conveniente envolver una parte de la interfaz de usuario en un proveedor anidado con un valor de cuenta corriente diferente.
- **Enrutamiento:** la mayoría de las soluciones de enrutamiento utilizan el contexto internamente para mantener la ruta actual. Así es como cada enlace “sabe” si está activo o no. Si construye su propio enrutador, es posible que también desee hacerlo.
- **Gestión del estado:** a medida que su aplicación crece, es posible que termine con mucho estado más cerca de la parte superior de su aplicación. Es posible que muchos componentes distantes a continuación deseen cambiarlo. Es común [utilizar un reductor junto con el contexto](https://react.dev/learn/scaling-up-with-reducer-and-context) para gestionar estados complejos y transmitirlos a componentes distantes sin demasiadas complicaciones.