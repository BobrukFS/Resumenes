# Typed array

Una **Typed array** es un bufer de datos binarios similar a un array. No existe ninguna propiedad u objeto JavaScript llamado TypedArray pero se pueden usar propiedades y metodos con objetos de TypedArrays.

**Los arreglos tipados en JavaScript** son objetos similares a arreglos que proporcionan un mecanismo para leer y escribir datos binarios sin procesar en búferes de memoria.  Los objetos arrays crecen y se encogen dinámicamente y pueden tener cualquier valor de JavaScript. Los motores de JavaScript realizan optimizaciones para que estos arreglos sean rápidos.

Sin embargo, a medida que las aplicaciones web se vuelven cada vez más poderosas, agregando características como manipulación de audio y video, acceso a datos sin procesar usando `WebSockets`, etc., ha quedado claro que hay momentos en los que sería útil que el código JavaScript pudiera manipular rápida y fácilmente datos binarios sin procesar. Aquí es donde entran en juego los arreglos tipados. Cada entrada en un arreglo tipado de JavaScript es un valor binario sin procesar en uno de los formatos admitidos, desde números enteros de 8 bits hasta números de punto flotante de 64 bits.