# Env

El archivo `.env` es un archivo de texto que se utiliza para almacenar variables de entorno para una aplicación. Las variables de entorno son valores que se pueden usar en el código de una aplicación para personalizar su comportamiento.

El archivo `.env` se coloca en la raíz del proyecto React. El archivo es ignorado por el control de versiones, por lo que los valores de las variables de entorno no se comparten entre los desarrolladores

Para usar el archivo `.env`, las variables de entorno se definen en el archivo de texto. Las variables de entorno se definen en forma de pares clave-valor. La clave es el nombre de la variable de entorno y el valor es el valor de la variable de entorno.

```env
VITE_ENDPOINT_PRODUCTOS=http://localhost:3000/tienda
VITE_ENDPOINT_CARRITO=http://localhost:3000/carrito
```

Para importarlas es lo siguiente:

```jsx
const url = import.meta.env.VITE_ENDPOINT_CARRITO
```