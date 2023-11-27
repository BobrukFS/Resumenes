Permite crear un intermediario para otro objeto, que puede interceptar y redefinir operaciones fundamentales para dicho objeto.

Un Proxy se crea con el constructor new Proxy, que recibe dos parámetros:

● target: el objeto original que se quiere envolver. 
● handler: un objeto que define cuáles operaciones serán interceptadas y cómo redefinir dichas operaciones.

El constructor new Proxy retorna un nuevo objeto con las mismas propiedades y valores que el target.

Su uso radica en implementar el patrón Proxy. Un proxy es un intermediario en la comunicación con un objeto. Podemos pensar en el proxy como un personal de vigilancia que te examina o te saca cosas para que puedas comunicarte con quien quieras. Definimos la lógica del proxy (la conducta del personal de vigilancia, en nuestro ejemplo), en el segundo argumento: el handler.

En el handler, podemos interceptar de las propiedades de un objeto.: 
● lecturas (get)
● escrituras (set)

![[Pasted image 20231021190726.png]]