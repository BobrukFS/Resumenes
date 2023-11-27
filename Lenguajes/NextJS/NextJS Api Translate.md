# NextJS Api Translate
## i18next-react

Para realizar traducciones en este caso lo que se hace primero es configurar un archivo i18n.ts que se debe inicializar en el root de la aplicacion.

```typescript
import i18next from "i18next";
import { initReactI18next } from "react-i18next";
import LanguageDetector from "i18next-browser-languagedetector";
import enTranslations from "./locales/en.json";
import esTranslations from "./locales/es.json";

i18next
  .use(initReactI18next)
  .use(LanguageDetector) //detecta el lenguaje del navegador
  .init({
    resources: {
      en: enTranslations, //diccionarios
      es: esTranslations, //diccionarios
    },
  });
```

Siempre debo tener un diccionario en una rchivo json, donde la estructura se construye de esta forma y se puede seguir anidando:

```json
{
  "translation": {
    "notFound": {
      "404": 404,
      "title": "Page not found",
      "paragraph": "Sorry, we couldn't find the page you're looking for.",
      "button": "Back to Home"
    },
}
```

Para realizar las traducciones tenemos dos formas, una es la principal y la que se debe recurrir siempre que es utilizando **i18next.t("referencia en el diccionario")** o descomponiendo el hook **useTranslation** de esta forma **const {t} = useTranslation** y ahi puedo usar **t("referencia en el diccionario")**. En caso de que no funcione de esta forma por problemas de hidratacion u otros, yo cree un componente que evita eso:

```jsx
"use client";
import React, { useState, useEffect } from "react";
import { Trans, useTranslation } from "react-i18next";
export const TransComp = ({ trad, texto }) => {
  const { t } = useTranslation();
  const [isClient, setIsClient] = useState(false);
  useEffect(() => {
    setIsClient(true);
  }, []);
  return <>{isClient ? t(trad) : texto}</>;
};
```

Para realizar cambios de idioma, podemos utilizar el metodo **i18next.changeLanguage("lenguaje a cambiar")**. Para obtener en que idioma estamos utilizamos **i18next.resolvedLanguage**.

https://react.i18next.com/
## i18next-next

Esta forma es otra forma de realizar la internalizacion de nuestra aplicacion web, mediante el enrutamiento o teniendo diferentes dominios.

https://www.i18next.com/
https://github.com/i18next/next-i18next