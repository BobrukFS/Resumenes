# Nombres de dominio

Proporcionan un nombre legible por humanos que se utiliza para identificar un sitio web.

## Estructura de los nombres de dominio

Un nombre de dominio tiene una estructura simple compuesta de varias partes (puede ser una sola, dos, o mas), separados por puntos:

![[Pasted image 20230420145218.png]]

Para cualquier dominio que controle (por ejemplo, [mozilla.org](https://www.mozilla.org/en-US/) ), puede crear "subdominios" con diferente contenido ubicado en cada uno, como [developer.mozilla.org](https://developer.mozilla.org/) , [iot.mozilla.org](https://iot.mozilla.org/) o [bugzilla.mozilla.org](https://bugzilla.mozilla.org/) .

### TLD

Los TLD (Dominio de nivel superior) informan a los usuarios el proposito general del servicio dentras del nombre de dominio.

Los TLD mas genericos (.com, .org, .net) no requieren que los servicios web cumplan con ningun criterio en particular, pero algunos TLD imponen politicas mas estrictas, como es el caso de :

* Los TLD locales como .us, .es pueden requerir que el servicio se brinde en un idioma determinado o que se aloje en un pais determinado.
* Los TLD que contienen .gov solo pueden ser utilizados por departamentos gubernamentales.
* Los TLD que contienen .edu son solo para el uso de instituciones educativas y academicas.

## Obtencion de un dominio

Los dominios no se compran. En su lugar, se paga por el derecho a usar un nombre de dominio durante uno o mas años. Puede renovar su derecho, y su renovacion tiene prioridad sobre las solicitudes de otras personas.

Las empresas denominadas **registradores** utilizan registros de nombres de dominio para realizar un seguimiento de la informacion tecnica y administrativa que lo conecta con su nombre de dominio.

## Actualizacion de DNS

Las bases de datos DNS se almacenan en todos los servidores DNS del mundo, y todos estos servidores se refieren a unos pocos servidores especiales llamados "servidores de nombres autorizados". 

Siempre que su registrador cree o actualice cualquier informacion para un dominio determinado, la informacion debe actualizarse en cada base de datos de DNS. Cada servidor DNS que conoce un dominio determinado almacena la informacion durante un tiempo antes de que se invalide automaticamente y luego se actualice.