# Utility Tipes

* `Awaited`: Este tipo esta destinado a modelar operaciones como **await** en funciones **async** o el metodo **.then()** en promesas.
- `Partial`: hace que todas las propiedades de un tipo sean opcionales.
- `Readonly`: hace que todas las propiedades de un tipo sean de solo lectura pero permite la mutabilidad. Solo avisa errores a tiempo real si quiero modificar pero no evita que modifica. Para hacerlo realmente inmutable utilizamos Object.Freeze
- `Pick`: le permite elegir propiedades específicas de un tipo.
- `Omit`: le permite omitir propiedades específicas de un tipo.
- `Exclude`: crea un tipo que es la diferencia establecida de A y B.