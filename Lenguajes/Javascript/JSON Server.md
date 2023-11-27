# JSON Server

El paquete o módulo de JSON-Server sirve para obtener una API de REST completa y falsa con cero codificación en menos de 30 segundos.

Para instalarlo utilizamos **npm install -g json-server**.

Luego creamos un archivo .json y le hacemos seguimiento mediante la siguiente linea de comandos:

```npm
json-server --watch db.json
```



El JSON de su cuerpo de solicitud debe estar cerrado por el objeto, al igual que la salida GET. (por ejemplo {"nombre": "Foobar"}).

Cuando se crea una propiedad con array en JSON Server, se crea un campo en la API RESTful que contiene un array de valores. El campo se puede acceder utilizando la barra inclinada seguida del nombre de la propiedad. Tambien podes acceder a un elemento especifico del array utilizando la barra inclinada seguida del indice del elemento.

Los valores de Id no son mutables. Cualquier valor de identificación en el cuerpo de su solicitud PUT o PATCH será ignorado. Solo se respetará un valor establecido en una solicitud POST, pero si no se ha realizado.

Si realiza solicitudes POST, PUT, PATCH o DELETE, los cambios se guardarán de forma automática y segura en db.json al utilizar lowdb. Una solicitud POST, PUT o PATCH debe incluir un encabezado application/type: application/json para usar el JSON en el cuerpo de la solicitud. De lo contrario, dará como resultado un 200 OK pero sin cambios en los datos.

Ejemplo: Aca se puede ver como se crea un campo en la API RESTful que es pasteles.

```db.json
//Ejemplo
{
    "pasteles": [
        {
            "titulo": "Carrot cake",
            "descripcion": "Deléitese con la delicia clásica de nuestros pasteles de zanahoria, disponibles para entrega en Melbourne, y experimente una combinación perfecta de capas húmedas de especias y glaseado cremoso de queso crema.",
            "precio": 1600,
            "img": "https://cakerun.com.au/wp-content/uploads/2022/09/whole-carrot-cake.webp",
            "id": 1
        },
        {
            "titulo": "Carrot cake",
            "descripcion": "Deléitese con la delicia clásica de nuestros pasteles de zanahoria, disponibles para entrega en Melbourne, y experimente una combinación perfecta de capas húmedas de especias y glaseado cremoso de queso crema.",
            "precio": 1600,
            "img": "https://cakerun.com.au/wp-content/uploads/2022/09/whole-carrot-cake.webp",
            "id": 1
        },
        {
            "titulo": "Carrot cake",
            "descripcion": "Deléitese con la delicia clásica de nuestros pasteles de zanahoria, disponibles para entrega en Melbourne, y experimente una combinación perfecta de capas húmedas de especias y glaseado cremoso de queso crema.",
            "precio": 1600,
            "img": "https://cakerun.com.au/wp-content/uploads/2022/09/whole-carrot-cake.webp",
            "id": 1
        },
        {
            "titulo": "Carrot cake",
            "descripcion": "Deléitese con la delicia clásica de nuestros pasteles de zanahoria, disponibles para entrega en Melbourne, y experimente una combinación perfecta de capas húmedas de especias y glaseado cremoso de queso crema.",
            "precio": 1600,
            "img": "https://cakerun.com.au/wp-content/uploads/2022/09/whole-carrot-cake.webp",
            "id": 1
        }
    ]
}
```