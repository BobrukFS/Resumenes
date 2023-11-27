# Importaciones dinamicas

  
La importación dinámica es una característica de JavaScript que permite importar módulos en tiempo de ejecución. Esto significa que el módulo no se carga al inicio de la aplicación, sino que solo se carga cuando se necesita.

La importación dinámica se puede utilizar para cargar módulos de forma condicional, según las necesidades de la aplicación. Por ejemplo, se puede utilizar para cargar un módulo que solo se necesita para una determinada ruta o función.

La importación dinámica también se puede utilizar para cargar módulos de forma asíncrona. Esto puede mejorar el rendimiento de la aplicación, ya que los módulos no se cargan hasta que son necesarios.

En JavaScript, la importación dinámica se puede realizar utilizando la función `import()`. La función `import()` acepta una ruta al módulo como argumento. La ruta puede ser una URL, un nombre de archivo o una expresión que devuelve una URL o un nombre de archivo

```js
//Ejemplo 1: Cargar un modulo condicionalmente
// Comprobar si el usuario ha iniciado sesión
const isLoggedIn = localStorage.getItem("isLoggedIn");

// Importar el módulo `login.js` de forma condicional
if (!isLoggedIn) {
  const module = await import("./login.js");
  // Iniciar sesión al usuario
  module.login();
}

//Ejemplo 2 : Cargar un modulo de forma asincrona
async function main() {
  // Importar el módulo `module.js` de forma asíncrona
  const module = await import("./module.js");

  // Llamar a la función del módulo
  const resultado = await module.funcionAsincrona();

  // Imprimir el resultado
  console.log(resultado);
}

main();

```