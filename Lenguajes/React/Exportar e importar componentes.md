# Exportar e importar componentes

## Exportar

Hay dos formas principales de exportar valores con JavaScript: **exportaciones predeterminadas** y **exportaciones con nombre**. La forma en que exporta su componente dicta cómo debe importarlo. Recibirá un error si intenta importar una exportación predeterminada de la misma manera que lo haría con una exportación con nombre. Este cuadro puede ayudarle a realizar un seguimiento:

![[Pasted image 20231027125248.png]]

Cuando escribes una importación _predeterminada_ , puedes poner el nombre que quieras después `import`. Por ejemplo, podría escribir `import Banana from './Button.js'`en su lugar y aún así le proporcionaría la misma exportación predeterminada. Por el contrario, en el caso de las importaciones con nombre, el nombre debe coincidir en ambos lados. ¡Por eso se llaman importaciones con nombre.

**Dato**: Un archivo solo puede tener una exportación predeterminada, ¡pero puede tener numerosas exportaciones con nombre!

**Dato**: Se suele utilizar exportaciones predeterminadas si el archivo exporta solo un componente y utiliza exportaciones con nombre si exporta varios componentes y valores.

**Dato**: Se desaconsejan los componentes sin nombres, como export default () => {}, porque dificultan la depuracion.

**Dato**: Es posible omitir la extension al importar.