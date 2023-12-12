# EsLint
ESLint es una herramienta para identificar e informar sobre patrones encontrados en el código ECMAScript/JavaScript, con el objetivo de hacer que el código sea más consistente y evitar errores.

Para instalar eslint utilizamos

```shell
npm install --save-dev eslint
```

Puede iniciar y configurar ESLint usando este comando:

```shell
npm init @eslint/config
```

Al ejecutar dicho comando, vamos a tener un archivo **.eslintrc** para poder configurar las reglas

```json
{
    "root": true,
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": { "project": ["./tsconfig.json"] },
    "plugins": [
        "@typescript-eslint"
    ],
    "rules": {
        "@typescript-eslint/strict-boolean-expressions": [
            2,
            {
                "allowString" : false,
                "allowNumber" : false
            }
        ],
       
		 "semi": ["error", "always"],
         "quotes": ["error", "double"]
    },
    "ignorePatterns": ["src/**/*.test.ts", "src/frontend/generated/*"]
}
```

Este archivo de configuración de ESLint define las reglas y configuraciones que ESLint utilizará para eliminar su código TypeScript. Incluye los siguientes elementos:

* **`root`: verdadero:** esto establece el archivo de configuración como el archivo de configuración raíz, lo que significa que se utilizará para todo el proyecto.
    
* **`extends`: ["eslint:recommended", "plugin:@typescript-eslint/recommended"]:** Esto especifica que el archivo de configuración debe extender las reglas recomendadas de ESLint y las reglas recomendadas del `@typescript-eslint`complemento.
    
* **`parser`: "@typescript-eslint/parser":** Esto especifica que se debe utilizar el analizador TypeScript para analizar el código.
    
* **`parserOptions`: {"project": ["./tsconfig.json"]}:** esto especifica que el `tsconfig.json`archivo debe usarse para configurar el analizador.
    
* **`plugins`: ["@typescript-eslint"]:** Esto especifica que `@typescript-eslint`se debe utilizar el complemento.
    
* **`rules`: {...}`:** Esto define las reglas específicas que ESLint aplicará.
    
* **`ignorePatterns`**: `["src/** / _.test.ts", "src/frontend/generated/_ "]:` Esto especifica que ESLint debe ignorar los archivos que coincidan con los patrones especificados.

Los nombres `"semi"`y `"quotes"`son los nombres de [las reglas](https://eslint.org/docs/latest/rules) en ESLint. El primer valor es el nivel de error de la regla y puede ser uno de estos valores:

- `"off"`o `0`- desactivar la regla
- `"warn"`o `1`- activar la regla como advertencia (no afecta el código de salida)
- `"error"`o `2`- activar la regla como error (el código de salida será 1)