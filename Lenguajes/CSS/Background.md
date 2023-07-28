# Background
Los elementos pueden incluir un fondo que se muestra detrás del contenido del elemento y a través del área ocupada por el contenido y el padding.
## Colores de fondo

* **background-color** : Esta propiedad define el color de fondo de cualquier elemento.
## Imagenes de fondo

* **background-image** : La propiedad **background-image** permite la visualización de una imagen en el fondo de un elemento. La imagen se muestra encima del color. La URL del archivo se declara con la función url() (por ejemplo, url("ladrillos.jpg")). Si se requiere más de una imagen, los valores se deben separar por una coma. Las imagenes que se utilizan con background-image suele ser decorativas a diferencia con las que se utilizan con el elemento img que son importantes para el contenido de la pagina. El último valor de imagen es aquel qué se mostrará en la capa más baja o por debajo de todo.

* **background-repeat** : Se utiliza para controlar el comportamiento de mosaico de las imágenes. Los valores disponibles son:

![[Pasted image 20221209220618.png]]

* **background-size** : Sirve para dimensionar la imagen de fondo, puede tomar valores de longitud o porcentaje. O tambien puede tomar los valores de estas palabras claves : 

![[Pasted image 20221209220731.png]]

* **background-position** : La propiedad **background-position** le permite elegir la posición en la que aparece la imagen de fondo en el cuadro al que se aplica. Esto utiliza un sistema de coordenadas en el que la esquina superior izquierda del cuadro es (0,0), y el cuadro se coloca a lo largo de los ejes horizontal (x) y vertical (y). Los valores más comunes background-position toman dos valores individuales: un valor horizontal seguido de un valor vertical. Pueden ser valores en px, o valores como top, bottom, center, left, right.

![[Pasted image 20221209220824.png]]

* **background-origin**:  Esta propiedad determina si la imagen de fondo se posicionará considerando el borde, el relleno o el contenido del área del elemento. Los valores disponibles son border-box, padding-box, y content-box.

* **background-clip**: Esta propiedad declara el área a cubrir por el fondo usando los valores border-box, padding-box, y content-box. El primer valor corta la imagen al borde de la caja del elemento, el segundo corta la imagen en el relleno de la caja y el tercero corta la imagen alrededor del contenido de la caja.

* **background-attachment**: La propiedad **background-attachment** determina si la imagen es estática o se desplaza con el resto de los elementos usando dos valores: scroll (por defecto) y fixed. El valor scroll hace que la imagen se desplace con la página, y el valor fixed fija la imagen de fondo en su lugar original.

![[Pasted image 20221209221131.png]]

* **background-blend-mode**: Esta propiedad es sumamente interesante porque imita los modos de fusión en Photoshop. Sus valores posibles son normal, multiply, screen, overlay, darken, etc.

### Multiples imagenes de fondo

![[Pasted image 20221209221018.png]]
Cada valor de las diferentes propiedades coincidirá con los valores en la misma posición en las otras propiedades.
### Simplificacion de las propiedades
Utilizamos la propiedad **background** para simplificar.

![[Pasted image 20221209221237.png]]

[[Gradientes]]