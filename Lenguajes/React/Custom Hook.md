# Custom Hook

Un hook tiene el nombre que comenzar con use... Ej: useLocalStorage, useForm.  Tiene que usar aunque sea un hook de los de react (useState, useEffect, useContext). Exportar la función para poder utilizarla en cualquier componente.

Cuando creamos un hook customizado siempre lo debemos nombrar como **use** seguido de lo que hace.

**Dato**: Van en una carpeta llamada hooks.

```jsx
//react.jsx
import {useState, useEffect} from 'react';
const react = () => {
const {data, loading, error, handleCancelRequest} = useFetch('https://pokeapi.co/api/v2/pokemon/ditto'); //desestructuracion del objeto response

//Si quiero hacer un post, en lo mismo que con fetch o axios, debo poner el method y el body en el segundo argumento de useFetch.

  return (<>
   <button onClick={handleCancelRequest}>Cancel Request</button>
    <div>{loading && <p>loading</p>}</div>
    <div>{error && <p>error</p>}</div>
    <div>{data && <p>{data}</p>}</div>
    </>
  )
}
export default react

//useFecth.js es un custom hook

import {useState, useEffect} from 'react';
import React from 'react'

const useFetch = (url) => {
    const [data, setData] = useState();
    const [loading, setLoading] = useState(true);
    const [error, setError] = useState(null);
    const [controller, setController] = useState(null);

    useEffect(() =>{
        const abortController = new AbortController();
        setController(abortController);
        setLoading(true)
        fetch(url, {signal: abortController.signal})
        .then((response)=> response.json())
        .then(data => setData(data))
        .catch((error) => {
            if(error.name === "AbortError"){
                console.log("Request cancelled");
            }
            setError(error);
        })
        .finally(()=> setLoading(false));
        return () => abortController.abort() //Cuando el componente se desmonte, se llama a esta funcion para que la peticion no se complete, por ejemplo al solicitar una peticion pero luego cambias de pagina.
    }, [])

    const handleCancelRequest = () =>{ //Funcion para abortar la peticion
        if(controller){
            controller.abort();
            setError("Request cancelled");
        }
    }
    return {data, loading, error, handleCancelRequest};
}
export default useFetch
```
