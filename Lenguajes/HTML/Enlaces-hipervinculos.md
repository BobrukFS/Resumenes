# Enlaces-Hipervinculos

Los **enlaces** se utilizan para establecer **relaciones entre dos recursos**. Aunque la mayoria de enlaces **relacionan paginas web**, tambien es posible enlazar otros recursos como **imagenes, documentos y archivos**. 

## Elementos que crean enlaces

El Elemento HTML Anchor **`<a></a>`** crea un enlace a otras páginas de Internet, archivos o ubicaciones dentro de la misma página, direcciones de correo, o cualquier otra URL que especifiquemos en sus atributos. El elemento **`<a>`** tiene que ir acompañado siempre con el atributo **href=”…”** para especificar el url del enlace.

**Dato**: Si quieres convertir una imagen en un enlace, simplemente usa el elemento `<img>` encerrando el elemento <img> entre `<a></a>`.

Tambien se pueden crear enlaces con `<area>, <form> y <link>`.

## Atributos que pueden ir en los enlaces

* **href="..."** : Podemos dividir los enlaces o links en 3 tipos:

	**1. Enlaces internos:** Estos enlaces son los que se dan entre páginas web del mismo dominio. Por ejemplo si nosotros tenemos una pagina de contacto.html, lo referimos con href y nos llevara a nuestra pagina de contacto al tocar el enlace.

	**2.** **Enlaces externos:** Estos enlaces son los que se dan entre páginas web de distinto dominio. Aca vamos a tener que poner HTTP.

	**3. Enlaces de posición (o marcadores o de ancla):** Este enlace nos lleva a un lugar de nuestra pagina web. Esto se realiza colocando el id del elemento al que queremos ir precedido de **#**(numeral).

	**4. Enlaces externos o internos y de posicion:** Este enlace nos lleva a un lugar de una pagina web interna o externa. Para ello ponemos la URL absoluta seguida del numeral y la id de la seccion.

Es posible crear enlaces o botones que, cuando se pulsan, **abren un nuevo correo** saliente en lugar de enlazar a un recurso o página mediante **href="mailto:"**
	![[Pasted image 20221126214903.png]]

Además de la dirección de correo electrónico, puedes proporcionar otra información. De hecho, puedes incluir cualquier campo estándar contenido en el encabezado de cualquier mensaje en la URL mailto que proporciones. Los más utilizados son el «subject» (asunto), «cc» (con copia a) o «bcc» (copia oculta), y «body» (cuerpo del mensaje, que no es realmente un campo de la cabecera, pero permite especificar un mensaje breve para el nuevo correo electrónico).

Hay que tener en cuenta el uso del signo de interrogación (?) para separar la URL principal de los valores de los campos, y el símbolo ampersand (&) para separar cada campo dentro del enlace mailto:.

![[Pasted image 20221126214937.png]]

Tambien es posible utilizar el atributo href con el valor **href="tel:"** seguido del numero de telefono para que al clickear se abra para llamar con el numero de telefono ya escrito.

* **target="..."**: Este atributo nos permite indicar si la url de destino se abrira en una nueva pestaña o ventana o reemplazara la actual. Con el valor `_blank` sirve para que se abra una pestaña nueva al clickear el enlace. Hay otros valores como `_self (por defecto), _parent, _top`.

* **title="..."**: Este atributo es obligatorio por cuestion de accesibilidad y nos permite describir nuestros vinculos para hacer aparecer un etiqueta amarilla llamada tooltip con dicha informacion.

* **dowload="..."**: Este atributo sirve por si queremos hacer referencia a una descarga en lugar de a algo que abra el navegador, disponemos del atributo download para proporcionar un nombre predeterminado al archivo a guardar. Tambien lo podemos tratar como un atributo booleano, donde en vez de leer el enlace, lo descarga.

* **ping="..."**: Este atributo declara la ruta del archivo que se debe abrir en el servidor cuando el usuario hace clic en el enlace. El valor puede ser una o más URL separadas por un espacio. Ejemplo : el archivo que indica el atributo ping no se descarga, sino que se ejecuta en el servidor. Este archivo se puede usar para ejecutar código que almacena información en el servidor cada vez que el archivo principal se descarga o para llevar un control de las veces que esta acción ocurre.

* **rel**: Este atributo controla que tipos de enlaces crea el enlace, definiendo la relacion entre el documento actual y el recurso vinculado en el hipervinculo.

* **nofollow**: El atributo "nofollow" es un valor de atributo que se utiliza en los enlaces HTML para indicar a los motores de búsqueda que no deben seguir el enlace a su destino.
	Cuando un enlace tiene el atributo "nofollow", los motores de búsqueda no lo consideran como un voto de confianza para el sitio de destino, lo que significa que el enlace no contribuirá al ranking del sitio en los resultados de búsqueda. Esto se utiliza comúnmente en los comentarios de los blogs o enlaces publicitarios, donde no se quiere que los motores de búsqueda sigan los enlaces y los consideren como una forma de manipular los resultados de búsqueda.
	El atributo "nofollow" también puede ayudar a proteger su sitio web de spam y contenido malicioso, ya que los motores de búsqueda no seguirán los enlaces a sitios de dudosa reputación.
	
### Urls relativas y absolutas

Url (Uniform Resource Locator) hace referencia al identificador unico de cada recurso disponible en internet. La URL de un recurso tiene dos objetivos principales: Identificar de forma unica a ese recurso y localizar de forma eficiente a ese recurso.

*  Una **URL absoluta**: Hace referencia a una dirección definida por su ubicación absoluta en la web, esta incluye el protocolo HTTP y el nombre del dominio. Por ejemplo, si subes una página de inicio index.html a un directorio llamado projects que se encuentra dentro de la raíz de un servidor web, y el dominio del sitio web es http://www.example.com, se podrá acceder a la página desde http://www.example.com/projects/index.html. Una URL absoluta siempre apuntará a la misma dirección, sin importar desde dónde se utilice.

* Una **URL relativa:** Hace referencia a una dirección que depende de la posición del archivo desde donde se utiliza. Por ejemplo, si desde un archivo ubicado en http://www.example.com/projects/index.html queremos enlazar hacia un archivo PDF ubicado en el mismo directorio, la URL sería simplemente el nombre del archivo (por ejemplo: project-brief.pdf) no necesitamos más información. Si el archivo PDF está situado en un subdirectorio dentro de projects llamado pdfs, la URL relativa es: pdfs/project-brief.pdf (la URL absoluta equivalente sería: http://www.example.com/projects/pdfs/project-brief.pdf).

	Una URL relativa hará referencia a diferentes direcciones según dónde se encuentre el archivo desde el cual se utiliza — por ejemplo, si movemos nuestro archivo index.html del directorio projects a la raíz del sitio web (el nivel más alto, no cualquiera de los otros directorios), la URL relativa pdfs/project-brief.pdf ahora hará referencia a http://www.example.com/pdfs/project-brief.pdf, en lugar de a http://www.example.com/projects/pdfs/project-brief.pdf.

A partir de las indicaciones anteriores podemos llegar a pensar que es mejor utilizar referencias absolutas en todos los casos; después de todo, estas no se rompen cuando la página se traslada como ocurre con las referencias relativas. Sin embargo, debes utilizar enlaces relativos siempre que sea posible cuando enlaces a otras ubicaciones dentro del mismo sitio web, es decir del mismo dominio. Cuando vinculas a otro sitio web, deberás utilizar un vínculo absoluto. Esto se debe a que:

1) Resulta más eficiente utilizar URLs relativas cuando sea posible. Cuando usas una URL absoluta, el navegador comienza buscando la ubicación real del servidor en el Sistema de nombres de dominio. Entonces va a ese servidor y busca el archivo solicitado. En cambio, con una URL relativa, el navegador simplemente busca el archivo solicitado en el mismo servidor. Si usas URLs absolutas donde las URLs relativas lo harían, constantemente estás haciendo que tu navegador haga un trabajo adicional, lo cual significa que funcionará de manera menos eficiente.

2) Las URLs relativas suelen ser mucho más cortas que las absolutas, lo que hace que el código sea mucho más fácil de leer.

Otro ejemplo:

![[Pasted image 20230622214746.png]]
