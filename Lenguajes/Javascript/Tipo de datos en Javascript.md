# Tipos de datos en Javascript

Un valor almacenado en una variable siempre pertenece a un tipo de dato predeterminado:

## Datos primitivos

Solo pueden contener un tipo de valor 

-   **Undefined :** Es utilizado para denotar la ausencia de un valor de una variable existente.

-   **Boolean:** Es un valor que distingue entre dos posibilidades, true(1) y false(0). Son útiles para determinar el estado actual de una condición.

-   **Number:** Representa tanto números enteros como de punto flotante(decimales). Existen valores numéricos especiales como el **infinity** y **NaN**(Not a Number). Tambien estan los **bigInt** que representa los numeros enteros.
 
-   **String:** Son usados para representar texto. Son escritos encerrando su contenido en comillas. Los strings son inmutables, es decir no podemos cambiar sus caracteres una vez creados.

Para incluir caracteres en un string utilizamos una barra invertida(`\`) y el carácter. Esto se conoce como **escapar el carácter**. Tambien se puede utilizar comillas simples ('') para hacer un string y evitar poner barras invertidas para escapar de los caracteres.

![[Pasted image 20230129220422.png]]
   
Tambien existen los **backticks** (**\`\`**)  que generan **template string** (plantillas literales) que nos permiten incrustar variables y expresiones utilizando **${…}** en un string, además de caracteres especiales, etc., sin la necesidad de la barra invertida u operadores. Estas backticks también nos permiten crear código HTML   

Haciendo comparaciones de strings, una letra minúscula es siempre mayor que una mayúscula. La z es mayor que la a.

```javascript
let variable = `El auto de ${sofia}`
```

-   **Null:** Indica que hay un valor pero ese valor es nulo

* **Symbols**

## Datos no primitivos

Aquellos que pueden almacenar mas de un tipo de dato

-  **Object literal**
-   **Array**
-   **Function**
-  **Map y set** 

[[Conversion de tipos de datos]]
[[Symbols]]




