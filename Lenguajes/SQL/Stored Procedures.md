# Stored procedures

Un stored procedure es un subprograma que se almacena en la base de datos y se puede ejecutar como si fuera una instrucción SQL. Los stored procedures son útiles para encapsular código reutilizable y simplificar la ejecución de tareas complejas.

La sintaxis de los stored procedures es similar a la de las funciones, pero los stored procedures no tienen que devolver un valor.

```sql
CREATE PROCEDURE nombre_procedimiento (
  parámetro1 tipo_de_dato,
  parámetro2 tipo_de_dato,
  ...
)
AS
BEGIN
  cuerpo_del_procedimiento
END;

--Ejemplo:

CREATE PROCEDURE insertar_registro (
  nombre VARCHAR(255),
  apellido VARCHAR(255),
  edad INT
)
AS
BEGIN
  INSERT INTO clientes (nombre, apellido, edad)
  VALUES (nombre, apellido, edad);
END;

```


Los stored procedures se pueden utilizar para realizar una amplia variedad de tareas, como:

- **Insertar, actualizar o eliminar datos en una base de datos.**
- **Realizar cálculos complejos.**
- **Validar datos de entrada.**
- **Enviar correos electrónicos u otros tipos de notificaciones.**
- **Integrar con otras aplicaciones.**

Los stored procedures también se pueden utilizar para mejorar el rendimiento de las aplicaciones, ya que el código del stored procedure se puede almacenar en caché y reutilizar en lugar de volver a compilarlo cada vez que se llama.

Aquí hay algunos ejemplos de cómo se pueden utilizar los stored procedures:

- Supongamos que tienes una tabla de clientes y quieres insertar un nuevo registro en la tabla. Puedes crear un stored procedure que inserte el nuevo registro en la tabla y que también envíe un correo electrónico de bienvenida al nuevo cliente.
- Supongamos que tienes una tabla de pedidos y quieres calcular el importe total de un pedido. Puedes crear un stored procedure que calcule el importe total del pedido y que también devuelva un mensaje de error si el importe total del pedido es superior al límite de crédito del cliente.
- Supongamos que tienes una tabla de productos y quieres validar la dirección de correo electrónico de un producto antes de insertarlo en la tabla. Puedes crear un stored procedure que valide la dirección de correo electrónico del producto y que devuelva un mensaje de error si la dirección de correo electrónico no es válida.