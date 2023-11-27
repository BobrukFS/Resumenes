# Importar y exportar en NodeJS

En NodeJS podemos importar y exportar utilizando la sintaxis de commonJS o la sintaxis de los modulos ES6.

Ejemplo con commonJS

```js
//index.js
let someVar = require("./constant"); //Importa

//constant.js
const MPG = 33;
module.exports = MPG; //Exporta
```

Para utilizar la sintaxis de modulos ES6 lo que debemos hacer es:

* usar la extension **.mjs**
* o añadir {"type" : "module"} al archivo package.json principal mas cercano.
