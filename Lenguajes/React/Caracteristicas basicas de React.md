# Caracteristicas basicas de React

## Pensando en React

Cuando creo una interfaz de usuario con React, primero dividire la interfaz en partes llamadas componentes. Luego, describite los diferentes estados visuales para cada uno de los componentes. Finalmente, conectare mis componentes para que los datos fluyan a traves de ellos.

* **Paso 1**: Dividir la interfaz de usuario en una jerarquia de componentes

![[Pasted image 20230727143932.png]]
![[Pasted image 20230727144137.png]]

* **Paso 2**: Crea una version estatica en React. Para crear una version estatica de su aplicacion que represente por ejemplo un modelo de datos hay que crear componentes que reutilicen otros componentes y pasen datos usando **props**. Los **props** son una forma de pasar datos de padre a hijo. Se puede construir "de arriba hacia abajo" comenzando con la construccion de los componentes mas arriba en la jerarquia o de "abajo hacia arriba" trabajando desde los componentes mas abajo. En proyectos simples, generalmente es mas facil ir de arriba hacia abajo y en proyectos mas grandes, es mas facil ir de abajo hacia arriba. Despues de construir sus componentes, tendra una biblioteca de componentes reutilizables que representan el modelo de datos. 

Si los datos fluyen hacia abajo desde el componente de nivel superior hasta los que se encuentran en la parte inferior del arbol se llama flujo de datos unidireccional.

* **Paso 3**: Encuentre la representacion minima pero completa del estado de la interfaz de usuario. Para que la interfaz de usuario sea interactiva, debe permitir que los usuarios cambien su modelo de datos subyacente. Usará _el estado_ para esto. El estado es el conjunto minimo de datos cambiantes que la aplicacion necesita recordar. El principio mas importante para estructurar el estado es mantenerlo DRY No te repitas, es un principio destinado a reducir la repeticion de informacion que es probable que cambie, reemplazandola con abstracciones que es menos probable que cambien o utilizando la normalizacion de datos que evita la redundancia en primer lugar.

	Si los datos son variables. No se trasmite de un padre a traves de props y no podemos calcularlo segun el estado existente o los props en su componente significa que es un estado, ejemplo un texto de busqueda ya que cambia con el tiempo y no se puede calcular a partir de nada. Lo mismo con la casilla de verificacion.

* **Paso 4**: Identifique donde deberia vivir el estado. Después de identificar los datos de estado mínimos de su aplicación, debe identificar qué componente es responsable de cambiar este estado o es el _propietario_ del estado. Recuerde: React utiliza un flujo de datos unidireccional, pasando los datos por la jerarquía de componentes del componente principal al componente secundario.

Para cada parte del estado en su solicitud:

1. Identifique _cada_ componente que representa algo basado en ese estado.
2. Encuentre su componente principal común más cercano, un componente por encima de todos ellos en la jerarquía.
3. Decide dónde debe vivir el estado:
    1. A menudo, puede poner el estado directamente en su padre común.
    2. También puede poner el estado en algún componente por encima de su padre común.
    3. Si no puede encontrar un componente en el que tenga sentido poseer el estado, cree un nuevo componente únicamente para mantener el estado y agréguelo en algún lugar de la jerarquía por encima del componente principal común.

* **Paso 5** : Agregar flujo de datos inverso




## JSX

La mayoria de los proyectos de React usan JSX. JSX es mas estricto que HTML. Su componente no puede devolver varias etiquetas JSX. Tienes que envolverlos en un padre compartido, como un envoltorio div o vacio ` <></>`. Hay que cerrar siempre las etiquetas HTML.

Para especificar una clase CSS utilizamos className. Funciona de la misma manera que el atributo class.

JSX permite poner marcado en JavaScript. Las llaves permiten escapar hacia atras en JS para que pueda incrustar alguna variable de su codigo y mostrarsela al usuario. 

```jsx
return (
	<h1>
		{user.name}
	</h1>
)
```

Tambien puede escapar a Javascript desde los atributos JSX, pero debe usar llaves en lugar de comillas. 

style={{}}

style={{
          width: user.imageSize,
          height: user.imageSize
        }}
    En el ejemplo anterior, `style={{}}`no es una sintaxis especial, sino un `{}`objeto normal dentro de las `style={ }`llaves JSX. Puede usar el `style`atributo cuando sus estilos dependen de variables de JavaScript.



Se puede responder a eventos declarando funciones de controlador de eventos (event handler functions) dentro de sus componentes.

No _llame_ a la función del controlador de eventos: solo necesita _pasarla_

React llamará a su controlador de eventos cuando el usuario haga clic en el botón.

## Snippets

* rfce : Genera una estructura basica de componente donde lo exporta