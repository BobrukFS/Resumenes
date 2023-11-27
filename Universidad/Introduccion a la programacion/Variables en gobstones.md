# Variables en gobstones

Las expresiones primitivas solo dan informacion de la celda actual, por lo que las **variables** nos permiten recordar informacion en un programa ya que una variable es un espacio en memoria que se le asigna/guarda un valor y es representado con un nombre que se puede usar como expresion.

Para crear una variable ponemos el **nombre** (debe ser un sustantivo) en camelCase seguida de **:=** y el valor. Una variable no existe si la variable no esta **inicializada** es decir si no se le asigno ningun valor por primera vez.

Las variables tienen un **alcance/scope**. El alcance (scope) de una variable es la parte del código donde el valor sigue siendo recordado por la variable. En Gobstones, el alcance es local, es decir, solo en el cuerpo del procedimiento que se asigna.

## Recorrido de acumulacion

Las variables son utiles para realizar un recorrido que permita contar, recuerda la cantidad ya procesada y el recuerdo cambia en cada iteracion. En este caso, la variable se la llama **contador** o **acumulador** y recuerda la cantidad ya procesada.

