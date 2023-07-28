# Git flow

Gitflow es un modelo alternativo de creación de ramas en Git en el que se utilizan ramas de función y varias ramas principales. Estas ramas de función de larga duración requieren más colaboración para la fusión y tienen mayor riesgo de desviarse de la rama troncal. También pueden introducir actualizaciones conflictivas. Gitflow puede utilizarse en proyectos que tienen un ciclo de publicación programado, así como para la práctica recomendada de DevOps de entrega continua. Lo que hace es asignar funciones muy específicas a las distintas ramas y definir cómo y cuándo deben estas interactuar. Además de las ramas de función, utiliza ramas individuales para preparar, mantener y registrar publicaciones.

Para inicializar git flow en la terminal git hay que realizar este comando **git flow init**.
## Ramas principales y de desarrollo
En lugar de una única rama main, este flujo de trabajo utiliza dos ramas para registrar el historial del proyecto. La rama main o principal almacena el historial de publicación oficial y la rama develop o de desarrollo sirve como rama de integración para las funciones. Asimismo, conviene etiquetar todas las confirmaciones de la rama main con un número de versión.

![[Pasted image 20221226020456.png]]
El primer paso es complementar la rama main predeterminada con una rama develop. Una forma sencilla de hacerlo es que un desarrollador cree de forma local una rama develop vacía y la envíe al servidor:

![[Pasted image 20221226020505.png]]
Esta rama contendrá el historial completo del proyecto, mientras que main contendrá una versión abreviada. A continuación, otros desarrolladores deberían clonar el repositorio central y crear una rama de seguimiento para develop.

A la hora de utilizar la biblioteca de extensiones de git-flow, ejecutar **git flow init** en un repositorio existente creará la rama develop.

![[Pasted image 20221226020521.png]]
## Ramas de funcion(feature)
Todas las funciones nuevas deben residir en su propia rama, que se puede enviar al repositorio central para copia de seguridad/colaboración. Sin embargo, en lugar de ramificarse de main, las ramas feature utilizan la rama develop como rama primaria. Cuando una función está terminada, se vuelve a fusionar en develop. Las funciones no deben interactuar nunca directamente con main.

![[Pasted image 20221226020539.png]]
### Creacion de una rama de funcion

![[Pasted image 20221226020552.png]]

### Finalizacion de una rama de funcion
Cuando hayas terminado con el trabajo de desarrollo en la función, el siguiente paso es fusionar feature_branch en develop.

![[Pasted image 20221226020609.png]]
## Ramas de publicacion (release)
Cuando develop haya adquirido suficientes funciones para una publicación (o se acerque una fecha de publicación predeterminada), debes bifurcar una rama release (o de publicación) a partir de develop. Al crear esta rama, se inicia el siguiente ciclo de publicación, por lo que no pueden añadirse nuevas funciones una vez pasado este punto (en esta rama solo deben producirse las soluciones de errores, la generación de documentación y otras tareas orientadas a la publicación). Cuando está lista para el lanzamiento, la rama release se fusiona en main y se etiqueta con un número de versión. Además, debería volver a fusionarse en develop, ya que esta podría haber progresado desde que se iniciara la publicación.

![[Pasted image 20221226020642.png]]
Utilizar una rama específica para preparar publicaciones hace posible que un equipo perfeccione la publicación actual mientras otro equipo sigue trabajando en las funciones para la siguiente publicación. Asimismo, crea fases de desarrollo bien definidas

Crear ramas release es otra operación de ramificación sencilla. Al igual que las ramas feature, las ramas release se basan en la rama develop. Se puede crear una nueva rama release utilizando los siguientes métodos.

![[Pasted image 20221226020650.png]]
En cuanto la publicación esté lista para su lanzamiento, se fusionará en las ramas main y develop, y luego se eliminará la rama release. Es importante volver a fusionarla en la rama develop porque podrían haberse añadido actualizaciones importantes a la rama release, y las funciones nuevas tienen que poder acceder a ellas.

![[Pasted image 20221226020657.png]]
## Ramas de correcion (hotfix)
Las ramas de mantenimiento, de corrección o de hotfix sirven para reparar rápidamente las publicaciones de producción. Las ramas hotfix son muy similares a las ramas release y feature, salvo por el hecho de que se basan en la rama main y no en la develop. Esta es la única rama que debería bifurcarse directamente a partir de main. Cuando se haya terminado de aplicar la corrección, debería fusionarse en main y develop (o la rama release actual), y main debería etiquetarse con un número de versión actualizado.

![[Pasted image 20221226020743.png]]
Se puede crear una nueva rama hotfix utilizando los siguientes métodos:

![[Pasted image 20221226020751.png]]
Al igual que al finalizar una rama release, una rama hotfix se fusiona tanto en main como en develop.

![[Pasted image 20221226020759.png]]
