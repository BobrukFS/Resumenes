# CommonJS

**CommonJS** es un sistema de módulos para JavaScript que se utiliza principalmente en Node.js. En CommonJS, los módulos se exportan mediante la asignación a la propiedad `exports` del módulo.

```js
//suma.js
exports.suma = function (a, b) { //Exporta
	return a + b;;
};

//Si quiero exportar varios
module.exports = {
	let var1 = 1;
	let var2 = 2;
};

//Si quiero importar varios

const {var1, var2} = require('/variables.js');

//main.js
const suma = require("./suma.js"); //Importa
const resultado = suma(1,2);
console.log(resultado)//3
```

**Dato**: CommonJS no permite la importación dinámica de módulos, mientras que ECMAScript modules sí lo permite.