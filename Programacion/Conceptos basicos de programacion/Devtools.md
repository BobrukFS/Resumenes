# Devtools

**Dato:** Si tocamos escape cuando estamos en otra pestaña del devtools se abrira un panel donde podemos poner las pestañas que querramos como console, perfomance monitor, etc.
## Pestaña consola
En ella podemos ejecutar codigo javascript. Es la herramienta mas util para controlar errores y corregir nuestro codigo es la consola. Las consolas estan disponibles en todos los navegadores. El panel Console es el que muestra los errores y mensajes personalizados. Tambien podemos utilizar la terminal para ejecutar codigo de js, poniendo **node ubicacion del archivo que queremos ejecutar**.
## Pestaña source/recursos
La pestaña resource es una pestaña que nos permite trabajar directamente con cada archivo que esta adentro.

![[Pasted image 20230122173023.png]]
**1.** **Zona de recursos:** En la zona de recursos, en la seccion **Page** se lista los archivos HTML, JavaScript, CSS y otros, incluyendo imágenes que estan incluidos en la pagina. Las extensiones de Chromes quizas tambien aparezcan aquí.

En la seccion **Filesystem** podemos agregar una carpeta para que sea nuestro espacio de trabajo, con ello podemos hacer cambios en tiempo real en la devtools y que se vea reflejado en nuestro editor de texto y queden guardados.

Tambien podemos crear **snippets** que son fragmentos de codigos que sirven para reutilizarse o utilizar codigos en fragmentos cuando quiera  ya que quedan guardados, los podemos guardar en nuestra computadora tambien tocando save as . Para ejecutar tocamos control + enter o el logotipo de ejecutar

2. **Zona de recursos :** Muestra el codigo fuente de los archivos.

3. **Zona de informacion y control :** Es para debugging.
## Pestaña network
![[Pasted image 20230122173104.png]]
En esta pestaña tenemos la barra para aplicar filtros.
![[Pasted image 20230122173113.png]]
Luego tenemos una zona donde vemos cuanto tarda cada archivo en cargarse.

![[Pasted image 20230122173128.png]]
Tenemos una zona donde podemos ver los archivos por su nombre, status, tipo, quien los inicializa, el tamaño, y el tiempo que tardan en cargar. Haciendo click derecho y clickeando en headeroptions podemos activar mas informacion para que sea visible. Si hacemos click derecho en un archivo podemos ver mas opciones.

![[Pasted image 20230122173137.png]]
Tenemos una zona de informacion de la pagina donde podemos ver el numero de peticiones, el tamaño de los recursos, cuanto tiempo tardo en cargar el DOM y la pagina.

![[Pasted image 20230122173146.png]]
**Dato:** Algunos archivos se guardan en cache para que cada vez que nosotros entremos a una pagina no tenga que cargar denuevo.
## Pestaña perfomance
Reccord button empieza a grabar desde el momento en el que clickeamos.

Reload button empieza a grabar desde el momento que carga la pagina. Luego de darle al top `podemos ver todo lo que sucedió en la web.

Podemos ver el perfomance monitor para ver los recursos que consume la pagina.

![[Pasted image 20230122174159.png]]
