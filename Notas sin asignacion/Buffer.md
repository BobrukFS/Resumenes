# Buffer

## Buffer circular

Un buffer circular, también conocido como buffer cíclico o buffer de anillo, es una estructura de datos que utiliza un único buffer o array ordinario para almacenar y gestionar elementos. La característica principal de un buffer circular es que, al llegar al final del buffer, se vuelve al principio, creando así un flujo continuo de datos [es.wikipedia.org](https://es.wikipedia.org/wiki/Buffer_circular).

Estos buffers tienen un tamaño fijo, lo que significa que no pueden almacenar más elementos de los que pueden contener. Cuando se inserta un nuevo elemento en un buffer lleno, se sobrescribe el elemento más antiguo. Esto puede ser útil en aplicaciones donde sólo se necesita mantener un registro de los últimos elementos procesados, como en sistemas de comunicación, procesamiento de señales y sistemas embebidos.

En resumen, un buffer circular es una estructura de datos que utiliza un array para almacenar elementos de manera cíclica, permitiendo un flujo continuo de datos y sobrescribiendo los elementos más antiguos cuando el buffer está lleno.