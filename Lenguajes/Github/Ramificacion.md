# Ramificacion

Cuando nosotros inicializamos el repositorio, git inicializa una rama que se llama master (o main). En git podemos tener tantas ramas como querramos.

**Dato:** Git no creará una **master (main)** rama hasta que confirmes algo.

La ramificación significa que te desvías de la línea principal de desarrollo y continúas trabajando sin alterar esa línea principal. Permite trabajar simultáneamente, estas ramas son independientes de la rama principal, y nosotros podemos hacer un merge para fusionar.

Una rama representa una línea independiente de desarrollo. Las ramas sirven como una abstracción de los procesos de cambio, preparación y confirmación. Pueden concebirse como una forma de solicitar un nuevo directorio de trabajo, un nuevo entorno de ensayo o un nuevo historial de proyecto. Las nuevas confirmaciones se registran en el historial de la rama actual, lo que crea una bifurcación en el historial del proyecto.

Git sabe en que rama estamos en cualquier momento mediante un apuntador especial denominado **HEAD**. HEAD es el apuntador a la rama local en la que estemos en este momento.

![[Pasted image 20221225231021.png]]
* **Git Branch** : Nos indica las ramas disponibles, y en verde es la que estamos.

* **Git Branch nombre** : Para crear una rama.

![[Pasted image 20221225231049.png]]
* **Git checkout -B nombre :** Para crear rama y cambiarse a dicha rama.

* **Git checkout nombre**: Para cambiar de rama.

* **Git switch** : Para cambiar de rama.

* **Git switch -c** : Para crear rama y cambiarse a dicha rama.

* **Git switch -** : Cambia a la ultima rama.

**Dato**: Git switch es mas seguro porque esta diseñado especificamente para cambiar entre ramas y puntos de confirmación.

* **Cat nombre:** Nos muestra el contenido del archivo.

* **Git Branch -d nombre:** Para eliminar una rama. Una vez que hayas terminado de trabajar en una rama y la hayas fusionado con el código base principal, puedes eliminar la rama sin perder ninguna historia. No obstante, si la rama no se ha fusionado, el comando anterior mostrará un mensaje de error: “error: The branch 'crazy-experiment' is not fully merged. If you are sure you want to delete it, run 'git branch -D crazy-experiment'.” Esto te protege ante la pérdida de acceso a una línea de desarrollo completa. Si realmente quieres eliminar la rama (por ejemplo, si se trata de un experimento fallido), puedes usar el indicador **-D** (en mayúscula).

* **Git Branch -m nombre :** Para cambiar el nombre de la rama en la que estamos.

* **Git Branch -a :** Para listar todas las ramas en el repositorio remoto incluso las ocultas.

*  **Git branch -av** : Para visualizar las ramas y el HEAD en el que estamos.

## Git merge

La fusión es la forma que tiene Git de volver a unir un historial bifurcado. El comando **git merge** **branch** permite tomar las líneas independientes de desarrollo creadas por git branch e integrarlas en una sola rama. Git merge branch fusiona en la rama en la que estamos ubicados actualmente la rama branch.

**git merge** combinará varias secuencias de confirmaciones en un historial unificado. En los casos de uso más frecuentes, git merge se utiliza para combinar dos ramas. git merge toma dos punteros de confirmación, normalmente los extremos de la rama, y encuentra una confirmación base común entre ellos. Una vez que Git encuentra una confirmación base en común, crea una **"confirmación de fusión" nueva** que combina los cambios de cada secuencia de confirmación de fusión puesta en cola.

Las confirmaciones de fusión son únicas con respecto a otras confirmaciones en el hecho de que tienen dos confirmaciones principales. Al crear una confirmación de fusión, Git tratará de fusionar automáticamente los historiales independientes. Sin embargo, si encuentra datos que se han cambiado en ambos historiales, no podrá combinarlos de ese modo. En ese caso, se crea un conflicto de control de versiones y Git solicitará la intervención del usuario para poder continuar de forma manual.

Para **abortar una fusion** se utiliza **git merge --abort**.

### Preparacion para fusionar

1.Ejecuta git status para asegurarte de que HEAD apunte a la rama de fusión-recepción correcta. En caso necesario, ejecuta git checkout para cambiar a la rama de recepción.

2. Asegúrate de que la rama de recepción y la rama de fusión están actualizadas con los cambios remotos más recientes. Ejecuta git fetch para incorporar los cambios de las confirmaciones remotas más recientes. Una vez que la recuperación se haya completado, asegúrate de que la rama main tenga las actualizaciones más recientes mediante la ejecución del comando git pull.

3.   Una vez adoptados los pasos comentados anteriormente de "preparación para la fusión", se puede iniciar una fusión ejecutando git merge donde  es el nombre de la rama que se fusionará con la rama de recepción.

## Tipos de fusiones

* **Fusion con avance rapido (Fast-foward)** :  Puede que se produzca una fusión con avance rápido cuando hay un proceso lineal desde el extremo de la rama actual hasta la rama de destino. En lugar de fusionar “realmente” las ramas, lo único que tiene que hacer Git para integrar los historiales es mover el extremo de la rama actual al extremo de la rama de destino (es decir, realizar un “avance rápido”).

![[Pasted image 20221226011549.png]]
![[Pasted image 20221226011553.png]]

En caso de necesitar una confirmación de fusión durante una fusión con avance rápido para mantener registros, es posible ejecutar **git merge --no-ff rama**. Este comando fusiona la rama especificada en la rama actual, pero siempre genera una confirmación de fusión (incluso si se trata de una fusión con avance rápido). Esto resulta útil para documentar todas las fusiones que tienen lugar en tu repositorio.

* **Fusion de 3 vias:** Sin embargo, no es posible una fusión con avance rápido si las ramas han divergido. Cuando no hay un proceso lineal hacia la rama de destino, Git no tiene más opción que combinarlas mediante una fusión de 3 vías. Las fusiones de 3 vías utilizan una confirmación específica para unir dos historiales. Esta fusión recibe su nombre del hecho de que Git utiliza tres confirmaciones para generar la confirmación de fusión: los dos extremos de la rama y su predecesor común.

![[Pasted image 20221226011644.png]]
![[Pasted image 20221226011648.png]]


### Resolución de conflicto de fusion manual

Si las dos ramas que tratas de fusionar han cambiado la misma parte del mismo archivo, Git no podrá averiguar qué versión utilizar. Cuando esto ocurre, Git se detiene justo antes de la confirmación de fusión para que puedas resolver los conflictos manualmente. Cuando se observa un conflicto de fusión, la ejecución del comando git status muestra qué archivos se deben resolver.

Cuando Git se encuentra un conflicto durante una fusión, editará el contenido de los archivos afectados con indicadores visuales que marquen ambos extremos del contenido conflictivo. Estos marcadores visuales son: `<<<<<<<, ======= y >>>>>>>`. Es útil buscar un proyecto para estos indicadores durante una fusión con el fin de encontrar dónde hay que resolver los conflictos. Normalmente, el contenido que se encuentra delante del marcador ======= es la rama de recepción y el de la parte de detrás es la rama de fusión.

Una vez identificadas las secciones conflictivas, puedes entrar y arreglar la fusión a tu gusto. Cuando estés listo para terminar la fusión, lo único que tienes que hacer es ejecutar git add en los archivos conflictivos para indicar a Git que se han resuelto. Seguidamente, ejecutas un git commit normal para generar la confirmación de fusión.

## Rebase

Para volver a tener una estructura lineal de trabajo, lo que podemos hacer es utilizar git rebase nombre rama, que permite llevar los cambios confirmados en un branch y aplicarlos sobre otro en vez de fusionar a tres bandas.

Para esto nos dirigimos a aquel bran que se habia bifurcado y que queremos tener de manera lineal y luego ponemos git rebase `<branch>`

![[Pasted image 20230724165218.png]]

![[Pasted image 20230724165236.png]]

Nunca reorganices confirmaciones de cambio (commits) que hayas enviado (push) a un repositorio público.