# Git grep y git blame

## Git blame

Supongamos que hemos sido capaces de identificar a través de nuestro código un error (bug) y lo que necesitamos es deducir en qué momento se introdujo ese cambio. Permite saber el último commit en el que fue introducida una línea específica de un archivo. **Git blame** se utiliza para rastrear los cambios realizados en un archivo. Es una herramienta muy útil para entender cómo se ha desarrollado un archivo.

Si analizamos el output que nos da la línea de comandos, podemos observar que se nos está brindando el hash del commit que introdujo cada línea escrita en el archivo, junto con el autor, la fecha y hora.

## Git grep

Con git grep podemos hacer una búsqueda común como si estuviéramos trabajando en cualquier editor de código. **Git grep** se utiliza para buscar texto en los archivos de un repositorio Git. Es una herramienta muy útil para encontrar errores o problemas en el código.