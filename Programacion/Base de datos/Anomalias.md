# Anomalias

Una anomalia es un estado inconsistente, incompleto o contradictorio de la base de datos. Si hubiera anomalias presentes en la relacion, esta seria incapaz de representar cierta informacion.

1. **Anomalías de Inserción:**
    - _¿Qué son?_ Ocurren cuando no puedes agregar información (una nueva fila o registro) a una base de datos hasta que tengas detalles adicionales sobre otra entidad.
    - _Ejemplo simple:_ Imagina una tabla de pedidos donde necesitas ingresar un nuevo pedido, pero no puedes hacerlo hasta que tengas el identificador del cliente. No puedes agregar el pedido sin saber a quién pertenece.
2. **Anomalías de Modificación:**
    - _¿Qué son?_ Ocurren cuando cambias un valor en la base de datos, pero no verificas los nuevos valores que estás ingresando, lo que puede llevar a información inconsistente.
    - _Ejemplo simple:_ Supongamos que en una tabla de empleados, decides cambiar el salario de un empleado, pero olvidas validar que el nuevo salario sea un valor lógico. Puedes terminar con salarios incorrectos en la base de datos.
3. **Anomalías de Eliminación:**
    - _¿Qué son?_ Ocurren cuando eliminas una fila o un valor específico y esto afecta a otras partes de la base de datos, generando resultados no deseados.
    - _Ejemplo simple:_ En una tabla de cursos y estudiantes, si eliminas un curso, pero no tienes precauciones, podrías perder información sobre qué estudiantes están inscritos en ese curso