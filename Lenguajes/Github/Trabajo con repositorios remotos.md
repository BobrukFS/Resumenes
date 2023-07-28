# Trabajo con repositorios remotos
Los repositorios remotos son versiones de su proyecto que están alojadas en Internet o en alguna red. 

Es muy posible que pueda estar trabajando con un repositorio "remoto" que, de hecho, está en el mismo host que usted. La palabra "remoto" no implica necesariamente que el repositorio esté en otro lugar de la red o de Internet, solo que está en otro lugar. 
## Mostrando nuestros servidores remotos

Para ver qué servidores remotos ha configurado, puede ejecutar el comando **git remote**. Enumera los nombres abreviados de cada identificador remoto que ha especificado. Si ha clonado su repositorio, al menos debería ver `origin` : ese es el nombre predeterminado que Git le da al servidor desde el que clonó:

![[Pasted image 20221221122617.png]]

También puede especificar **-v**, que le muestra las URL que Git ha almacenado para que se use el nombre abreviado al leer y escribir en ese control remoto:

![[Pasted image 20221221122629.png]]
Si tiene más de un control remoto, el comando los enumera a todos. Por ejemplo, un repositorio con múltiples controles remotos para trabajar con varios colaboradores podría verse así.

![[Pasted image 20221221123209.png]]
## Agregar repositorios remotos

Para agregar un nuevo repositorio Git remoto como un nombre corto al que puede hacer referencia fácilmente, ejecute **git remote add shortname url**:

![[Pasted image 20221223203353.png]]
Por ejemplo, si desea obtener toda la información que tiene Paul pero que aún no tiene en su repositorio, puede ejecutar git fetch pb:

![[Pasted image 20221223203431.png]]
Para utilizar git remote ya debemos tener un repositorio git existente.

### Clone

Tambien podemos utilizar **git clone url carpeta** que lo que hara es crear un nuevo repositorio git al bajar el repositorio de la url especificada. Ademas de vincular el repositorio remoto con mi git.

![[Pasted image 20221223204417.png]]

Si hago **git clone url .** me baja el repositorio remoto a mi repositorio local y evita crearse una carpeta nueva.

### Fork

Tambien podemos utilizar **fork** cuando deseamos colaborar en un proyecto pero no tenemos permisos de escritura (push access). Github intentara hacer una copia entera del usuario en nuestra cuenta de usuario que quedara almacenada en nuestra cuenta como un nuevo repositorio, donde podremos realizar cualquier cambio. Cualquier persona puede hacer un fork de cualquier proyecto open-source, realizar cambios y aportes al proyecto original y crear lo que se denomina un "Pull Request".

Si hacemos clic en el botón Pull Request, accedemos a una ventana que nos pedirá un título y una descripción de nuestro Pull Request. Usualmente, vale la pena esforzarnos en pensar ambos datos, ya que va a ser de mucha ayuda para el dueño del proyecto original a determinar qué cambios estuvimos haciendo y si los tiene que aceptar o no. Cuando hagamos clic en el botón Create pull request, el dueño del proyecto del que hicimos el Fork va a recibir una notificación de que alguien está sugiriendo cambios y va a poder acceder a toda la información de los cambios que propusimos. En la vista de diferencias, el dueño del proyecto puede hacer clic en cualquier línea de cambio propuesta para dejar un comentario sobre alguna de ellas. Ahora el usuario que está contribuyendo al proyecto original simplemente puede realizar más commits en el branch en cuestión y volver a hacer un push. Esta acción actualizará automáticamente el Pull Request. Si se afectan líneas de código que habían sido previamente comentadas por alguien, se verán colapsadas en la página de la discusión del Pull Request. Agregar commits a un Pull Request existente no activa una notificación. Una vez que se hayan realizado los cambios o corregido el trabajo, lo ideal es dejar un nuevo comentario para informar sobre ellos al dueño del proyecto. Algo interesante es que GitHub verifica que el Pull Request pueda ser integrado de manera limpia y sin problemas. En ese caso, se mostrará un botón de atajo para realizar esta operación.


## Obtener y extraer de sus servidores remotos

Para obtener datos de tus proyectos remotos se ejecuta **git fetch shortname del servidor remoto**. Es el comando que le dice a tu git local que recupere la última información de los metadatos del original (aunque no hace ninguna transferencia de archivos. Es más bien como comprobar si hay algún cambio disponible).

El comando va a ese proyecto remoto y extrae todos los datos de ese proyecto remoto que aún no tiene en el repositorio local. Después de hacer esto, debe tener referencias a todas las sucursales desde ese control remoto, que puede fusionar o inspeccionar en cualquier momento.

Si clona un repositorio, el comando agrega automáticamente ese repositorio remoto con el nombre "origen". Por lo tanto, git fetch origin obtiene cualquier trabajo nuevo que se haya enviado a ese servidor desde que lo clonó (o lo obtuvo por última vez). Es importante tener en cuenta que el  git fetch solo descarga los datos en su repositorio local; no los fusiona automáticamente con ninguno de sus trabajos ni modifica lo que está trabajando actualmente. Tienes que fusionarlo manualmente en tu trabajo cuando estés listo.

Tambien tenemos el comando **git pull remoto branch que queremos extraer en la rama actual** que se emplea ademas para verificar si hay algun cambio, para extraer y descargar contenido desde un repositorio remoto y actualizar (fusionar) al instante el repositorio local para reflejar ese contenido.

![[Pasted image 20221223205430.png]]

## Push a los servidores remotos

Cuando tiene su proyecto en un punto que desea compartir, debe impulsarlo aguas arriba. El comando para esto es simple: **git push remote branch que queremos empujar al servidor**. Si desea enviar su rama master a su servidor origin (nuevamente, la clonación generalmente configura ambos nombres para usted automáticamente), puede ejecutar esto para enviar cualquier confirmación que haya hecho al servidor:

![[Pasted image 20221223204721.png]]

Si quiero subir varias ramas al mismo tiempo, pongo: 

```git
git push origin main develop features
```

Tambien podemos vincular el repositorio remoto con la rama, asi solo tenemos que escribir el comando git push, sin necesidad de estar especificando que rama y a que repositorio remoto se envia. Esto se logra con: **git push -u origin main**
## Inspeccionar un repositorio remoto

Para inspeccionar un repositorio remoto podemos utilizar **git remote show nombre del servidor remoto**.

![[Pasted image 20221223204956.png]]
Este comando muestra a qué rama se envía automáticamente cuando se ejecuta git push en ciertas ramas. También le muestra qué sucursales remotas en el servidor aún no tiene, qué sucursales remotas tiene que se han eliminado del servidor y varias sucursales locales que pueden fusionarse automáticamente con su sucursal de seguimiento remoto cuando ejecuta git pull.
## Cambio de nombre y eliminacion de servidores remotos

Para cambiar el nombre se utiliza **git remote rename name newname**.

![[Pasted image 20221223205130.png]]
Para eliminar un repositorio remoto se utiliza **git remove nombre**.

![[Pasted image 20221223205201.png]]
Una vez que elimine la referencia a un control remoto de esta manera, también se eliminarán todas las ramas de seguimiento remoto y los ajustes de configuración asociados con ese control remoto.