# Objeto Number

Métodos y propiedades del objeto Number:

* **toString(base) :** Devuelve un string con la representación de un numero, en el sistema numérico con la base especificada. La base puede variar entre 2 y 36. La predeterminada es 10. La base 16 es usada para colores hex, etc ya que los dígitos van de 0 a 9 o A a F. La base 2 es mayormente usada para el debug de operaciones de bit ya que los dígitos son de 0 o 1. La base 36 es el máximo, los dígitos pueden ser 0 a 9 o A a Z. Tambien se puede utilizar para transformar un numero a un string let string = "" + num.

* **toFixed(n)** **:** Redondea el número a n dígitos después del punto decimal y devuelve una cadena que representa el resultado.