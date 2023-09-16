# Depuracion o debugging
Es el proceso de encontrar y corregir los errores en nuestro codigo. Existen varios tipos de errores, desde errores de programacion hasta errores logicos, etc. La mayoria de las veces, para determinar que es lo que no funciona en nuestro codigo es necesario leer las intrucciones una por una y seguir la logica hasta detectar el error. Afortunadamente, los navegadores ofrecen herramientas para ayudarnos a resolver estos problemas.

A veces los errores no son errores de programacion, si no errores logicos. El interprete JS no puede encontrar ningun error en el codigo, pero la aplicación no hace lo que esperamos. Esto se puede deberse a varios motivos, desde una operación que olvidamos realizar, hasta una variable iniciada con el valor incorrecto. Estos son los errores mas dificiles de identificar, pero existe una tecnica de programacion llamada **breakpoints (puntos de interrupcion)** que nos puede ayudar a encontrar una solucion.

Los **breakpoints** son puntos de interrupcion en nuestro codigo que establecemos para controlar el estado actual de la aplicación (haciendo click en la linea de codigo donde lo queremos generar). En un breakpoint, mostramos los valores actuales de las variables o un mensaje que nos informa de que el interprete ha llegado a esa parte del codigo. Es decir un breakpoint es un punto de codigo donde el debugger pausara automaticamente la ejecucion de JS. Mientras se pausa el código, podemos examinar las variables actuales, ejecutar comandos en la consola, etc. En otras palabras, podemos depurar.

Siempre podemos encontrar una lista de los breakpoints en el panel derecho. Esto es muy útil cuando tenemos muchos breakpoints en varios archivos. Ya que nos permite: Saltar rápidamente al breakpoint en el código (haciendo click en él dentro del panel), Desactivar temporalmente el breakpoint desmarcándolo , Eliminar el breakpoint haciendo click derecho y seleccionando quitar/eliminar/remove,etc.

Tambien existen los **breakpoints condicionales** estos se crean haciendo click derecho en el numero de linea y tocando la opcion de breakpoint condicional. Este solo se disparara cuando la expresion dada, que debes proveer cuando la creas, sea verdadera. Esto es util cuando necesitamos detener la ejecucion para un determinado valor de las variables o parametros de funcion.

Tambien podemos pausar el codigo utilizando el comando **debugger** que es equivalente a un breakpoint. Un ejemplo:

![[Pasted image 20230121210925.png]]
En la **zona de informacion y control** encontramos:

![[Pasted image 20230121210936.png]]
![[Pasted image 20230121210942.png]]
![[Pasted image 20230121210951.png]]
![[Pasted image 20230121211035.png]]
## Excepciones
A veces sabemos de antemano que nuestro codigo puede producir un error, para evitar que el script muera podemos gestionar los errores. Los errores que se pueden gestionar por el codigo se llaman **excepciones,** y el proceso de generar una excepcion se llama **throw**. En estos terminos, cuando informamos de nuestros propios errores decimos que arrojamos una **excepcion.** 

[[Manejo de excepciones]]