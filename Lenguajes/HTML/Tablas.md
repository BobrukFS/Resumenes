# Tabla
Una **tabla** es un conjunto estructurado de datos formado por filas y columnas (datos tabulares). Una tabla le permite buscar rápida y fácilmente valores que indican algún tipo de conexión entre diferentes tipos de datos. Si los datos se presentan, comparan, ordenan, calculan o cruzan, probablemente `<table>`sea la elección correcta.

* **`<table></table>`**: El elemento **table** abarca todo el contenido de la tabla.

	* **`<th></th>`**: El elemento **th** define una celda para la cabecera de la tabla. Incluye etiquetas de apertura y cierre para delimitar el contenido de la celdas.
	
	* **`<tr></tr`**: El elemento **tr** define una fila de celdas. Incluye etiquetas de apertura y cierre para agrupar las celdas.
	
	* **`<td></td>`**: El elemento **td** define una celda. Incluye etiquetas de apertura ycierre para delimitar el contenido de la celda.
	
Los encabezados y las celdas de las tablas tienen los atributos **colspan="..."** y **rowspan="..."**, que nos permiten hacer que los elementos abarquen mas de una fila o columna. Ambos aceptan un valor numérico sin unidades, que es igual al número de filas o columnas que desea abarcar.

Tambien existen elementos para agrupar elementos en tablas:

* **`<thead></thead>`**: Este elemento sirve para agrupar cabeceras.

*  **`<tbody></tbody>`**: Es el cuerpo de nuestra trabla.

*  **`<tfoot></tfoot>`**: Este elemento debe envolver la parte de la tabla que es el pie de pagina, por ejemplo, podria ser una ultima fila con los elementos de las filas anteriores sumados.

Podemos darle estilo a las tablas con el elemento **`<col>`**:

Podemos especificar la información una vez, en un elemento **`<col>`**. Los elementos **`<col>`** se especifican dentro de un **`<colgroup>`**  justo debajo de la etiqueta **`<table>`** de apertura.

Para aplicar el estilo a varias columnas tenemos que utilizar el atributo **span="..."**.

![[Pasted image 20221127202721.png]]

* **`<caption></caption>`**: El elemento **caption** sirve para agregar un titulo a la tabla. El elemento **caption** debe estar inmediatamente luego de la etiqueta table.

```html
<table>
  <caption>MLW Alumni</caption>
  <thead>
    <tr>
      <th>Name</th>
      <th>Destiny</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Hal Gibrah</th>
      <td>Calculator</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>Cathy Terr</th>
      <td>Waste disposal</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>Lou Minious</th>
      <td>Lightbulb</td>
      <td>1956</td>
    </tr>
  </tbody>
</table>
```

![[Pasted image 20230424223726.png]]

### Atributo scope

El atributo **scope="..."** define las celdas con las que el elemento **th** se relaciona. Puede tener los siguientes valores:

* **row**: El encabezado se relaciona con todas las celdas de la fila a la que pertenece.

* **col**: El encabezado se relaciona con todas las celdas de la columna a la que pertenece.

* **rowgroup**: El encabezado pertenece a un grupo de filas y se relaciona con todas sus celdas. 

* **colgroup**: El encabezado pertenece a un colgroup y se relaciona con todas sus celdas.