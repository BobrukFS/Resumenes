# Internet

## ¿Que es internet?

Una **red** es un grupo de dispositivos que estan conectados entre si ya sea fisicamente (cable ethernet) o de forma inalambrica (Wifi). 

![[Pasted image 20230420142834.png]]
![[Pasted image 20230420142851.png]]

Para evitar conectar todos los dispositivos con todos los dispositivos, ya que para eso necesitariamos muchos cables, conectamos los dispositivos a una computadora especial llamada **enrutador o router**. Este enrutador cumple una unica funcion: Se encarga de asegurar que el mensaje enviado desde un dispositivo emisor llegue al destino correcto.

![[Pasted image 20230420143022.png]]

Como un enrutador otro dispositivo, nada nos impide conectar con otro enrutador y asi escalar infinitamente.

![[Pasted image 20230420143339.png]]

Para conectar nuestra red a la infraestructura telefono necesitamos un equipo especial llamado **modem**. Este modem convierte la informacion de nuestra red en informacion manejable por la infraestructura telefonica y viceversa.

![[Pasted image 20230420143727.png]]

El siguiente paso es enviar el mensaje desde nuestra red a la red que queremos llegar. Para lograr eso, conectaremos nuestra red a un proveedor de servicios de internet (ISP). Un ISP es una empresa que gestiona algunos enrutadores especiales interconectados, que tambien pueden acceder a enrutadores de otros ISP. Asi, el mensaje de nuestra red es llevada a traves de la red de redes de ISP, hasta el destino. **Internet** consiste en toda esta infraestructura de redes, es por eso que se dice que internet es una red de redes.

![[Pasted image 20230420143936.png]]

**Dato**: Internet es una infraestructura, mientras que la Web es un servicio construido sobre dicha infraestructura.
## ¿Como funciona?

Las computadores conectadas a la web se llaman **clientes** y **servidores**.

![[Pasted image 20230420150409.png]]

* Los **clientes** son dispositivos de los usuarios conectados a internet y el software que se encuentra disposible y permite acceder a internet en dichos dispositivos (normalmente, un navegador como chrome o firefox).

* Los **servidores** son computadores que almacenan paginas web, sitios o aplicaciones. Cuando un dispositivo cliente quiere acceder a una pagina web, una copia de la pagina web se descarga desde el servidor en el equipo cliente y se muestra en el navegador web del usuario.

**Dato**: Un sitio web se compone de muchos archivos diferentes: 
	* **Archivos de codigo:** Como HTML, CSS, Javascript, etc.
	* **Recursos:** Resto de materiales que conforman un sitio web, como imagenes, musica, video, etc.


Internet funciona conectando dispositivos y sistemas informaticos mediante un conjunto de protocolos estandarizados. Estos protocolos definen como se intercambian la informacion entre los dispositivos y garantizan que los datos se trasmitan de forma fiable y segura.

* **Protocolo de internet (IP)** :  Es el responsable de enrutar los **paquetes** (Los datos se envian a traves de la web como miles de trozos pequeños, estos se llaman paquetes, que son una pequeña unidad de datos que se trasmite a traves de una red) a su destino correcto. Cada dispositivo conectado a una red posee una **direccion ip**. Esta direccion esta compuesta por una serie de cuatro numeros separados por puntos, por ejemplo: 192.168.2.10.

	Los humanos tenemos una mayor dificultad para recordar esas direcciones, por lo que se utiliza lo que conocemos como [[Nombres de dominio]] (Un nombre legible por humanos que se utiliza para identificar un sitio web). Por ejemplo, google.com es el nombre de dominio que utilizamos para la direccion IP 173.194.121.32.

* **Protocolo de control de trasmision (TCP)**: Garantiza que los paquetes se trasmitan de forma confiable y en el orden correcto.

* **Sistema de nombres de dominio (DNS)**: El sistema de nombres de dominio es responsable de traducir los nombres de dominio en direcciones IP.

* **Protocolo de transferencia de hipertexto (HTTP)**: Es un protocolo de aplicacion que define un idioma para que los clientes y servidores se puedan comunicar. 

* **SSL/TLS**: Los protocolos secure socket layer y transport layer security se utilizan para proporcionar una comunicacion segura a traves de internet.

Uno de los beneficios clave del uso de protocolos estandarizados es que permiten que los dispositivos y sistemas de diferentes fabricantes y proveedores se comuniquen entre si sin problemas.

**¿Que sucede exactamente?**

1. El navegador va al servidor DNS y encuentra la direccion real del servidor donde el sitio web se encuentra.
2. El navegador envia un mensaje de peticion HTTP al servidor, pidiendole que envie una copia de la pagina web para el cliente. Este mensaje y todos los datos enviados entre el cliente y el servidor, se envian a traves de tu conexion a internet usando TCP/IP.
3. Se comenzaran a enviar los archivos de la pagina web (primero el index.html) al navegador como una serie de pequeños trozos llamados paquetes de datos.
4. El navegador reune los pequeños trozos, forma un sitio web completo y te lo muestra.




HTTP es el protocolo utilizado para transferir datos entre un cliente (como un navegador web) y un servidor (como un sitio web). Cuando visita un sitio web, su navegador web envia una solicitud HTTP al servidor, solicitando la pagina web u otro recurso que haya solicitado. Luego, el servidor envia una respuesta HTTP al cliente, que contiene los datos solicitados.

HTTPS es una version mas segura de HTTP, que encripta los datos que se trasmiten entre el cliente y el servidor mediante encriptacion SSL/TLS. Esto proporciona una capa adicional de seguridad que ayuda a proteger la informacion confidencial, como las credenciales de inicio de sesion, la informacion de pago y otros datos personales.

Cuando visita un sitio web que utiliza HTTPS, su navegador web mostrará un icono de candado en la barra de direcciones, lo que indica que la conexión es segura.

TCP/IP es el protocolo de comunicacion subyacente. Proporciona una entrega de datos confiable, ordenada y con verificacion de errores entre aplicaciones que se ejecutan en diferentes dispositivos.

* Puertos: Los puertos se utilizan para identificar la aplicacion o el servicio que se ejecuta en un dispositivo. A cada aplicacion o servicio se le asigna un numero de puerto unico, lo que permite que los datos se envien al destino correcto.
* Sockets: Un socket es una combinacion de una direccion IP y un numero de puerto, que representa un punto final especifico para la comunicacion. Los sockets se utilizan para establecer conexiones entre dispositivos y transferir datos entre aplicaciones.
* Conexiones: Una conexión se establece entre dos enchufes cuando dos dispositivos quieren comunicarse entre sí. Durante el proceso de establecimiento de la conexión, los dispositivos negocian varios parámetros, como el tamaño máximo del segmento y el tamaño de la ventana, que determinan cómo se transmitirán los datos a través de la conexión.
* Transferencia de datos: Una vez que se establece una conexion, los datos se pueden trasnferir entre las aplicaciones que se ejecutan en cada dispositivo. Los datos generalmente se transmiten en segmentos, y cada segmento contiene un número de secuencia y otros metadatos para garantizar una entrega confiable.

SSL/TLS

Se usa comúnmente para proporcionar conexiones seguras para aplicaciones como navegadores web, clientes de correo electrónico y programas de transferencia de archivos.

-   **Certificados:** los certificados SSL/TLS se utilizan para establecer la confianza entre el cliente y el servidor. Contienen información sobre la identidad del servidor y están firmados por un tercero de confianza (una autoridad de certificación) para verificar su autenticidad.
    
-   **Protocolo de enlace:** durante el proceso de protocolo de enlace SSL/TLS, el cliente y el servidor intercambian información para negociar el algoritmo de cifrado y otros parámetros para la conexión segura.
    
-   **Cifrado:** una vez que se establece la conexión segura, los datos se cifran utilizando el algoritmo acordado y se pueden transmitir de forma segura entre el cliente y el servidor.

Al crear aplicaciones y servicios basados ​​en Internet, es importante comprender cómo funciona SSL/TLS y asegurarse de que su aplicación esté diseñada para usar SSL/TLS al transmitir datos confidenciales, como credenciales de inicio de sesión, información de pago y otros datos personales. También deberá asegurarse de obtener y mantener certificados SSL/TLS válidos para sus servidores y de seguir las mejores prácticas para configurar y proteger sus conexiones SSL/TLS. Al hacerlo, puede ayudar a proteger los datos de sus usuarios y garantizar la integridad y confidencialidad de la comunicación de su aplicación a través de Internet.

[[World wide web]]




