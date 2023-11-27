# Cross-Origin Resource Sharing

Al igual que `fetch`, no envía cookies ni autorización HTTP a otro origen de forma predeterminada. Para habilitarlos, configúrelo `xhr.withCredentials`en `true`:

```js
let xhr = new XMLHttpRequest();
xhr.withCredentials = true;
```

La cabecera access-controll-allow-origin va a determinar quien tiene acceso a ese recurso.

[[JSONP]]