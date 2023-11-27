# Triggers

En el contexto de las bases de datos, un **trigger** es un procedimiento almacenado que se ejecuta automáticamente en respuesta a un evento específico que ocurre en la base de datos. Los triggers se utilizan para automatizar tareas y mantener la integridad de los datos. Permite ejecutar funciones o  Stores Procedures ante determinados eventos.

Los eventos que pueden desencadenar un trigger incluyen:

- **INSERT:** Cuando se inserta una nueva fila en una tabla.
- **UPDATE:** Cuando se actualiza una fila existente en una tabla.
- **DELETE:** Cuando se elimina una fila de una tabla

Los triggers también pueden ser condicionales, lo que significa que solo se ejecutan si se cumple una determinada condición. Por ejemplo, puedes crear un trigger que envíe un correo electrónico a un administrador de la base de datos cada vez que se inserte un nuevo registro en una tabla específica.

Cuando se desencadenara un trigger:

* **BEFORE**: Antes
* **AFTER** : Despues
* **INSTEAD OF**: Se ejecuta en lugar de la operacion que activa el trigger.


Ejemplo

```sql
CREATE TRIGGER check_update    
	BEFORE UPDATE OF balance ON 
accounts    
	FOR EACH ROW    
	EXECUTE FUNCTION 
	check_account_update();
```

Otro ejemplo:

```sql
CREATE TRIGGER before_insert_trigger 
BEFORE INSERT ON your_table 
FOR EACH ROW 
EXECUTE FUNCTION before_insert_trigger_function();
```