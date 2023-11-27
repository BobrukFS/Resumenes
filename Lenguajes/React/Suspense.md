# Suspense

En React, `Suspense` es un componente que se utiliza para gestionar la carga de datos asincrónicos de manera más eficiente y proporcionar una mejor experiencia al usuario cuando se están obteniendo datos de fuentes externas, como una API o una carga de componentes.

En React, Suspense se utiliza para pausar el render de un componente hasta que los datos asíncronos se resuelvan. Esto se puede utilizar para crear una sensación de suspenso al ocultar información o contenido al usuario hasta que se haya cargado.

Por ejemplo, imaginemos que tenemos un componente que muestra una lista de artículos. El componente podría utilizar Suspense para pausar el render de la lista hasta que se hayan cargado los datos de los artículos. Esto crearía una sensación de suspenso, ya que el usuario no sabría qué artículos hay en la lista hasta que se hayan cargado.

Para utilizar Suspense, debemos envolver el componente que queremos pausar en un componente `<Suspense>`. Dentro del componente `<Suspense>`, podemos proporcionar un componente de fallback que se mostrara al usuario mientras los datos se estan cargando.

```jsx
//react.jsx

import {useState, useEffect} from 'react';
import {Suspense} from "react";
import {fetchData} from '/fetchData';
const apiData = fetchData('https://pokeapi.co/api/v2/pokemon/ditto');

const react = () => {
        const data = apiData.read()
        
  return (<>
    <Suspense fallback={<div>Loading...</div>}>//Si no se cargan sus hijos
        <p>{data}</p>//Si se carga se muestra.
    </Suspense>
    </>
  )
}

export default react

//fetch.js
import {useState, useEffect} from 'react';
import React from 'react'

function getSuspeder(promise){
    let status = "pending";
    let response;
    const suspender = promise.then(
	        (res) => { //Si se cumple la promesa, el estado de la promise pasa a success y la respuesta es el objeto response que devuelve el then.
            status = "success";
            response = res;
        },
        (err) => {
            status = "error";
            response = err;
        }
    );

    const read = () => {
        switch(status){ //Si no es ni pending ni error, devuelve response.
            case "pending" : throw suspender;
            case "error"   : throw response;
            default : return response;
        }
    }
    return {read};
}

export function fetchData(url){
    const promise = fetch(url)
    .then((response)=> response.json())
    .then((data)=>data);
    return getSuspender(promise); 
}
```

[[Fallback]]