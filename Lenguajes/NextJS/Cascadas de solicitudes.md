# Cascadas de solicitudes
Una "cascada" se refiere a una secuencia de solicitudes de red que dependen de la finalización de solicitudes anteriores. En el caso de la recuperación de datos, cada solicitud solo puede comenzar una vez que la solicitud anterior haya devuelto datos.

![[Pasted image 20231109215426.png]]
Este patrón no es necesariamente malo. Puede haber casos en los que desee cascadas porque desea que se cumpla una condición antes de realizar la siguiente solicitud. Por ejemplo, es posible que desee obtener primero el ID de un usuario y la información del perfil. Una vez que tengas la identificación, puedes proceder a buscar su lista de amigos. En este caso, cada solicitud depende de los datos devueltos por la solicitud anterior. Sin embargo, este comportamiento también puede ser involuntario y afectar el rendimiento. Una forma común de evitar cascadas es iniciar todas las solicitudes de datos al mismo tiempo, en paralelo.

En JavaScript, puedes usar el`Promise.all()`o `Promise.allSettled()`para iniciar todas las promesas al mismo tiempo. 

Al usar este patrón, puedes:

- Comience a ejecutar todas las recuperaciones de datos al mismo tiempo, lo que puede generar mejoras en el rendimiento.
- Utilice un patrón de JavaScript nativo que se pueda aplicar a cualquier biblioteca o marco.