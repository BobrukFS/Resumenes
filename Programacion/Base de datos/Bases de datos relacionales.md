# Bases de datos relacionales

En este tipo de base de datos, los datos estan relacionados conceptualmente, no por su utilizacion y su implementacion en maquina. El centro de los modelos relacionales son las **entidades** y las **relaciones** entre ellas.

Una **base de datos relacional** es un tipo de base de datos que almacena y organiza datos de forma estructurada. Utiliza una estructura que permite identificar y acceder a los datos en relación con otros datos de la base de datos. Los datos de una base de datos relacional se almacenan en varias tablas de datos, cada una de las cuales tiene una clave única que identifica cada fila.

La base de datos relacional nos permite agrupar los datos en forma de **tablas**, donde dentro de las mismas, los datos se organizan en **filas** y **columnas**. La interseccion de un **registro** (fila o tupla) y un **campo** (columna) nos da el dato.

Las bases de datos relacionales pueden utilizar el modelo entidad-relacion como el modelo relacional.

SQL por ejemplo, es un lenguaje de programacion para trabajar con base de datos relacionales.
## ACID
A una base de datos relacional le voy a exigir 4 propiedades ACID que debe respetar:

* **Atomic:** La atomicidad significa que una transacción se ejecuta por completo o no se ejecuta en absoluto. Si una parte de la transacción falla, toda la transacción se deshace. Esto garantiza que los datos de la base de datos siempre estén en un estado consistente. Por ejemplo, si una transacción tiene como objetivo actualizar el saldo de una cuenta bancaria y transferir dinero a otra cuenta, la transacción debe ser atómica. Si la actualización del saldo falla, la transferencia de dinero también debe deshacerse. De lo contrario, el saldo de la cuenta bancaria podría estar en un estado inconsistente. Una **transacción** es un grupo de comandos SQL cuyos resultados serán visibles para el resto del sistema como una unidad cuando la transacción se confirme, o no serán visibles en absoluto si la transacción se anula.
* **Consistent:** La consistencia significa que los datos de la base de datos están siempre en un estado consistente al final de una transacción. Esto significa que todos los datos afectados por una transacción están en un estado válido. Por ejemplo, si una transacción tiene como objetivo agregar un nuevo registro a una tabla, el nuevo registro debe cumplir con todas las reglas de integridad de la tabla. De lo contrario, la transacción no se ejecutará.
* **Isolated:** El aislamiento significa que las transacciones se ejecutan de forma aislada entre sí. Esto significa que los cambios realizados por una transacción no son visibles para otras transacciones hasta que la transacción se completa. El aislamiento se logra mediante mecanismos de bloqueo. Cuando una transacción comienza, bloquea los datos que va a modificar. Otros procesos no pueden acceder a esos datos hasta que la transacción se complete.
* **Durable:** La durabilidad significa que los cambios realizados por una transacción se conservan incluso en caso de fallos del sistema. Esto significa que los datos de la base de datos siempre están disponibles, incluso si el sistema se apaga repentinamente. La durabilidad se logra mediante la escritura de los cambios realizados por una transacción en el almacenamiento permanente. Esto se hace después de que la transacción se haya completado.

La mayoría de los motores de bases de datos relacionales implementan los principios ACID. Esto garantiza que las transacciones sean fiables y consistentes.

- `BEGIN`: Inicia una transacción. Todos los comandos SQL realizados después de `BEGIN` formarán parte de la misma transacción.
- `COMMIT WORK`: Confirma la transacción y aplica todos los cambios realizados durante la transacción. Los cambios se vuelven permanentes.
- `ROLLBACK WORK`: Anula la transacción y deshace todos los cambios realizados durante la transacción. La base de datos vuelve al estado que tenía antes de que comenzara la transacción.
## MVCC

MVCC significa "Multi-Version Concurrency Control" (Control de Concurrencia Multi-Versión) y es un mecanismo utilizado en sistemas de gestión de bases de datos para manejar la concurrencia en ambientes multiusuario. La idea central detrás de MVCC es permitir que múltiples transacciones coexistan de manera concurrente sin interferencias, al tiempo que mantienen una visión consistente de los datos.

1. **Versiones de Datos:**
    - En lugar de actualizar directamente los datos existentes, MVCC crea versiones de los datos para cada transacción.
    - Cada transacción ve una versión consistente y aislada de los datos, independientemente de las operaciones concurrentes de otras transacciones.
2. **Timestamps o Números de Versión:**
    - Cada versión de un dato está asociada con un timestamp o número de versión único.
    - Las transacciones también tienen un timestamp o número de versión que indica cuándo comenzaron.
3. **Lecturas Consistentes:**
    - Las transacciones pueden leer datos sin bloquearlos para otras transacciones.
    - Cada transacción ve la versión de los datos que existía en el momento en que comenzó la transacción.
4. **Escrituras y Conflictos:**
    - Cuando una transacción realiza una escritura, crea una nueva versión de los datos con un nuevo timestamp o número de versión.
    - Si dos transacciones intentan modificar los mismos datos simultáneamente, puede haber conflictos que se deben manejar según las políticas de la base de datos.
5. **Eliminación de Datos:**
    - Las versiones antiguas de los datos pueden eliminarse, pero esto se realiza de manera que no afecte a las transacciones que aún pueden estar utilizando esas versiones.
## Ventajas y desventajas de una base de datos relacional

### Ventajas

* Independencia de los datos y los programas y procesos. Esto permite modificar los datos sin modificar el codigo de las aplicaciones.

- **Datos estructurados** : RDBMS permite el almacenamiento de datos de forma estructurada, utilizando filas y columnas en tablas. Esto facilita la manipulación de los datos mediante SQL (lenguaje de consulta estructurado), lo que garantiza un uso eficiente y flexible.
    
- **Propiedades de ACID** : ACID significa Atomicidad, Consistencia, Aislamiento y Durabilidad. Estas propiedades garantizan una manipulación de datos confiable y segura en un RDBMS, lo que lo hace adecuado para aplicaciones de misión crítica.
    
- **Normalización** : RDBMS admite la normalización de datos, un proceso que organiza los datos de una manera que reduce la redundancia de datos y mejora la integridad de los datos.
    
- **Escalabilidad** : los RDBMS generalmente ofrecen buenas opciones de escalabilidad, lo que permite agregar más almacenamiento o recursos computacionales a medida que crecen los datos y la carga de trabajo.
    
- **Integridad de los datos** : RDBMS proporciona mecanismos como restricciones, claves primarias y claves externas para hacer cumplir la integridad y coherencia de los datos, garantizando que los datos sean precisos y confiables.
    
- **Seguridad** : los RDBMS ofrecen varias funciones de seguridad, como autenticación de usuario, control de acceso y cifrado de datos para proteger datos confidenciales.
### Desventajas

-   Segmentación de los datos: La normalización puede generar consultas complejas que abarcan varias tablas, lo que puede afectar negativamente el rendimiento.

*   Peor rendimiento frente a las bases de datos NoSQL: Los requisitos de consistencia de datos en el modelo relacional pueden disminuir la velocidad de escritura en las transacciones.

* **Escalabilidad horizontal** : los RDBMS no son tan fácilmente escalables horizontalmente como las bases de datos NoSQL. Escalar horizontalmente, lo que implica agregar más máquinas al sistema, puede ser un desafío en términos de costo y complejidad.

* **Manejo de datos no estructurados** : los RDBMS no son adecuados para manejar datos no estructurados como archivos multimedia, publicaciones en redes sociales y datos de sensores, ya que su estructura relacional está optimizada para datos estructurados.

- **Esquema fijo** : RDBMS sigue un esquema rígido para la organización de datos, lo que significa que cualquier cambio en el esquema puede llevar mucho tiempo y ser complicado.

- **Complejidad** : configurar y administrar un RDBMS puede ser complejo, especialmente para aplicaciones grandes. Requiere conocimientos y habilidades técnicos para gestionar, ajustar y optimizar la base de datos.

- **Costo** : Los RDBMS pueden ser costosos, tanto en términos de tarifas de licencia como de recursos computacionales y de almacenamiento que requieren.

[[Modelos de datos]]
[[SQL]]
[[Normalizacion]]
