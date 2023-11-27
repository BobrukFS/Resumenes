# Funciones en Typescript

En TypeScript, las funciones se pueden escribir de diferentes maneras para indicar los parámetros de entrada y el tipo de retorno de la función. Las funciones no tienen inferencia salvo en funciones anonimas segun el contexto

```ts
function add(a: number, b: number = 100): number //tipo de retorno {
  return a + b;
}

//Otra sintaxis

const sumar = (a: number, b: number) : number =>{
	return a + b
}

//Otra sintaxis

const sumar : (a: number, b: number) => number = (a, b) =>{
	return a + b
}


//Otro ejemplo
const multiply = (a: number, b: number): number => {
  return a * b;
};

//Otro ejemplo

const sayHiFromFunction = (fn: (name: string) => void) =>{
	fn("Miguel")
}

const sayHi = (name:string) =>{
	console.log(`Hola ${name}`)
}

sayHiFromFunction(sayHi);

//Inferencia funciones anonimas segun el contexto

const avengers = ["spider", "hulk", "avengers"]

avengers.forEach(function(avenger)){
				 console.log(avenger.toUpperCase()) //Te recomienda un metodo de string
})
```

En TypeScript, una **firma** es una descripción de los tipos de los parámetros y el valor de retorno de una función, interfaz o clase. Las firmas se utilizan para proporcionar información al compilador de TypeScript sobre los tipos de los datos que se pueden utilizar con una función, interfaz o clase.

Ejemplo en react:

```jsx
export function Card({
  title,
  value,
  type,
}: {
  title: string;
  value: number | string;
  type: 'invoices' | 'customers' | 'pending' | 'collected';
}) {
  const Icon = iconMap[type];
  return (
    <div className="rounded-xl bg-gray-50 p-2 shadow-sm">
      <div className="flex p-4">
        {Icon ? <Icon className="h-5 w-5 text-gray-700" /> : null}
        <h3 className="ml-2 text-sm font-medium">{title}</h3>
      </div>
      <p
        className={`${lusitana.className}
          truncate rounded-xl bg-white px-4 py-8 text-center text-2xl`}
      >
        {value}
      </p>
    </div>
  );
}
```


## Funciones genericas
En TypeScript, una función genérica es una función que puede ser utilizada con diferentes tipos de datos. Las funciones genéricas se definen utilizando un parámetro de tipo, que se utiliza para indicar el tipo de datos que se pueden utilizar con la función.

```ts
function maximo<T>(a: T, b: T): T {
  return a > b ? a : b;
}

```
## Function overloading

En TypeScript, la sobrecarga de funciones permite definir varias funciones con el mismo nombre, pero con diferentes firmas. Esto puede ser útil para proporcionar diferentes implementaciones de una función en función de los tipos de los parámetros o del valor de retorno.

Para sobrecargar una función en TypeScript, se deben declarar varias funciones con el mismo nombre, pero con diferentes firmas. Las firmas de las funciones se definen utilizando los tipos de los parámetros y el valor de retorno.

```ts
function loMismo(param: string):string;
function loMismo(param: number):number;
function loMismo(param: any){
    return param
};

//Otro ejemplo
interface loMismoOverload {
    (param:string) : string, //Son funciones genericas
    (param:number) : number, //Son funciones genericas
}

const loMismo: loMismoOverload = (param:any) =>{
    return param
}

//Ya que si no lo hago de este modo, lo puedo hacer de este

function loMismo <T extends string | number>  (param: T) {
  return param;
};
```