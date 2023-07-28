# Minificar codigo

Consiste en reducir el peso de los archivos de código fuente a través de la eliminación de bytes innecesarios —espacios adicionales, saltos de línea, sangrías y comentarios—, además de simplificar todo lo posible la escritura de las sentencias (por ejemplo, usando nombres de variables y funciones más cortos, o evitando lo más posible la repetición). Los lenguajes que se suelen minificar son CSS y Javascript.

## Ventajas

* Se reduce el peso del codigo fuente del sitio web, esto puede acelerar de forma drastica la carga de las paginas.

* Se reduce la cantidad de bytes que necesita nuestro sitio web, por lo que tambien se reduce el espacio ocupado en el servidor y el consumo mensual de ancho de banda.

## Desventajas

* El codigo minificado es extremadamente dificil de depurar: no hay comentarios y todos los errores se produciran en una unica linea larga.

* En JS si no conocemos bien la tecnica, minificar el codigo puede alterar de manera indeseada su funcionamiento.