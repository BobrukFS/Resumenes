# Float
Se puede hacer flotar cualquier elemento, para ello se utiliza la propiedad **float**.

* **float** : Esta propiedad permite a un elemento flotar hacia un lado u otro, y ocupar el espacio disponible, incluso cuando tiene que compartir la línea con otro elemento. Los valores disponibles son none (el elemento no flota), left (el elemento flota hacia la izquierda) y right (el elemento flota hacia la derecha).

Ejemplo:

![[Pasted image 20221214094707.png]]
Pensemos en cómo funciona el flotador. El elemento con el flotante establecido (el elemento `<div>` en este caso) se saca del flujo de diseño normal del documento y se pega en el lado izquierdo de su contenedor principal ( `<body>`, en este caso). Cualquier contenido que vendría debajo del elemento flotante en el flujo de diseño normal ahora lo envolverá, llenando el espacio del lado derecho hasta la parte superior del elemento flotante. Allí, se detendrá.

Si bien podemos agregar un margen al flotante para alejar el texto, no podemos agregar un margen al texto para alejarlo del flotante. Esto se debe a que un elemento flotante se saca del flujo normal y las cajas de los siguientes elementos en realidad corren detrás del flotador.

Hemos visto que un flotador se elimina del flujo normal y que otros elementos se mostrarán junto a él. Si queremos evitar que el siguiente elemento se mueva hacia arriba, debemos borrarlo ; Esto se logra con la propiedad **clear**.

* **clear** : Esta propiedad restaura el flujo normal del documento, y no permite que el elemento siga flotando hacia la izquierda, la derecha o ambos lados. Los valores disponibles son none, left, right, y both (ambos).

![[Pasted image 20221214102237.png]]
![[Pasted image 20221214102241.png]]
![[Pasted image 20221214102246.png]]

