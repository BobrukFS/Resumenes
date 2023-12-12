# Renderizado

Antes de que sus componentes se muestren en la pantalla, React debe renderizarlos.

Hay dos razones para que un componente se renderice:

1. Es el **renderizado inicial del componente.** : Cuando se inicia su aplicación, debe activar el renderizado inicial.
2. **Se ha actualizado** el estado del componente (o de uno de sus antecesores) . Una vez que el componente se haya renderizado inicialmente, puede activar más renderizados actualizando su estado. La actualización del estado de su componente pone automáticamente en cola un renderizado.
3.  Después de activar un renderizado, React llama a sus componentes para determinar qué mostrar en la pantalla. **"Renderizar" es React llamando a sus componentes.**

- **En el renderizado inicial,** React llamará al componente raíz.
- **Para renderizaciones posteriores,** React llamará al componente de función cuya actualización de estado activó la renderización.

Este proceso es recursivo: si el componente actualizado devuelve algún otro componente, React representará _ese componente a continuación, y si ese componente también devuelve algo,_ _lo_ representará a continuación, y así sucesivamente. El proceso continuará hasta que no haya más componentes anidados y React sepa exactamente qué se debe mostrar en la pantalla.

**Dato**: El comportamiento predeterminado de representar todos los componentes anidados dentro del componente actualizado no es óptimo para el rendimiento si el componente actualizado está muy arriba en el árbol.

Después de renderizar (llamar) sus componentes, React modificará el DOM.

- **Para el renderizado inicial,** React utilizará la API DOM `appendChild()` para poner todos los nodos DOM que ha creado en la pantalla.
- **Para volver a renderizar,** React aplicará las operaciones mínimas necesarias (¡calculadas durante el renderizado!) para que el DOM coincida con la última salida de renderizado.

**React solo cambia los nodos DOM si hay una diferencia entre los renderizados.**

[[Renderizado condicional y de listas]]