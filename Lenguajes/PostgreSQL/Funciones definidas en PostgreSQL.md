# Funciones definidas en PostgreSQL
La sintaxis es

```sql
CREATE FUNCTION contarAlumnos (columna VARCHAR(255))
RETURNS INT
language plpgsql
AS
$$
BEGIN
  RETURN (
    SELECT COUNT(columna)
    FROM alumnosQuilmes
  );
END;
$$;
```