# Objeto Date
El objeto date almacena una fecha y se encarga de mantener los valores dentro de sus limites. La fecha en estos objetos se almacena en milisegundos, lo cual nos permite realizar operaciones entre fechas, calcular intervalos,etc.

Javascript ofrece el siguiente constructor para crear estos objetos:

**new Date(valor) :**  Este constructor crea un valor en milisegundos para representar una fecha basada en los valores provistos por el atributo. El atributo **valor** se puede declarar cpmo una cadena de caracteres o como los componentes de una fecha separados por comas, en este orden: año, mes, horas, minutos, segundos y milisegundos. Si no especificamos ningun valor, el constructor crea un objeto con la fecha actual del sistema.

La fecha almacenada en estos objetos se representa con un valor en milisegundos calculado desde el 1 de enero ddel año 1970. Debido a que este valor no resulta familiar para los usuarios, **los objetos Date ofrecen los siguientes metodos:**

* **getFullYear() :**  Este metodo devuelve un numero entero que representa el añor (un valor de 4 digitos).

* **getMonth() :** Este metodo devuelve un numero entero que representa al mes (un valor de 0 a 11).

* **getDate() :** Este metodo devuelve un numero entero que representa el dia del mes (un valor de 1 a 31).

* **getDay() :** Este metodo devuelve un numero entero que representa el dia de la semana (un valor de 0 a 6).

* **getHours() :** Este metodo devuelve un numero que representa las horas (un valor de 0 a 23).

* **getMinutes() :** Este metodo devuelve un numero entero que representa los minutos (un valor de 0 a 59).

* **getSeconds() :** Este metodo devuelve un numero entero que representa los segundos (un valor de 0 a 59).

* **getMilliseconds()** **:** Este metodo devuelve un numero entero que representa los milisegundos (un valor de 0 a 999).

* **getTime() :** Este metodo devuelve un numero entero en milisegundos que representa el intervalo desde el 1 de enero de 1970 hasta la fecha.

**Dato:** El valor 0 en el mes seria enero.

```javascript
//Otro tipo de ejemplo

var hoy = new Date(2017, 0, 5);

var futuro = new Date(2017, 0, 20);

var intervalo = futuro - hoy;

console.log(intervalo); // 1296000000 milisegundos, para pasarlo a segundos dividimos por 1000, luego esos segundos a minutos lo dividimos por 60.

//Funcion que resuelva el problema del horario para pasarlo a horas

function dias(milisegundos){
    return ((((milisegundos/1000)/60)/60)/24);
}
```
Los objetos Date tambien incluyen metodos para **modificar los componentes de la fecha.**

* **setFullYear(año) :** Este metodo especifica el año (un valor de 4 digitos). Tambien puede recibir valores para especificar el mes y el dia.

* **setMonth(mes) :** Este metodo especifica el mes (un valor de 0 a 11). Tambien puede recibir valores para especificar el dia.

* **setDate(dia) :** Este metodo especifica el dia (un valor de a 1 31).

* **setHours(horas) :** Este metodo especifica la hora (un valor de 0 a 23). Tambien puede recibir valores para especificar los minutos y segundos.

* **setMinutes(minutos) :** Este metodo especifica los minutos (un valor de 0 a 59). Tambien puede recibir un valor para especificar los segundos.

* **setSeconds(segundos) :** Este metodo especifica los segundos (un valor de 0 a 59). Tambien puede recibir un valor para especificar los milisegundos.

* **setMilliseconds(milisegundos) :** Este metodo especifica los milisegundos (un valor de 0 a 999).

Los objetos Date tambien ofrecen metodos para **convertir una fecha en una cadena de caracteres.**

* **toString() :** Este metodo convierte una fecha en una cadena de caracteres. El valor que devuelve se expresa en ingles americano y con el formato “Wed Jan 04 2017 22:32:48 GMT-0500(EST)”.

* **toDateString() :** Este metodo convierte una fecha en una cadena de caracteres pero solo devuelve la parte de la fecha, no la hora. El valor se expresa en ingles americano y con el formato “Wed Jan 04 2017”.

* **toTimeString() :** Este metodo convierte una fecha en una cadena de caracteres, pero solo devuelve la hora. El valor se expresa en ingles americano y con el formato “23.21:55 GMT-0500(EST)”.

**Dato:** Los objetos Date tambien incluyen metodos que consideran la localizacion(la ubicación fisica del usuario y su idioma).  **MomentJS** es una librería JS es una librería que esta relacionado a esto.