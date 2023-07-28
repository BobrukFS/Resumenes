# Estilos de codificacion en JS
Nuestro codigo debe ser lo mas limpio y facil de leer como sea posible.

![[Pasted image 20230121221938.png]]
Tamaño de linea
![[Pasted image 20230121221951.png]]
Indentacion(sangria)
![[Pasted image 20230121221959.png]]
![[Pasted image 20230121222003.png]]
Colocación de funciones
![[Pasted image 20230121222014.png]]
![[Pasted image 20230121222018.png]]
Guías de estilo

Una guía de estilo contiene reglas generales sobre “cómo escribir” el código, cuáles comillas usar, cuántos espacios para indentar, la longitud máxima de la línea, etc. Muchas cosas menores.

Cuando todos los miembros de un equipo usan la misma guía de estilo, el código se ve uniforme, independientemente de qué miembro del equipo lo haya escrito.

![[Pasted image 20230121222029.png]]
Linters automatizados

Linters son herramientas que pueden verificar automáticamente el estilo de su código y hacer sugerencias de mejora.

Lo mejor de ellos es que la comprobación de estilo también puede encontrar algunos errores, como errores tipográficos en nombres de variables o funciones. Debido a esta característica, se recomienda usar un linter incluso si no desea apegarse a un “estilo de código” en particular.

![[Pasted image 20230121222040.png]]
## ¿Como hacer que nuestro codigo moderno funcione en interpretes mas viejos?
Hay dois herramientas para ello:

1-      **Transpiladores**

2-      **Polyfills**

**Transpiladores**

Un transpilador es un software que traduce un codigo fuente a otro codigo fuente. Puede analizar codigo moderno y rescribirlo usando sintaxis y construcciones mas viejas para que tambien funcione eninterpretes antiguos.

Babel es uno de los mas prominentes transpiladores circulando. Webpack brinda los medios para ejecutar la transpilacion automatica en cada cambio de codigo.

**Polyfills**

Es un script que actualiza o agrega funciones nuevas. Este llena los vacios agregando las implementaciones que faltan.

Nuevas caracteristicas en el lenguaje pueden incluir no solo construcciones sintacticas y operadores, si no tambien funciones integradas. Aquí estamos hablando de nuevas funciones, no de cambios de sintaxis. No hay necesidad de transpilar nada. Solo necesitamos declarar la funcion faltante.

![[Pasted image 20230121222243.png]]