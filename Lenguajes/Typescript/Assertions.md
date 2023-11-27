# Assertions

Las aserciones de tipo son una forma de indicarle al compilador que trate un valor como un tipo especifico, independientemente de su tipo inferido.

Hay dos sintaxis para lograr esto:

```ts
//con chorchete angular
let num = 42;
let str = <string>num;

//usando as

let str2 = num as string;

//Ejemplo

const canvas = document.getElementById("Canvas");

if(canfas != null && canvas instanceof HTMLCanvasElement){//por las dudas que no sea canvas se verifica
	const ctx = (canvas as HTMLCanvasElement).getContext("2d"); //aunque al utilizar instanceof ya sabe que es un HTMLCanvas por lo que lo infiere y no hace falta usar assertions
}
```

Utilizando **as const** le estamos diciendo a una expresion que tiene un tipo especifico y que su valor debe tratarse como un valor de solo lectura. El uso de as const permite a TypeScript inferir tipos más precisos para constantes, lo que puede conducir a una mejor verificación de tipos y una mejor inferencia de tipos en su código.

**Dato**: Al hacer llamadas a una API, puede utilizar quicktype para tipar todo el JSON, ponerlo en un archivo y poder utilizar la assesion de tipos como por ejemplo poner as GithubApiResponse. Sin embargo si el json devuelve otra cosa el codigo no funciona, por lo que podemos utilizar Typescript Zod que es una biblioteca que hace validaciones de tipos en tiempo de ejecucion, se evita..