# Renderizado condicional y de listas

Hay veces que necesitamos mostrar cosas diferentes dependiendo de las diferentes condiciones. 
## Renderizado condicional

El renderizado condicional funciona de la misma forma que los condicionales en JavaScript con la diferencia que en React condicionamos renderizado de componentes en la pantalla. Puedo utilizar estructuras de control (if, else), operador ternario (?) o el &&.

![[Pasted image 20230924234135.png]]

En la práctica, regresar `null`de un componente no es común porque podría sorprender a un desarrollador que intenta renderizarlo. Más a menudo, incluiría o excluiría condicionalmente el componente en el JSX del componente principal.
## Renderizado de listas

El renderizado de listas consiste en reutilizar un componente y usarlo para renderizar varias instancias de ese mismo componente pero con varios datos que estan en una matriz. Para lograr esto se utiliza **filter()** y **map()**. 

Una caracteristica principal de este proceso es que los elementos de JSX se generan de forma dinamica con JavaScript, por lo que React necesita que se asigne a cada item una propiedad llamada **key**. El valor de key debe ser unico en toda la lista(puede ser el indice). Las claves le indican a React a qué elemento de la matriz corresponde cada componente, para que pueda compararlos más adelante. Esto se vuelve importante si los elementos de su matriz se pueden mover (por ejemplo, debido a la clasificación), insertarse o eliminarse. Una buena elección `key`ayuda a React a inferir qué sucedió exactamente y realizar las actualizaciones correctas en el árbol DOM. 

Es posible utilizar el índice de un elemento en la matriz como clave. De hecho, eso es lo que usará React si no especificas a `key`en absoluto. Pero el orden en el que se representan los elementos cambiará con el tiempo si se inserta, elimina o si se reordena la matriz. El índice como clave a menudo conduce a errores sutiles y confusos. Si sus datos provienen de una base de datos, se puede utilizar como key las claves/ID o si sus datos se generan y persisten localmente, se puede utilizar un contador incremental o un paquete como uuid cuando se crean elementos.

Ejemplo:

![[Pasted image 20230924234124.png]]

Otro ejemplo:

```jsx
//Filtrar y mapear para renderizar

const chemists = people.filter(person =>  
	person.profession === 'chemist'  
);

const listItems = chemists.map(person =>  
	<li>  
		<img  
		src={getImageUrl(person)}  
		alt={person.name}  
		/>  
		<p>  
			<b>{person.name}:</b>  
			{' ' + person.profession + ' '}  
			known for {person.accomplishment}  
		</p>  
	</li>  
);

return <ul>{listItems}</ul>;
```
