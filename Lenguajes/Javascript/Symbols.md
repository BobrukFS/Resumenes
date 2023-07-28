# Symbols

Los símbolos se utilizan principalmente para crear propiedades de objetos privadas o para crear una forma de nombrar eventos de forma única. Sirven para asegurarnos que creamos una referencia única que nunca colisionará con otra.

El valor de **“Symbol”** representa un identificador único. Un valor de este tipo puede ser creado usando el objeto integrado **Symbol():**

![[Pasted image 20230122170604.png]]

Al crearlo, podemos agregarle una **descripción** (también llamada **symbol name**), que será útil en la depuración de código:

![[Pasted image 20230122171034.png]]

Se garantiza que los símbolos son únicos. Aunque declaremos varios Symbols con la misma descripción, éstos tendrán valores distintos. La descripción es solamente una etiqueta que no afecta nada más. Estos se crean en memoria en un nuevo espacio, no como las variables que si tienen el mismo valor se estan atando al mismo espacio en memoria.

![[Pasted image 20230122171043.png]]
**Dato:** Symbols no se autoconvierten a String. Si realmente queremos mostrar un Symbol, necesitamos llamar el método .toString() explícitamente. Para mostrar su descripción ponemos nombresymbol.description.

## Claves ocultas

Los symbols nos permiten crear propiedades ocultas y unicas en un objeto, a las cuales ninguna otra parte del código puede acceder ni sobreescribir accidentalmente. Esto permite una forma de encapsulacion debil.

Técnicamente, los symbols no están 100% ocultos. Existe un método incorporado **Object.getOwnPropertySymbols(obj)** que nos permite obtener todos los symbols. También existe un método llamado **Reflect.ownKeys(obj)** que devuelve todas las claves de un objeto, incluyendo las que son de tipo symbol.

## Symbols en objetos literales

Si queremos usar Symbol en un objeto literal, debemos usar corchetes:

![[Pasted image 20230122171114.png]]

**Dato:** Los símbolos no participan dentro de los ciclos for..in. Además también son ignorados por Object.keys(). En contraste, Object.assign copia tanto las claves string como symbol.

## Símbolos globales

Algunas veces necesitamos que symbols con el mismo nombre sean la misma entidad. Para lograr esto, existe un global symbol registry. Ahí podemos crear symbols y accesarlos después, lo cual nos garantiza que cada vez que se acceda a la clave con el mismo nombre, esta te devuelve exactamente el mismo symbol.

Para crear u accesar a un symbol en el registro global, usa **Symbol.for(symbol name)**. Esta llamada revisa el registro global, y si existe un symbol descrito con el mismo symbol name, lo retornara, de lo contrario creara un nuevo symbol Symbol(symbol name) y lo almacenara en el registro con el symbol name dado.

![[Pasted image 20230122171134.png]]
Los Symbols dentro de este registro son llamados global symbols y están disponibles y al alcance de todo el código en la aplicación.

Para los global symbols, no solo Symbol.for(key) devuelve un symbol por su nombre. Para hacer lo opuesto, (devolver el symbol name  por su global symbol) podemos usar: Symbol.keyFor().

![[Pasted image 20230122171238.png]]
El Symbol.keyFor utiliza internamente el registro “global symbol registry” para buscar la clave del symbol, por lo tanto, no funciona para los symbol que no están dentro del registro. Si el symbol no es global, no será capaz de encontrarlo y por lo tanto devolverá undefined.

**Dato:** Todo symbol tiene la propiedad description.

## Aplicacion

Al ser únicos y utilizables como nombres de propiedad, los símbolos son adecuados para definir interfaces que pueden vivir pacíficamente junto a otras propiedades, sin importar cuáles sean sus nombres.