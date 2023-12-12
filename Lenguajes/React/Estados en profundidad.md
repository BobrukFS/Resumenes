# Estados en profundidad
## Pensando en la interfaz de usuario de forma declarativa

1. **Identifique** los diferentes estados visuales de su componente
2. **Determinar** qué desencadena esos cambios de estado.
3. **Representar** el estado en la memoria usando`useState`
4. **Eliminar** cualquier variable de estado no esencial
5. **Conecte** los controladores de eventos (handle event) para establecer el estado

Ejemplo de determinar que desencadena esos cambios de estado:


![[Pasted image 20231210142045.png]]
## Elegir la estructura del estado

1. **Estado relacionado con el grupo.** Si siempre actualiza dos o más variables de estado al mismo tiempo, considere fusionarlas en una sola variable de estado. Otro caso en el que agruparás datos en un objeto o una matriz es cuando no sabes cuántas partes de estado necesitarás. Por ejemplo, es útil tener un formulario donde el usuario puede agregar campos personalizados.
2. **Evite las contradicciones en el estado.** Cuando el Estado está estructurado de tal manera que varias partes del Estado pueden contradecirse y “no estar de acuerdo” entre sí, se deja lugar a errores. Intenta evitar esto.
3. **Evite el estado redundante.** Si puedes calcular alguna información a partir de los props del componente o sus variables de estado existentes durante el renderizado, no debes poner esa información en el estado de ese componente.
4. **Evite la duplicación en el estado.** Cuando los mismos datos se duplican entre múltiples variables de estado o dentro de objetos anidados, es difícil mantenerlos sincronizados. Reduzca la duplicación cuando pueda. Para patrones de interfaz de usuario como la selección, mantenga el ID o el índice en el estado en lugar del objeto en sí.
5. **Evite el estado profundamente anidado.** El estado profundamente jerárquico no es muy conveniente de actualizar. Cuando sea posible, prefiera estructurar el estado de forma plana.

El objetivo detrás de estos principios es _hacer que el estado sea fácil de actualizar sin introducir errores_ . Eliminar datos redundantes y duplicados del estado ayuda a garantizar que todas sus piezas permanezcan sincronizadas.
## Preservar y restablecer el estado

React realiza un seguimiento de qué estado pertenece a qué componente en función de su lugar en el árbol de la interfaz de usuario. Puede controlar cuándo preservar el estado y cuándo restablecerlo entre renderizaciones.

React crea árboles de renderizado para la estructura de componentes en su interfaz de usuario. React asocia cada parte del estado que contiene con el componente correcto según el lugar donde se encuentra ese componente en el árbol de renderizado. Cuando React elimina un componente, destruye su estado.

**React conserva el estado de un componente mientras se renderice en su posición en el árbol de la interfaz de usuario.** Si se elimina o se representa un componente diferente en la misma posición, React descarta su estado.

```jsx
//Ejemplo: No conserva el estado
import { useState } from 'react';

export default function App() {
  const [showB, setShowB] = useState(true);
  return (
    <div>
      <Counter />
      {showB && <Counter />} 
      <label>
        <input
          type="checkbox"
          checked={showB}
          onChange={e => {
            setShowB(e.target.checked)
          }}
        />
        Render the second counter
      </label>
    </div>
  );
}

function Counter() {
  const [score, setScore] = useState(0);
  const [hover, setHover] = useState(false);

  let className = 'counter';
  if (hover) {
    className += ' hover';
  }

  return (
    <div
      className={className}
      onPointerEnter={() => setHover(true)}
      onPointerLeave={() => setHover(false)}
    >
      <h1>{score}</h1>
      <button onClick={() => setScore(score + 1)}>
        Add one
      </button>
    </div>
  );
}

//Ejemplo: conserva el estado

import { useState } from 'react';

export default function App() {
  const [isFancy, setIsFancy] = useState(false);
  return (
    <div>
      {isFancy ? (
        <Counter isFancy={true} /> 
      ) : (
        <Counter isFancy={false} /> 
      )}
      <label>
        <input
          type="checkbox"
          checked={isFancy}
          onChange={e => {
            setIsFancy(e.target.checked)
          }}
        />
        Use fancy styling
      </label>
    </div>
  );
}

function Counter({ isFancy }) {
  const [score, setScore] = useState(0);
  const [hover, setHover] = useState(false);

  let className = 'counter';
  if (hover) {
    className += ' hover';
  }
  if (isFancy) {
    className += ' fancy';
  }

  return (
    <div
      className={className}
      onPointerEnter={() => setHover(true)}
      onPointerLeave={() => setHover(false)}
    >
      <h1>{score}</h1>
      <button onClick={() => setScore(score + 1)}>
        Add one
      </button>
    </div>
  );
}
```

**Dato**: Recuerde que **es la posición en el árbol de la interfaz de usuario (no en el marcado JSX) lo que le importa a React.**

Como regla general, **si desea preservar el estado entre renderizaciones, la estructura de su árbol debe "coincidir"** de una renderización a otra. Si la estructura es diferente, el es

Hay dos formas de restablecer el estado al cambiar entre ellas:

1. Renderizar componentes en diferentes posiciones.
2. Dé a cada componente una identidad explícita con`key`. Puede usar claves para hacer que React distinga entre cualquier componente. De forma predeterminada, React usa el orden dentro del padre ("primer contador", "segundo contador") para discernir entre componentes. Pero las claves te permiten decirle a React que este no es solo un _primer_ contador o un _segundo_ contador, sino un contador específico, por ejemplo, el contador _de Taylor_ . ¡De esta manera, React conocerá el contador _de Taylor_ dondequiera que aparezca en el árbol!

[[Uplifting]]
[[Context]]