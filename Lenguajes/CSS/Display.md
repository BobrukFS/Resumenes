# Display

La propiedad **display** define el tipo de caja usado para presentar el elemento en pantalla. Existen varios valores disponibles para esta propiedad. Los valores mas utilizados son **block, inline, block-inline, flex grid y none(elimina el elemento del documento).**

Las cajas también tienen un tipo de visualización(**display) interna(inner)** que dicta cómo se disponen los elementos dentro de esa caja. De forma predeterminada, los elementos dentro de un cuadro se presentan en flujo normal , lo que significa que se comportan como cualquier otro bloque y elementos en línea. Sin embargo, podemos cambiar el tipo de display interno usando la propiedad **display** con valores como **flex**, **grid**, etc. 

Los elementos estructurales se configuran por defecto con el valor block, mientras que los elementos que representan el contenido normalmente se configuran como inline. Si queremos modificar el tipo de elemento, solo tenemos que asignar la propiedad **display** con un nuevo valor.

## Display block e inline

### Display block

En un **display de block** los elementos se colocaran uno debajo del otro sin importar su tamaño o contenido.

![[Pasted image 20221209203225.png]]
#### Alineamiento

* **margin** : Tambien se puede alinear con el **margin : auto auto** para centrar. 

* **margin-right: auto** para ponerlo a la izquierda. **margin-left: auto** para ponerlo a la derecha.

### Display inline

Si una caja tiene **display inline** los elementos se posicionara de izquierda hacia la derecha al menos que no haya espacio. 

![[Pasted image 20221209203255.png]]
**Dato**: No sirve margin para alinear en un elemento con display inline u display inline:block, para ello lo tendriamos que cambiar el display a block u otro.

### Display inline-block
Proporciona un término medio entre inline y block. Esto es útil para situaciones en las que no desea que un elemento se divida en una nueva línea, pero desea que respete width y height evite la superposición.

![[Pasted image 20221209203325.png]]

[[Display flex]]
[[Display grid]]
