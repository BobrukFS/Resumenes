# Uplifting

Pensemos en el cambio de idioma o el cambio del tema de la aplicacion, para ello hay que reflejar el mismo cambio en datos compartidos en varios componentes. Para ello vamos a usar una estrategia denominada **Uplifting**.

Esta estrategia consiste en **definir una unica "fuente de verdad" lo mas arriba posible del arbol de componentes**.

Una unica fuente de verdad significa que **el estado compartido debe estar almacenado en un solo componente(en lugar de repetirse el mismo dato en varios componentes)**.

Lo mas arriba posible del arbol hace referencia al sentido unidireccional de los cambios de estado: los cambios de estado ocurren de padres a hijos(y no al reves). Para que dos componentes respondan al mismo cambio, ese cambio debe ser hecho en un componente padre que los englobe.

## Implementacion

Para implementar esta estrategia necesitamos gestionar dos comunicaciones: pasar el estado del padre al hijo y notificar cambios de estado del hijo al padre.

● Recordemos que el estado compartido debe estar almacenado en el padre. 
● Pasar el estado del padre al hijo es muy sencillo y se hace a través de las props.

Las props son una excelente forma de pasar un dato de un componente padre a otro hijo. Sin embargo, pasar el estado del hijo al padre no es tan sencillo pues no puede hacerse directamente. Para lograr eso, debemos crear nuestros propios eventos. Podemos recibir en las props funciones cuyo cuerpo esté en el padre y cuya llamada esté en el componente actual. Dicho con otras palabras: este paso consiste en crear una función en el padre (con acceso a su estado), pasarla a través de las props al hijo, y ejecutarla en el hijo cuando sea necesario. Recuerda que lo que estás usando en el hijo, es una función, por lo que puedes pasarle tantos parámetros como quieras.

![[Pasted image 20230924234631.png]]
![[Pasted image 20230924234643.png]]
Si bien esta estrategia es muy útil, no sirve cuando debemos compartir datos a lo largo de muchos elementos del árbol o de forma muy profunda (en vez de padres a hijos, de abuelos a nietos o más). En estos casos, esta estrategia no es recomendable. En su lugar, se opta por Context API o el uso de Redux. Sin embargo, para pequeñas comunicaciones es una estrategia sumamente válida.